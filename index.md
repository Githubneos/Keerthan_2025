---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
hide: true
comments: true
---

<table>
    <tr>
        <td><img src="{{site.baseurl}}/images/logo.png" height="60" title="Tools" alt=""></td>
        <td><a href="{{site.baseurl}}/accomplishments/">Accomplishments</a></td>
        <td><a href="{{site.baseurl}}/front-end/">HTML Frontend</a></td>
        <td><a href="{{site.baseurl}}/cookie-clicker/">Cookie Clicker</a></td>
        <td><a href="{{site.baseurl}}/sprint1/">Sprint 1 hacks</a></td>
    </tr>
</table>

<style>
  <div class="post-content e-content" itemprop="articleBody"><style>
  body {
    font-family: 'Arial', sans-serif;
    background-color: #1a1a1a;
    color: #f4f4f4;
    margin: 0;
    padding: 20px;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .container {
    max-width: 800px;
    width: 100%;
    background-color: #2c2c2c;
    padding: 40px;
    border-radius: 10px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    text-align: center;
  }

  h1 {
    font-size: 36px;
    margin-bottom: 40px;
    color: #ffffff;
  }

  .main-link {
    display: inline-block;
    font-size: 22px;
    background-color: #3498db;
    color: white;
    padding: 15px 30px;
    border-radius: 5px;
    text-decoration: none;
    margin-bottom: 30px;
    transition: background-color 0.3s ease;
  }

  .main-link:hover {
    background-color: #2980b9;
  }

  .links {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  .link-container {
    width: 48%;
    margin-bottom: 20px;
  }

  .dropdown {
    background-color: #3c3c3c;
    color: #f4f4f4;
    padding: 15px;
    border-radius: 5px;
    text-decoration: none;
    position: relative;
    display: block;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  .dropdown:hover {
    background-color: #555555;
  }

  .dropdown-content {
    display: none;
    position: absolute;
    background-color: #555555;
    min-width: 200px;
    box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
    z-index: 1;
    border-radius: 5px;
    padding: 10px;
    top: 40px;
  }

  .dropdown:hover .dropdown-content {
    display: block;
  }

  ul {
    text-align: left;
    padding-left: 20px;
  }
</style>

<div class="container">
  <h1>Programming Topics</h1>

  <div class="links">
    <!-- Dropdown for Unit 1 -->
        <div class="link-container">
       <div class="dropdown" onclick="window.location.href='https://nighthawkcoders.github.io/portfolio_2025/csp/big-idea/p2/3-1';">Unit 1 — Variables and Assignments
        <div class="dropdown-content">
          <ul>
            <li>Naming: SnakeCase, Pascal Case, CamelCase</li>
            <li>Types of Variables: Intigers, Strings, Boolean, Floats, Lists, Dictionaries</li>
            <li>Operators</li>
            <li>Arrays and Objects in Javascript: Arrays, Objects</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 2 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/32hacks';">Unit 2 — Data Abstraction
        <div class="dropdown-content">
          <ul>
            <li>Learned how various data types can use abstraction for efficiency</li>
            <li>Created dictionaries to encapse variables</li>
            <li>Learned about number functions to create a simple javascript and python calculator</li>
            <li>Learned about looping through strings to print outputs in python</li>
            <li>Functions that compare different strings with eachother, and returning true or false outputs.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 3 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/33-35hacks';">Unit 3 — Mathematical Expressions
        <div class="dropdown-content">
          <ul>
            <li>Using arithmetic operators (+,-,*,/) to perform calculatoins</li>
            <li>Also learned the code for factorials involving variable creation as well as multiplication and subtraction. Can also use division and addition based on personal preference.</li>
            <li>Learned about fibonacci sequence and how to calculate the "n"th digit of fibonacci sequence</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 4 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='https://nighthawkcoders.github.io/portfolio_2025/csp/big-idea/p2/3-1';">Unit 4 — Strings and String Operations
        <div class="dropdown-content">
          <ul>
            <li>Go over string functions in both javascript and python as follows:</li>
            <li>Concatenation, Interpolation, Indexing (substrings), escape characters (javascript)</li>
            <li>Using looping to create a palindrome checker and reverse order hack (python)</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 5 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/33-35hacks';">Unit 5 — Boolean Expressions
        <div class="dropdown-content">
          <ul>
            <li>Learned how boolean expressions involve using loops and conditions to make decisions.</li>
            <li>Rational Operators, Logical Operators </li>
            <li>Creating Logic Gate Similator in boty Python and Java</li>
            <li>Contrapositive Law in Python and Java</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 6 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/36-37hacks';">Unit 6 — Conditionals
        <div class="dropdown-content">
          <ul>
            <li>Go over If Statements, Else Statements, Javascript and Python Examples. </li>
            <li>Use these conditionals in our popcorn hacks</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 7 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/36-37hacks';">Unit 7 — Nested Conditionals
        <div class="dropdown-content">
          <ul>
            <li>If statements, Else Statements, Nested Conditions, and Examples in both languages we're learning.</li>
            <li>Conditionals using variables and operations to pair with if and else statements to create programs.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 8 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/38hacks';">Unit 8 — Iterations
        <div class="dropdown-content">
          <ul>
            <li>Going over Looping: For Loops, While Loops / Do-While Loops, Index Loops</li>
            <li>Learning how to continue and break loops</li>
            <li>Endless/Infinite loop. When Condition is not met then loop continues infintetly</li>
            <li>Common operations: iterating over rows and columns.</li>
            <li>Using exceptions with loops</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 9 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/310hacks';">Unit 10 — Lists
        <div class="dropdown-content">
          <ul>
            <li>Learning how storage and maniplation of data is performed using indexing and lists.</li>
            <li>Learned how to: Add values to lists, insert elements to list, append elements to end of lists, remove elements from list, and calculate the length of a list.</li>
            <li>Learned about Pseudocode:</li>
            <li>Variables in sudocode, number lists, modulus operator (remainder) and control structures.</li>
            <li>Practiced using iterations in functions.</li>
          </ul>
        </div>
      </div>
    </div>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Number Guessing Game</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #f8f9fa;
        }
        input, button {
            padding: 10px;
            margin-top: 10px;
        }
        #result {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

# Guess the Number Game

<style>
/* Make the text color black */
body {
    color: black;
}
</style>

<script>
  // Variables
  let secretNumber = Math.floor(Math.random() * 100) + 1;  // Random number between 1 and 100
  let attempts = 5;  // Number of attempts left
  let output = document.createElement("p");  // Create a paragraph element to show messages
  document.body.appendChild(output);  // Append the paragraph to the body of the page

  // Function to check the user's guess
  function checkGuess() {
    // Data abstraction: get user input from the text box
    let guess = document.getElementById('guess').value;
    guess = parseInt(guess);  // Convert the input to an integer
    let message = "";  // String to store the message
    
    // Conditional statements to compare the guess with the secret number
    if (guess < secretNumber) {
      message = "Too low!";
    } else if (guess > secretNumber) {
      message = "Too high!";
    } else {
      message = "You got it!";
      attempts = 0;  // Set attempts to 0 to end the game
    }
    
    // Nested conditionals to check the number of attempts
    attempts--;
    if (attempts > 0 && message !== "You got it!") {
      message += " You have " + attempts + " attempts left.";
    } else if (attempts == 0 && message !== "You got it!") {
      message = "Game over! The correct number was " + secretNumber + ".";
    }
    
    // Display the message in the paragraph
    output.innerHTML = message;
  }
</script>

<!-- Form for user input -->
<form>
  <!-- Input box for the user to enter a guess -->
  <input type="number" id="guess" placeholder="Enter your guess" />
  
  <!-- Button to trigger the checkGuess function -->
  <button type="button" onclick="checkGuess()">Submit</button>
</form>


### Emoji hack

- Hello, world! 🌍
- I'm happy to share my work with you! 🎉
- Let's code something amazing! 💻
- Feel free to contact me anytime 📫

## Comments

<!-- Load the utterances script -->
<div id="utterances-comments"></div>
<script src="https://utteranc.es/client.js"
        repo="Githubneos/Keerthan_2025"     <!-- replace with your GitHub username and repository name -->
        issue-term="pathname"                   <!-- this links the comments to the page based on its URL path -->
        label="comment"                         <!-- adds a label to each comment issue -->
        theme="github-light"                    <!-- you can change this to "github-dark" or other themes -->
        crossorigin="anonymous"
        async>
</script>


# Frontend Hack: Dark Mode Toggle

Click the button below to toggle dark mode.

<button class="toggle-button" onclick="toggleDarkMode()">Toggle Dark Mode</button>

<script>
  function toggleDarkMode() {
    document.body.classList.toggle('dark-mode');
    document.body.classList.toggle('light-mode');
    // Save mode in local storage
    const mode = document.body.classList.contains('dark-mode') ? 'dark' : 'light';
    localStorage.setItem('theme', mode);
  }

  // Load the theme from local storage on page load
  (function loadTheme() {
    const savedTheme = localStorage.getItem('theme');
    if (savedTheme === 'dark') {
      document.body.classList.add('dark-mode');
      document.body.classList.remove('light-mode');
    }
  })();
</script>

<style>
  /* Basic styling for light and dark modes */
  body {
    transition: background-color 0.3s, color 0.3s;
  }
  .light-mode {
    background-color: #ffffff;
    color: #000000;
  }
  .dark-mode {
    background-color: #121212;
    color: #ffffff;
  }
  /* Toggle button styling */
  .toggle-button {
    padding: 10px 20px;
    background-color: #888;
    color: white;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    position: fixed;
    top: 20px;
    right: 20px;
  }
</style>


<style>
/* Custom CSS directly within index.md */
body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  color: #333;
}

h1, h2, h3 {
  color: #003366;
}

.post {
  background-color: white;
  padding: 20px;
  margin: 10px 0;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

.post h2 {
  margin-top: 0;
  font-size: 1.5em;
  color: #0056b3;
}

.post p {
  font-size: 1.1em;
  line-height: 1.6;
}
</style>

<div class="blog-posts">
  {% for post in site.posts %}
    <div class="post">
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p><small>Posted on {{ post.date | date: "%B %d, %Y" }}</small></p>
      <p>{{ post.excerpt }}</p>
      <a href="{{ post.url }}">Read more</a>
    </div>
  {% endfor %}
</div>

# Minefield Game

Try not to click on a mine! Click on the cells, and avoid the hidden mines. Good luck!

<div id="minefield"></div>
<p id="status"></p>

<style>
  #minefield {
    display: grid;
    grid-template-columns: repeat(10, 40px);
    gap: 5px;
    margin-top: 20px;
  }
  .cell {
    width: 40px;
    height: 40px;
    background-color: #8bc34a;
    text-align: center;
    font-size: 18px;
    cursor: pointer;
    border: 1px solid #555;
  }
  .mine {
    background-color: red;
    color: white;
  }
  .safe {
    background-color: #cfd8dc;
  }
</style>

<script>
  const minefield = document.getElementById('minefield');
  const statusText = document.getElementById('status');
  const rows = 10, cols = 10, minesCount = 15;
  let minePositions = [];

  // Initialize the minefield
  function initMinefield() {
    minePositions = [];
    minefield.innerHTML = '';
    statusText.textContent = 'Click a cell to start!';

    for (let i = 0; i < rows * cols; i++) {
      const cell = document.createElement('div');
      cell.classList.add('cell');
      cell.addEventListener('click', () => revealCell(cell, i));
      minefield.appendChild(cell);
    }

    // Place mines at random positions
    while (minePositions.length < minesCount) {
      const minePos = Math.floor(Math.random() * rows * cols);
      if (!minePositions.includes(minePos)) minePositions.push(minePos);
    }
  }

  // Reveal cell when clicked
  function revealCell(cell, index) {
    if (minePositions.includes(index)) {
      cell.classList.add('mine');
      cell.textContent = '💣';
      statusText.textContent = 'Game Over! You hit a mine.';
      revealMines();
    } else {
      cell.classList.add('safe');
      cell.textContent = '✔️';
    }
  }

  // Reveal all mines after losing
  function revealMines() {
    const cells = document.querySelectorAll('.cell');
    minePositions.forEach(pos => {
      cells[pos].classList.add('mine');
      cells[pos].textContent = '💣';
    });
  }

  // Start the game
  initMinefield();
</script>


# Celtics and Warriors

Here's an image of the Celtics and the Warriors.

![Celtics](https://upload.wikimedia.org/wikipedia/en/thumb/8/8f/Boston_Celtics.svg/1200px-Boston_Celtics.svg.png)
![Warriors](https://upload.wikimedia.org/wikipedia/en/thumb/0/01/Golden_State_Warriors_logo.svg/1200px-Golden_State_Warriors_logo.svg.png)
