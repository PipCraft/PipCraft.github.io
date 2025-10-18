---
layout: default
title: Click My Head!
permalink: /game/
---

<h2 style="color: #FFDDDD;">Click My Head! 🤯</h2>
<p style="color: #FFEEEE;">Can you click my floating head? Go on, try!</p>

<div id="game-container">
  <img src="/assets/images/pip.jpg" alt="My floating head" id="floating-head">
</div>

<div id="win-message">
  <h2 style="color: #CCFFCC;">You got me! You win! 🏆</h2>
  <button id="reset-button">Play Again?</button>
</div>


<style>
  body {
    background-color: #330000; /* Dark red background for the whole page */
  }

  #game-container {
    /* This is the "stage" for your game */
    width: 100%;
    height: 60vh; /* 60% of the viewport height */
    position: relative; /* Crucial for positioning the head inside it */
    border: 3px dashed #663333; /* Lighter red dashed border */
    background-color: #440000; /* Slightly lighter dark red for the game area */
    overflow: hidden; /* Prevents head from floating outside */
    box-sizing: border-box;
  }

  #floating-head {
    /* This is your head! */
    position: absolute; /* Allows it to be moved with 'top' and 'left' */
    width: 100px;
    height: 100px;
    border-radius: 50%; /* Makes it a circle */
    cursor: pointer;
    border: 4px solid #A00000; /* A noticeable red border */
    
    /* This is the magic! Makes the movement smooth. */
    transition: top 0.8s ease-in-out, left 0.8s ease-in-out;
  }

  #floating-head.caught {
    /* Style when clicked */
    border-color: #FFBB00; /* Gold/Orange color when caught */
    transform: scale(1.1);
  }

  #win-message {
    /* This is hidden until you win */
    display: none;
    text-align: center;
    margin-top: 20px;
    color: #CCFFCC; /* Greenish color for win message */
  }

  #reset-button {
    font-size: 1em;
    padding: 10px 20px;
    cursor: pointer;
    background-color: #A00000; /* Red button */
    color: #FFFFFF; /* White text */
    border: 2px solid #FFDDDD;
    border-radius: 5px;
  }
</style>


<script>
  // Wait until the whole page is loaded before running the game
  document.addEventListener("DOMContentLoaded", function() {

    // Get all the elements we need
    const head = document.getElementById("floating-head");
    const gameArea = document.getElementById("game-container");
    const winMessage = document.getElementById("win-message");
    const resetButton = document.getElementById("reset-button");

    let moveInterval; // This will hold our game loop timer

    // Function to move the head to a new random position
    function moveHead() {
      // Get the boundaries of the game area
      const areaWidth = gameArea.clientWidth;
      const areaHeight = gameArea.clientHeight;

      // Get the size of the head
      const headWidth = head.clientWidth;
      const headHeight = head.clientHeight;

      // Calculate a random position
      // We subtract the head's size so it doesn't go off-screen
      const newX = Math.floor(Math.random() * (areaWidth - headWidth));
      const newY = Math.floor(Math.random() * (areaHeight - headHeight));

      // Apply the new position
      head.style.left = newX + "px";
      head.style.top = newY + "px";
    }

    // Function to start the game
    function startGame() {
      winMessage.style.display = "none"; // Hide win message
      head.classList.remove("caught"); // Remove 'caught' style
      head.style.cursor = "pointer";
      
      // Move the head immediately, then keep moving it every 1.5 seconds
      moveHead();
      moveInterval = setInterval(moveHead, 1500); // 1500ms = 1.5 seconds
    }

    // --- Event Listeners ---

    // 1. When you click the head
    head.addEventListener("click", function() {
      // You win!
      clearInterval(moveInterval); // Stop the head from moving
      winMessage.style.display = "block"; // Show the "You win!" message
      head.classList.add("caught"); // Add the "caught" style
      head.style.cursor = "default";
    });

    // 2. When you click the "Play Again?" button
    resetButton.addEventListener("click", function() {
      startGame();
    });

    // --- Start the game for the first time ---
    startGame();

  });
</script>
