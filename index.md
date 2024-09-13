---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
image: /images/mario_animation.png
hide: true
comments: false
---

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

<div id="game"></div>

<script>
// JavaScript for Minesweeper Game

document.addEventListener('DOMContentLoaded', function () {
    const gridSize = 10; // Grid size (10x10)
    const mineCount = 15; // Number of mines
    const grid = document.getElementById("game");
    const cells = [];
    let gameOver = false;

    function createBoard() {
        grid.innerHTML = '';
        cells.length = 0;
        gameOver = false;

        // Create grid
        for (let i = 0; i < gridSize; i++) {
            const row = [];
            for (let j = 0; j < gridSize; j++) {
                const cell = document.createElement("button");
                cell.classList.add("cell");
                cell.dataset.x = i;
                cell.dataset.y = j;
                cell.addEventListener('click', () => handleClick(i, j));
                row.push(cell);
                grid.appendChild(cell);
            }
            cells.push(row);
        }

        // Randomly place mines
        let minesPlaced = 0;
        while (minesPlaced < mineCount) {
            const x = Math.floor(Math.random() * gridSize);
            const y = Math.floor(Math.random() * gridSize);
            if (!cells[x][y].classList.contains('mine')) {
                cells[x][y].classList.add('mine');
                minesPlaced++;
            }
        }

        // Calculate numbers for each cell
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (!cells[i][j].classList.contains('mine')) {
                    const count = countMinesAround(i, j);
                    if (count > 0) cells[i][j].textContent = count;
                }
            }
        }
    }

    function countMinesAround(x, y) {
        let count = 0;
        for (let i = -1; i <= 1; i++) {
            for (let j = -1; j <= 1; j++) {
                const newX = x + i;
                const newY = y + j;
                if (newX >= 0 && newX < gridSize && newY >= 0 && newY < gridSize) {
                    if (cells[newX][newY].classList.contains('mine')) count++;
                }
            }
        }
        return count;
    }

    function handleClick(x, y) {
        if (gameOver || cells[x][y].classList.contains('revealed')) return;

        cells[x][y].classList.add('revealed');
        if (cells[x][y].classList.contains('mine')) {
            revealMines();
            alert('Game Over! You clicked on a mine.');
            gameOver = true;
        } else if (cells[x][y].textContent === '') {
            revealEmpty(x, y);
        }

        // Check if the game is won
        if (checkWin()) {
            alert('Congratulations! You won!');
            gameOver = true;
        }
    }

    function revealMines() {
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (cells[i][j].classList.contains('mine')) {
                    cells[i][j].classList.add('revealed');
                    cells[i][j].textContent = '💣';
                }
            }
        }
    }

    function revealEmpty(x, y) {
        for (let i = -1; i <= 1; i++) {
            for (let j = -1; j <= 1; j++) {
                const newX = x + i;
                const newY = y + j;
                if (newX >= 0 && newX < gridSize && newY >= 0 && newY < gridSize) {
                    if (!cells[newX][newY].classList.contains('revealed') && !cells[newX][newY].classList.contains('mine')) {
                        cells[newX][newY].classList.add('revealed');
                        if (cells[newX][newY].textContent === '') {
                            revealEmpty(newX, newY);
                        }
                    }
                }
            }
        }
    }

    function checkWin() {
        for (let i = 0; i < gridSize; i++) {
            for (let j = 0; j < gridSize; j++) {
                if (!cells[i][j].classList.contains('mine') && !cells[i][j].classList.contains('revealed')) {
                    return false;
                }
            }
        }
        return true;
    }

    createBoard();
});
</script>

<style>
/* CSS for Minesweeper Game */

#game {
    display: grid;
    grid-template-columns: repeat(10, 40px);
    gap: 2px;
    margin-top: 20px;
}

.cell {
    width: 40px;
    height: 40px;
    background-color: #e0e0e0;
    border: none;
    font-size: 18px;
    cursor: pointer;
    transition: background-color 0.2s;
}

.cell.revealed {
    background-color: #fff;
    border: 1px solid #ccc;
    cursor: default;
}

.cell.mine.revealed {
    color: red;
    font-size: 24px;
}
</style>
