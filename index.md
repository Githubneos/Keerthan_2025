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
        <td><a href="{{site.baseurl}}/devops/tools/verify">Verify</a></td>
        <td><a href="{{site.baseurl}}/devops/github/pages/play">Play</a></td>
        <td><a href="{{site.baseurl}}/devops/hacks">Hacks</a></td>
    </tr>
</table>

<style>
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
            <li>Types of Variables: Integers, Strings, Boolean, Floats, Lists, Dictionaries</li>
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
            <li>Created dictionaries to encapsulate variables</li>
            <li>Learned about number functions to create a simple javascript and python calculator</li>
            <li>Learned about looping through strings to print outputs in python</li>
            <li>Functions that compare different strings with each other, and returning true or false outputs.</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 3 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/33-35hacks';">Unit 3 — Mathematical Expressions
        <div class="dropdown-content">
          <ul>
            <li>Using arithmetic operators (+,-,*,/) to perform calculations</li>
            <li>Learned the code for factorials involving variable creation as well as multiplication and subtraction.</li>
            <li>Learned about the Fibonacci sequence and how to calculate the "n"th digit of Fibonacci sequence</li>
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
            <li>Rational Operators, Logical Operators</li>
            <li>Creating Logic Gate Simulator in both Python and Java</li>
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
            <li>Go over If Statements, Else Statements, Javascript and Python Examples.</li>
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
            <li>Endless/Infinite loop. When Condition is not met then loop continues infinitely</li>
            <li>Common operations: iterating over rows and columns.</li>
            <li>Using exceptions with loops</li>
          </ul>
        </div>
      </div>
    </div>
    <!-- Dropdown for Unit 10 -->
    <div class="link-container">
      <div class="dropdown" onclick="window.location.href='/TEST_2025/310hacks';">Unit 10 — Lists
        <div class="dropdown-content">
          <ul>
            <li>Learning how storage and manipulation of data is performed using indexing and lists.</li>
            <li>Learned how to: Add values to lists, insert elements to list, append elements to end of lists, remove elements from list, and calculate the length of a list.</li>
            <li>Learned about Pseudocode:</li>
            <li>Variables in pseudocode, number lists, modulus operator (remainder) and control structures.</li>
            <li>Practiced using iterations in functions.</li>
          </ul>
        </div>
      </div>
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

<h1>Welcome to the Number Guessing Game!</h1>
<p>Try to guess the secret number between 1 and 100.</p>
<input type="number" id="guessInput" placeholder="Enter your guess" />
<button onclick="makeGuess()">Guess</button>

<div id="result"></div>
<div id="guessedNumbers"></div>

<script>
    // Variables
    let secretNumber = Math.floor(Math.random() * 100) + 1; // Random number between 1 and 100
    const maxAttempts = 7; // Maximum attempts allowed
    let attempts = 0; // Count of attempts
    const guessedNumbers = []; // Array to keep track of guessed numbers

    // Function to make a guess
    function makeGuess() {
        const guessInput = document.getElementById('guessInput');
        const resultDiv = document.getElementById('result');
        const guessedNumbersDiv = document.getElementById('guessedNumbers');

        let guess = parseInt(guessInput.value); // Convert input to an integer

        // Check if the input is a valid number
        if (isNaN(guess) || guess < 1 || guess > 100) {
            resultDiv.textContent = "Please enter a valid number between 1 and 100.";
            return;
        }

        guessedNumbers.push(guess); // Add guess to the array
        attempts++; // Increment attempt count

        // Check the guess
        if (guess < secretNumber) {
            resultDiv.textContent = "Too low! Try again.";
        } else if (guess > secretNumber) {
            resultDiv.textContent = "Too high! Try again.";
        } else {
            resultDiv.textContent = `Congratulations! You guessed the number ${secretNumber} in ${attempts} attempts.`;
            return; // Stop further guesses
        }

        // Check if maximum attempts reached
        if (attempts >= maxAttempts) {
            resultDiv.textContent = `Sorry! You've used all your attempts. The secret number was ${secretNumber}.`;
            return; // Stop further guesses
        }

        // Display guessed numbers
        guessedNumbersDiv.textContent = `Guessed numbers: ${guessedNumbers.join(", ")}`;
        guessInput.value = ""; // Clear input field
    }
</script>

</body>
</html>

