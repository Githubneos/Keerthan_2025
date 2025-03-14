---
layout: base
title: CPT & PPR Review
description: CPT & PPR
permalink: /cpt/
author: Keerthan Karumudi
hide: true
comments: true
---

# CPT & PPR Blog



## CPT Requirements

### Big Idea 1.1 & 1.2: Collaboration, Program Function, and Purpose
- #### Iteration, SCRUM, Agile, Issues, Kanban
    - Used Agile methodologies to iteratively improve features based on testing and feedback.
    - Kanban board helped track issues like incorrect guess validation and grading logic.
    - Addressed issues such as improving UI, debugging API endpoints, and refining game logic.
- #### Program Code
    - Followed structured programming with functions to handle guesses, scoring, and submissions.
    - Applied FRQ-style coding practices, including function abstraction and modularity.
- #### Key Tools and Methods
    - Blind Trace Challenge: Used SSIM (Structural Similarity Index) for scoring, Flask API for data storage.
    - Debugged using Postman and browser Inspect tools for API testing and frontend improvements

 ### Big Idea 1.3: Program Design and Development
- #### Frontend and Backend Integration
    - Developed a responsive UI for both games with interactive elements for submitting guesses/drawings.
    - Backend manages guess storage, SSIM scoring for Blind Trace, and API endpoints.
- #### Improving Applications
    - Enhanced game functionality based on feedback from peers and N@tM reviews.
    - Improved Blind Trace Challenge by storing past scores and adding a submission table.
- #### Design Documentation
    - Used flowcharts and UML diagrams to map out game logic and API requests.
- Documented API endpoints for fetching and storing game data.
- #### Code Comments and Style
    - Followed PEP 8 for clean and maintainable Python code.
- Used meaningful comments to document game logic and API implementation.

### Big Idea 1.4: Debugging Code and Fixing Errors
- #### Backend Debugging
    - Used Postman to test API requests for both games (guess submissions, score retrieval).
    - Fixed JSON response formatting issues in Flask for better frontend integration.
- #### Frontend Debugging
    - Used browser Inspect tools to debug rendering issues in both games.
    - Fixed JavaScript errors affecting data display (e.g., retrieving past scores, incorrect guess checks).
- #### End-to-End Tracing
    - Ensured correct retrieval and display of stored game data.
- #### Testing
    - Simulated user interactions to catch errors in both games before deployment.

### Big Idea 2: Data Management and Storage
- #### Database Management with SQLite
    - Blind Trace Challenge: Stored user drawings, SSIM scores, and past game data.
- #### Data Retrieval and Display
    - Optimized database structure to handle multiple game sessions.
- #### Data Security and Privacy
    - Implemented validation checks to prevent invalid inputs and SQL injection.
    - Restricted API access using authentication mechanisms.
- #### Data Backup and Recovery
    - Considered periodic backups for database preservation.
    - Ensured deletion functions properly remove user data while maintaining game integrity.

    ### Big Idea 4: Internet and Deployment
- #### Deployment Strategies
    - Deployed the application on AWS using Docker and Nginx.
    - Implemented CI/CD pipeline to automate deployment updates.
- #### HTTP and RESTful APIs
    - Designed RESTful APIs for submitting guesses, retrieving past scores, and grading drawings.
    - Used HTTP methods (GET, POST, DELETE) for handling user interactions.
- #### Security and Authentication
    - Used JWT authentication to protect API endpoints.
    - Enforced HTTPS encryption for secure communication.
- #### Performance Optimization
    - Optimized frontend by minimizing assets and improving caching.
- Improved backend efficiency using database indexing and query optimization.
- #### Monitoring and Logging
    - Implemented logging to track API requests and debug potential issues.
    - Monitored game performance and identified areas for improvement.


## PPR Requirements

import traceback
import base64
import io
import numpy as np
from flask import Blueprint, request, jsonify, g
from flask_restful import Api, Resource
from datetime import datetime
from __init__ import db
from api.jwt_authorize import token_required
from model.blind_trace import BlindTraceSubmission
from PIL import Image
import requests

#Blueprint & API Initialization
blind_trace_api = Blueprint('blind_trace_api', __name__, url_prefix='/api/blind_trace')
api = Api(blind_trace_api)

