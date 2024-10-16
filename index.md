---
layout: base
title: Student Home 
description: Home Page
author: Keerthan Karumudi
hide: true
comments: true
---

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


# Welcome to the Fun Number Guessing Game
```python

<div style="text-align: center;">
    <h2>How to Play</h2>
    <ul style="list-style-type: none;">
        <li>1. The program will generate a random number between 1 and 50.</li>
        <li>2. You will be prompted to guess the number.</li>
        <li>3. The game will give feedback: whether your guess is too high, too low, or correct.</li>
        <li>4. You have 5 chances to guess the number correctly. If not, the game ends, and the correct number is revealed.</li>
    </ul>
</div>
import random

# Function for the guessing game
def play_guessing_game():
    number_to_guess = random.randint(1, 50)
    guesses = []
    attempts = 5
    while attempts > 0:
        try:
            guess = int(input("Guess a number between 1 and 50: "))
            guesses.append(guess)
            if guess == number_to_guess:
                print(f"Congratulations! You guessed the number {number_to_guess} correctly!")
                break
            elif guess < number_to_guess:
                print("Your guess is too low.")
            else:
                print("Your guess is too high.")
            attempts -= 1
            if attempts > 0:
                print(f"You have {attempts} attempts left.")
            else:
                print(f"Game over! The correct number was {number_to_guess}.")
        except ValueError:
            print("Please enter a valid number.")
    print(f"Your guesses: {guesses}")

# Main loop
while True:
    play_game = input("Do you want to play the number guessing game? (yes/no): ").lower()
    if play_game == "yes":
        play_guessing_game()
    elif play_game == "no":
        print("Thanks for playing! Goodbye.")
        break
    else:
        print("Please answer with 'yes' or 'no'.")
