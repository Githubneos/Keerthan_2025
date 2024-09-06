---
layout: page
title: About ME
permalink: /about/
---

Places I have Lived:

<div style="display: flex; justify-content: center; align-items: center; margin-top: 20px;">
  
  <!-- California Flag -->
  <div style="text-align: center; margin: 20px;">
    <img src="https://upload.wikimedia.org/wikipedia/commons/0/01/Flag_of_California.svg" alt="Flag of California" style="width: 200px; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <div style="font-size: 18px; font-weight: bold; color: #555; margin-top: 10px;">forever</div>
  </div>

  <!-- India Flag -->
  <div style="text-align: center; margin: 20px;">
    <img src="https://upload.wikimedia.org/wikipedia/en/4/41/Flag_of_India.svg" alt="Flag of India" style="width: 200px; height: auto; border: 1px solid #ddd; border-radius: 8px;">
    <div style="font-size: 18px; font-weight: bold; color: #555; margin-top: 10px;">2 weeks a year</div>
  </div>

</div>


Welcome to my website! Here are some of my favorite movies:

<div style="display: flex; flex-wrap: wrap; justify-content: center; margin-top: 20px;">

  <!-- Movie 1 -->
  <div style="background-color: white; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); margin: 15px; width: 200px; overflow: hidden; transition: transform 0.2s;">
      <img src="https://m.media-amazon.com/images/I/51NiGlapXlL._AC_.jpg" alt="The Shawshank Redemption" style="width: 100%; height: auto;">
      <div style="padding: 10px; font-size: 18px; font-weight: bold; color: #555;">The Shawshank Redemption</div>
  </div>

  <!-- Movie 2 -->
  <div style="background-color: white; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); margin: 15px; width: 200px; overflow: hidden; transition: transform 0.2s;">
      <img src="https://m.media-amazon.com/images/I/51oBxmV-dML._AC_.jpg" alt="The Godfather" style="width: 100%; height: auto;">
      <div style="padding: 10px; font-size: 18px; font-weight: bold; color: #555;">The Matrix</div>
  </div>

</div>

# My Interests in Computer Science and Engineering

Here are some of my interests: 

## Computer Science Principles (CSP) Interests

- **Coding and Programming**: I enjoy writing code to solve problems and making passion projects using languages like Python, JavaScript, and Scratch.
- **Game Development**: Making simple games using tools like Unity, Roblox, or even Python! 
- **Web Design**: Learning to build my own websites using HTML, CSS, and JavaScript. I like making sites that look cool and are easy to use.
- **Artificial Intelligence (AI) for Beginners**: Exploring how AI works and how it’s used in apps like Siri, Alexa, and Google Assistant.
- **Robotics and Automation**: Building and programming simple robots using kits like LEGO Mindstorms or VEX Robotics.

## Engineering Interests

- **Electronics and Circuits**: Experimenting with simple circuits using batteries, wires, LEDs, and breadboards to understand how electronics work.
- **3D Printing and Design**: Learning to design and print 3D models using software like Tinkercad or SketchUp. It's amazing to see digital designs turn into real objects!
- **Mechanical Engineering Basics**: Understanding how gears, levers, and pulleys work in machines and gadgets.
- **Environmental Engineering**: Learning about renewable energy sources like solar and wind power and how technology can help protect the environment.
- **DIY Projects and Makerspace Activities**: Building things with my hands, like making model bridges, rockets, or even simple machines.
- **Aerospace and Space Exploration**: Fascinated by rockets, space missions, and how spacecraft are designed to explore the universe.


<div id="movie-summaries">
  <!-- Summaries and images will be loaded here dynamically -->
</div>

<script>
// JavaScript to fetch movie summaries and images from Wikipedia

async function fetchWikipediaInfo() {
  const terms = ["Jurassic Park (film)", "Avengers (2012 film)"];
  const movieContainer = document.getElementById("movie-summaries");

  for (const term of terms) {
    const url = `https://en.wikipedia.org/api/rest_v1/page/summary/${encodeURIComponent(term)}`;
    try {
      const response = await fetch(url);
      const data = await response.json();

      // Create a new div element to hold each movie's information
      const movieElement = document.createElement("div");
      movieElement.style.marginBottom = "40px"; // Add some space between movie sections

      // Add movie title
      const titleElement = document.createElement("h2");
      titleElement.textContent = data.title;
      movieElement.appendChild(titleElement);

      // Add movie summary
      const summaryElement = document.createElement("p");
      summaryElement.textContent = data.extract;
      movieElement.appendChild(summaryElement);

      // Add movie image if available
      if (data.thumbnail && data.thumbnail.source) {
        const imgElement = document.createElement("img");
        imgElement.src = data.thumbnail.source;
        imgElement.alt = data.title;
        imgElement.style.width = "200px"; // Resize image for display
        imgElement.style.height = "auto";
        movieElement.appendChild(imgElement);
      }

      // Add a link to read more on Wikipedia
      const linkElement = document.createElement("a");
      linkElement.href = data.content_urls.desktop.page;
      linkElement.target = "_blank"; // Open in a new tab
      linkElement.textContent = "Read more on Wikipedia";
      movieElement.appendChild(linkElement);

      // Append the movie element to the container
      movieContainer.appendChild(movieElement);
    } catch (error) {
      console.error("Error fetching Wikipedia summary:", error);
    }
  }
}

// Call the function to fetch and display movie summaries and images
fetchWikipediaInfo();
</script>



