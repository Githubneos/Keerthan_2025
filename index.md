---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
image: /images/mario_animation.png
hide: true
comments: false
---
(% include nav/home.html %)
<table>
    <tr>
        <td><img src="{{site.baseurl}}/images/logo.png" height="60" title="Tools" alt=""></td>
        <td><a href="{{site.baseurl}}/about me">About Me</a></td>
        <td><a href="{{site.baseurl}}/accomplishments">Accomplishments</a></td>
    </tr>
</table>

<!-- Liquid:  statements -->

<!-- Include submenu from _includes to top of pages -->

<!--- Concatenation of site URL to frontmatter image  --->
{% assign sprite_file = site.baseurl | append: page.image %}
<!--- Has is a list variable containing mario metadata for sprite --->
{% assign hash = site.data.mario_metadata %}  
<!--- Size width/height of Sprit images --->
{% assign pixels = 256 %}

<!--- HTML for page contains <p> tag named "Mario" and class properties for a "sprite"  -->

<p id="mario" class="sprite"></p>
  
<!--- Embedded Cascading Style Sheet (CSS) rules, 
        define how HTML elements look 
--->
<style>

  /*CSS style rules for the id and class of the sprite...
  */
  .sprite {
    height: {{pixels}}px;
    width: {{pixels}}px;
    background-image: url('{{sprite_file}}');
    background-repeat: no-repeat;
  }

  /*background position of sprite element
  */
  #mario {
    background-position: calc({{animations[0].col}} * {{pixels}} * -1px) calc({{animations[0].row}} * {{pixels}}* -1px);
  }
</style>

<!--- Embedded executable code--->
<script>
  ////////// convert YML hash to javascript key:value objects /////////

  var mario_metadata = {}; //key, value object
  {% for key in hash %}  
  
  var key = "{{key | first}}"  //key
  var values = {} //values object
  values["row"] = {{key.row}}
  values["col"] = {{key.col}}
  values["frames"] = {{key.frames}}
  mario_metadata[key] = values; //key with values added

  {% endfor %}

  ////////// game object for player /////////

  class Mario {
    constructor(meta_data) {
      this.tID = null;  //capture setInterval() task ID
      this.positionX = 0;  // current position of sprite in X direction
      this.currentSpeed = 0;
      this.marioElement = document.getElementById("mario"); //HTML element of sprite
      this.pixels = {{pixels}}; //pixel offset of images in the sprite, set by liquid constant
      this.interval = 100; //animation time interval
      this.obj = meta_data;
      this.marioElement.style.position = "absolute";
    }

    animate(obj, speed) {
      let frame = 0;
      const row = obj.row * this.pixels;
      this.currentSpeed = speed;

      this.tID = setInterval(() => {
        const col = (frame + obj.col) * this.pixels;
        this.marioElement.style.backgroundPosition = `-${col}px -${row}px`;
        this.marioElement.style.left = `${this.positionX}px`;

        this.positionX += speed;
        frame = (frame + 1) % obj.frames;

        const viewportWidth = window.innerWidth;
        if (this.positionX > viewportWidth - this.pixels) {
          document.documentElement.scrollLeft = this.positionX - viewportWidth + this.pixels;
        }
      }, this.interval);
    }

    startWalking() {
      this.stopAnimate();
      this.animate(this.obj["Walk"], 3);
    }

    startRunning() {
      this.stopAnimate();
      this.animate(this.obj["Run1"], 6);
    }

    startPuffing() {
      this.stopAnimate();
      this.animate(this.obj["Puff"], 0);
    }

    startCheering() {
      this.stopAnimate();
      this.animate(this.obj["Cheer"], 0);
    }

    startFlipping() {
      this.stopAnimate();
      this.animate(this.obj["Flip"], 0);
    }

    startResting() {
      this.stopAnimate();
      this.animate(this.obj["Rest"], 0);
    }

    stopAnimate() {
      clearInterval(this.tID);
    }
  }

  const mario = new Mario(mario_metadata);

  ////////// event control /////////

  window.addEventListener("keydown", (event) => {
    if (event.key === "ArrowRight") {
      event.preventDefault();
      if (event.repeat) {
        mario.startCheering();
      } else {
        if (mario.currentSpeed === 0) {
          mario.startWalking();
        } else if (mario.currentSpeed === 3) {
          mario.startRunning();
        }
      }
    } else if (event.key === "ArrowLeft") {
      event.preventDefault();
      if (event.repeat) {
        mario.stopAnimate();
      } else {
        mario.startPuffing();
      }
    }
  });

  //touch events that enable animations
  window.addEventListener("touchstart", (event) => {
    event.preventDefault(); // prevent default browser action
    if (event.touches[0].clientX > window.innerWidth / 2) {
      // move right
      if (currentSpeed === 0) { // if at rest, go to walking
        mario.startWalking();
      } else if (currentSpeed === 3) { // if walking, go to running
        mario.startRunning();
      }
    } else {
      // move left
      mario.startPuffing();
    }
  });

  //stop animation on window blur
  window.addEventListener("blur", () => {
    mario.stopAnimate();
  });

  //start animation on window focus
  window.addEventListener("focus", () => {
     mario.startFlipping();
  });

  //start animation on page load or page refresh
  document.addEventListener("DOMContentLoaded", () => {
    // adjust sprite size for high pixel density devices
    const scale = window.devicePixelRatio;
    const sprite = document.querySelector(".sprite");
    sprite.style.transform = `scale(${0.2 * scale})`;
    mario.startResting();
  });
