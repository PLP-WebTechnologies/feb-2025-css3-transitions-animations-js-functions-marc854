# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Animations with JavaScript</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <button id="animateButton">Click to Animate</button>
    <div id="animatedBox"></div>
    
    <script src="script.js"></script>
</body>
</html>

/* styles.css */

/* Basic styles for the button and the box */
body {
    font-family: Arial, sans-serif;
    text-align: center;
    padding: 50px;
}

#animateButton {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
    border: none;
    background-color: #4CAF50;
    color: white;
    border-radius: 5px;
    transition: background-color 0.3s ease;
}

#animateButton:hover {
    background-color: #45a049;
}

#animatedBox {
    width: 100px;
    height: 100px;
    margin-top: 20px;
    background-color: #3498db;
    transition: transform 1s, background-color 1s;
}

/* CSS animation for the box */
.animate {
    transform: translateX(300px);
    background-color: #e74c3c;
}

// script.js

// Select elements
const animateButton = document.getElementById('animateButton');
const animatedBox = document.getElementById('animatedBox');

// Check if the user has previously triggered the animation
if (localStorage.getItem('animated') === 'true') {
    animatedBox.classList.add('animate');
    animateButton.disabled = true; // Disable button once animation is triggered
    animateButton.innerText = "Animation Played!";
}

// Function to trigger animation and store preference in localStorage
function triggerAnimation() {
    animatedBox.classList.add('animate');
    localStorage.setItem('animated', 'true'); // Store the animation state
    animateButton.disabled = true; // Disable button
    animateButton.innerText = "Animation Played!";
}

// Add event listener to the button
animateButton.addEventListener('click', triggerAnimation);