class BlindTraceAPI:
    class _Submission(Resource):
        @token_required()
        def post(self):
            """Submit a drawing, grade it using SSIM, and store the result"""
            current_user = g.current_user
            data = request.get_json()

            # Validate request data
            if not data or "image_url" not in data or "drawing" not in data:
                return {"message": "Missing required fields", "error": "Bad Request"}, 400

            try:
                # Decode base64 drawing
                drawing_data = base64.b64decode(data["drawing"].split(",")[1])
                drawing_img = Image.open(io.BytesIO(drawing_data)).convert("L")  # Convert to grayscale

                # Fetch reference image
                reference_img = Image.open(io.BytesIO(requests.get(data["image_url"]).content)).convert("L")

                # Resize to match dimensions
                reference_img = reference_img.resize(drawing_img.size)

                # Convert images to numpy arrays
                drawing_arr = np.array(drawing_img)
                reference_arr = np.array(reference_img)

                # Compute Mean Squared Error (MSE)
                mse = np.mean((drawing_arr - reference_arr) ** 2)
                max_mse = np.prod(drawing_arr.shape) * 255**2  # Max possible MSE for 8-bit images
                score = round(100 * (1 - mse / max_mse), 2)  # Normalize to percentage

                # Save submission
                submission = BlindTraceSubmission(
                    user_id=current_user.id,
                    image_url=data["image_url"],
                    drawing=data["drawing"],
                    score=score,
                    submission_time=datetime.utcnow()
                )
                db.session.add(submission)
                db.session.commit()

                return {
                    "message": "Submission graded",
                    "score": score,
                    "submission": submission.read()
                }, 201

            except Exception as e:
                db.session.rollback()
                traceback.print_exc()
                return {"message": "Internal Server Error", "error": str(e)}, 500

        @token_required()
        def get(self):
            """Retrieve all past submissions for the current user"""
            current_user = g.current_user
            try:
                submissions = BlindTraceSubmission.query.filter_by(user_id=current_user.id).all()
                return {
                    "message": "Submissions retrieved successfully",
                    "submissions": [sub.read() for sub in submissions]
                }, 200
            except Exception as e:
                traceback.print_exc()
                return {"message": "Internal Server Error", "error": str(e)}, 500

        @token_required()
        def delete(self):
            """Delete a submission by ID"""
            current_user = g.current_user
            data = request.get_json()

            if not data or "id" not in data:
                return {"message": "Missing required fields", "error": "Bad Request"}, 400

            try:
                submission = BlindTraceSubmission.query.get(data["id"])
                if not submission:
                    return {"message": "Submission not found", "error": "Not Found"}, 404
                
                if submission.user_id != current_user.id:
                    return {"message": "Unauthorized to delete this submission", "error": "Forbidden"}, 403

                db.session.delete(submission)
                db.session.commit()

                return {"message": "Submission deleted successfully"}, 200

            except Exception as e:
                db.session.rollback()
                traceback.print_exc()
                return {"message": "Internal Server Error", "error": str(e)}, 500

    # Register API endpoint
    api.add_resource(_Submission, '/submission')




### Component B
[Scribble Demo](https://youtu.be/xtaRHwqYLoQ)



### Component C

#### Segment 1 Procedure def(sequencing and selection)

def update(self, user, score, date):
    """
    Updates the Blind Trace submission instance.
    
    Args:
        user (str): The updated user who submitted the drawing.
        score (float): The updated similarity score.
        date (str): The updated date of submission.
    """
    self._user = user
    self._score = score
    self._date = date

    db.session.commit()

    return {'message': 'Blind Trace submission updated successfully'}





#### Segment 2 

function editBlindTrace(id, currentUser, currentScore, currentDate) {
    // Display the edit form and hide the add form
    document.getElementById('blind-trace-edit-form').style.display = 'block';
    document.getElementById('blind-trace-form').style.display = 'none'; // Hide the Add form

    // Set placeholder values to the current submission details
    document.getElementById('edit-user').placeholder = currentUser;
    document.getElementById('edit-score').placeholder = currentScore;
    document.getElementById('edit-date').placeholder = currentDate;

    // Clear input fields to allow user entry
    document.getElementById('edit-user').value = "";
    document.getElementById('edit-score').value = "";
    document.getElementById('edit-date').value = "";

    // When the form is submitted, send a PUT request to update the Blind Trace submission
    const form = document.getElementById('edit-blind-trace-form');
    form.onsubmit = async function(event) {
        event.preventDefault(); // Prevent default form submission behavior

        // Get user input; if fields are empty, keep the previous values
        const user = document.getElementById('edit-user').value || currentUser;
        const score = document.getElementById('edit-score').value || currentScore;
        const date = document.getElementById('edit-date').value || currentDate;

        // Send a PUT request to update the submission in the backend
        const response = await fetch(`${API_URL}/blind-trace/${id}`, { // Calls the backend update function
            method: 'PUT', // Specifies that this request is an update operation
            headers: {
                'Content-Type': 'application/json', // Informs the backend that JSON data is being sent
            },
            body: JSON.stringify({ user, score, date }), // Sends the updated submission data to the backend
        });

        // Handle the response
        if (response.ok) {
            alert('Blind Trace submission updated successfully!'); // Notify user of success
            fetchBlindTraceSubmissions(); // Refresh the displayed submissions
            cancelEditBlindTrace(); // Hide the edit form and show the add form again
        } else {
            alert('Failed to update Blind Trace submission.'); // Notify user of failure
        }
    };
}


### Segment 3 & 4: List Usage

#### Storing Data in a List

blind_traces = BlindTrace.query.all()  # Retrieving all Blind Trace submissions
result = [  # Using a list to store multiple submissions
    {
        'id': submission.id,
        'user': submission.user,
        'score': submission.score,
        'date': submission.date
    }
    for submission in blind_traces  # Iteration over the list of submissions
]



#### Using Data from the List

@app.route('/api/blindtrace/random', methods=['GET'])
def get_random_blindtrace():
    submissions = BlindTraceSubmission.query.all()  # Fetch all Blind Trace submissions
    if not submissions:  # Check if no submissions are available
        return jsonify({'error': 'No submissions available'}), 404

    random_submission = random.choice(submissions)  # Select a random submission
    return jsonify({
        'id': random_submission.id,
        'user': random_submission.user,  # Assuming 'user' is the user who made the submission
        'score': random_submission.score,  # Assuming 'score' is the evaluation score
        'date': random_submission.date_created  # Assuming 'date_created' stores when it was submitted
    }), 200