</script>

👍 Python is awesome! 😀

<style>
    .logo-container {
        display: inline-block;
        margin: 20px;
        text-align: center;
    }
    .logo-container img {
        width: 200px;
        height: auto;
    }
    .logo-container p {
        font-size: 18px;
        font-weight: bold;
    }
</style>

<div style="display: flex; flex-wrap: wrap; justify-content: center; margin-top: 20px;">

  <!-- Golden State Warriors logo -->
  <div style="background-color: white; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); margin: 15px; width: 200px; overflow: hidden; transition: transform 0.2s;">
      <img src="https://upload.wikimedia.org/wikipedia/en/0/01/Golden_State_Warriors_logo.svg" alt="Golden State Warriors" style="width: 100%; height: auto;">
      <div style="padding: 10px; font-size: 18px; font-weight: bold; color: #555;">Golden State Warriors</div>
  </div>

  <!-- Boston Celtics logo -->
  <div style="background-color: white; border-radius: 8px; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); margin: 15px; width: 200px; overflow: hidden; transition: transform 0.2s;">
      <img src="https://upload.wikimedia.org/wikipedia/en/8/8f/Boston_Celtics.svg" alt="Boston Celtics" style="width: 100%; height: auto;">
      <div style="padding: 10px; font-size: 18px; font-weight: bold; color: #555;">Boston Celtics</div>
  </div>


  
</div>
# Snake Game
Play the Snake game below!

<!-- HTML for the Snake Game -->
<div id="game-container" style="text-align: center;">
    <canvas id="gameCanvas" width="400" height="400" style="border:1px solid #000000;"></canvas>
</div>

<!-- JavaScript for Snake Game -->
<script>
    // JavaScript for Snake Game
    document.addEventListener('DOMContentLoaded', (event) => {
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const box = 20; // Size of each square on the grid
        let snake = [{x: 9 * box, y: 10 * box}];
        let direction = 'RIGHT';
        let food = {
            x: Math.floor(Math.random() * 19 + 1) * box,
            y: Math.floor(Math.random() * 19 + 1) * box,
        };
        let score = 0;

        // Control the snake direction
        document.addEventListener('keydown', (event) => {
            if (event.key === 'ArrowLeft' && direction !== 'RIGHT') direction = 'LEFT';
            else if (event.key === 'ArrowUp' && direction !== 'DOWN') direction = 'UP';
            else if (event.key === 'ArrowRight' && direction !== 'LEFT') direction = 'RIGHT';
            else if (event.key === 'ArrowDown' && direction !== 'UP') direction = 'DOWN';
        });

        // Check collision
        function collision(head, array) {
            for (let i = 0; i < array.length; i++) {
                if (head.x === array[i].x && head.y === array[i].y) return true;
            }
            return false;
        }

        // Draw the game
        function draw() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            for (let i = 0; i < snake.length; i++) {
                ctx.fillStyle = (i === 0) ? 'green' : 'white';
                ctx.fillRect(snake[i].x, snake[i].y, box, box);
                ctx.strokeStyle = 'red';
                ctx.strokeRect(snake[i].x, snake[i].y, box, box);
            }

            // Draw food
            ctx.fillStyle = 'red';
            ctx.fillRect(food.x, food.y, box, box);

            // Old head position
            let snakeX = snake[0].x;
            let snakeY = snake[0].y;

            // Direction movement
            if (direction === 'LEFT') snakeX -= box;
            if (direction === 'UP') snakeY -= box;
            if (direction === 'RIGHT') snakeX += box;
            if (direction === 'DOWN') snakeY += box;

            // If snake eats food
            if (snakeX === food.x && snakeY === food.y) {
                score++;
                food = {
                    x: Math.floor(Math.random() * 19 + 1) * box,
                    y: Math.floor(Math.random() * 19 + 1) * box,
                };
            } else {
                // Remove tail
                snake.pop();
            }

            // New head
            const newHead = {x: snakeX, y: snakeY};

            // Game over
            if (
                snakeX < 0 ||
                snakeY < 0 ||
                snakeX >= canvas.width ||
                snakeY >= canvas.height ||
                collision(newHead, snake)
            ) {
                clearInterval(game);
                alert('Game Over! Your score is: ' + score);
                return;
            }

            snake.unshift(newHead);
            // Draw the score
            ctx.fillStyle = 'black';
            ctx.font = '20px Arial';
            ctx.fillText('Score: ' + score, 10, canvas.height - 10);
        }

        // Start the game
        const game = setInterval(draw, 100);
    });
</script>



