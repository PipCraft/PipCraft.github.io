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

<div id="win-overlay">
  <div id="win-content">
    <h2 style="color: #CCFFCC;">You got me! You win! 🏆</h2>
    <button id="reset-button">Play Again?</button>
  </div>
</div>


<style>
  body {
    background-color: #330000;
    margin: 0; /* Remove default body margin */
    font-family: sans-serif; /* A more readable font */
  }

  h2 { font-size: 2rem; margin-bottom: 10px; }
  p { font-size: 1.1rem; margin-top: 0; }

  #game-container {
    width: 100%;
    height: 60vh;
    position: relative;
    border: 3px dashed #663333;
    background-color: #440000;
    overflow: hidden; 
    box-sizing: border-box;
  }

  #floating-head {
    position: absolute;
    width: 100px;
    height: 100px;
    border-radius: 50%;
    cursor: pointer;
    border: 4px solid #A00000;
    transition: top 0.8s ease-in-out, left 0.8s ease-in-out;
    object-fit: cover; /* Ensures image fills the circle without distortion */
  }

  #floating-head.caught {
    border-color: #FFBB00;
    transform: scale(1.1);
  }

  /* NEW: Styles for the full-page win overlay */
  #win-overlay {
    position: fixed; /* Fixed position to cover the whole viewport */
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.85); /* Semi-transparent dark background */
    display: flex; /* Use flexbox for easy centering */
    justify-content: center; /* Center horizontally */
    align-items: center; /* Center vertically */
    z-index: 1000; /* Make sure it's on top of everything else */
    display: none; /* Hidden by default */
    color: #FFFFFF; /* White text for contrast */
    text-align: center;
    backdrop-filter: blur(5px); /* Optional: blur effect for modern browsers */
    -webkit-backdrop-filter: blur(5px); /* Safari compatibility */
  }

  #win-content {
    background-color: #550000; /* Dark red box for the message */
    padding: 30px 40px;
    border-radius: 15px;
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.5);
    max-width: 90%; /* Don't let it get too wide on desktop */
  }

  #win-overlay h2 {
    font-size: 2.5em; /* Larger win text */
    margin-bottom: 20px;
  }

  #reset-button {
    font-size: 1.8em; /* Much larger button for easy tapping */
    padding: 15px 30px;
    cursor: pointer;
    background-color: #A00000;
    color: #FFFFFF;
    border: 2px solid #FFDDDD;
    border-radius: 10px;
    transition: background-color 0.3s ease;
  }

  #reset-button:hover {
    background-color: #CC0000; /* Lighter red on hover */
  }
  
  /* Media Query for Mobile */
  @media (max-width: 768px) {
    #game-container {
      height: 70vh;
    }

    #floating-head {
      width: 120px;
      height: 120px;
    }

    h2 {
      font-size: 1.8rem;
    }

    p {
      font-size: 1rem;
    }

    #win-overlay h2 {
      font-size: 2em; /* Adjust win text size for smaller screens */
    }

    #reset-button {
      font-size: 1.5em; /* Adjust button size for smaller screens */
      padding: 12px 25px;
    }
  }
</style>


<script>
  document.addEventListener("DOMContentLoaded", function() {

    const head = document.getElementById("floating-head");
    const gameArea = document.getElementById("game-container");
    const winOverlay = document.getElementById("win-overlay"); // NEW: Get the overlay
    const resetButton = document.getElementById("reset-button");

    let moveInterval;
    let moveSpeed;

    function moveHead() {
      const areaWidth = gameArea.clientWidth;
      const areaHeight = gameArea.clientHeight;
      const headWidth = head.clientWidth;
      const headHeight = head.clientHeight;
      
      const newX = Math.floor(Math.random() * (areaWidth - headWidth));
      const newY = Math.floor(Math.random() * (areaHeight - headHeight));

      head.style.left = newX + "px";
      head.style.top = newY + "px";
    }

    function startGame() {
      if (window.innerWidth < 768) {
        moveSpeed = 2000; // Slower on mobile (2 seconds)
      } else {
        moveSpeed = 1500; // Original speed on desktop (1.5 seconds)
      }

      winOverlay.style.display = "none"; // UPDATED: Hide the entire overlay
      head.classList.remove("caught");
      head.style.cursor = "pointer";
      
      moveHead();
      moveInterval = setInterval(moveHead, moveSpeed);
    }

    head.addEventListener("click", function() {
      clearInterval(moveInterval);
      winOverlay.style.display = "flex"; // UPDATED: Show the overlay (flex to center content)
      head.classList.add("caught");
      head.style.cursor = "default";
    });

    resetButton.addEventListener("click", function() {
      startGame();
    });

    startGame();
  });
</script>
