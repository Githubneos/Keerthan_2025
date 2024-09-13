---
layout: page
title: Accomplishments
description: Blog for accomplishments and attempts
permalink: /accomplishments/
---

<div>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
</div>

<script>
// JavaScript code for the Snake Game

const canvas = document.getElementById("gameCanvas");
const ctx = canvas.getContext("2d");

const boxSize = 20;
const canvasSize = 400;
const rows = canvasSize / boxSize;
const cols = canvasSize / boxSize;

// Snake settings
let snake = [{ x: 5, y: 5 }];
let direction = { x: 0, y: 0 };
let food = { x: 10, y: 10 };
let score = 0;

function drawBox(x, y, color) {
    ctx.fillStyle = color;
    ctx.fillRect(x * boxSize, y * boxSize, boxSize, boxSize);
}

function drawSnake() {
    snake.forEach(segment => drawBox(segment.x, segment.y, "green"));
}

function drawFood() {
    drawBox(food.x, food.y, "red");
}

function updateSnake() {
    const head = { x: snake[0].x + direction.x, y: snake[0].y + direction.y };

    // Wrap around walls (turn off walls)
    head.x = (head.x + cols) % cols;
    head.y = (head.y + rows) % rows;

    // Check for food collision
    if (head.x === food.x && head.y === food.y) {
        score++;
        placeFood();
    } else {
        snake.pop(); // Remove the tail if no food eaten
    }

    // Check for snake collision (itself)
    if (snake.some(segment => segment.x === head.x && segment.y === head.y)) {
        resetGame();
    }

    snake.unshift(head); // Add new head
}

function placeFood() {
    food = {
        x: Math.floor(Math.random() * cols),
        y: Math.floor(Math.random() * rows)
    };
}

function resetGame() {
    snake = [{ x: 5, y: 5 }];
    direction = { x: 0, y: 0 };
    score = 0;
    placeFood();
    alert("Game Over! Score: " + score);
}

function draw() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    drawSnake();
    drawFood();
}

function gameLoop() {
    updateSnake();
    draw();
}

function changeDirection(event) {
    const keyPressed = event.keyCode;

    if (keyPressed === 37 && direction.x === 0) {
        direction = { x: -1, y: 0 }; // Left
    } else if (keyPressed === 38 && direction.y === 0) {
        direction = { x: 0, y: -1 }; // Up
    } else if (keyPressed === 39 && direction.x === 0) {
        direction = { x: 1, y: 0 }; // Right
    } else if (keyPressed === 40 && direction.y === 0) {
        direction = { x: 0, y: 1 }; // Down
    }
}

// Set up event listeners and start game loop
document.addEventListener("keydown", changeDirection);
placeFood();
setInterval(gameLoop, 150); // Game speed
</script>

<style>
/* Inline CSS for the Snake Game */

body {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
    background-color: #f0f0f0;
    font-family: Arial, sans-serif;
}

h1 {
    margin-bottom: 20px;
}

canvas {
    border: 1px solid #000;
    background-color: #fff;
}
</style>