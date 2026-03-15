# Snake Game

A browser-based implementation of the classic **Snake game** built using **JavaScript, HTML5 Canvas, and CSS**. The project demonstrates real-time game logic, event-driven input handling, and sprite-based rendering in a lightweight front-end application.

Play the game:  
https://michaelgalloway404.github.io/Snake_Game/

## Overview

This project recreates the classic Snake arcade game where the player controls a growing snake that consumes food while avoiding collisions with walls and itself. The game supports **multiple difficulty levels**, **pause/play controls**, and **score tracking**.

## Key Features

- **Real-time game loop** using `setInterval`
- **Keyboard input handling** for directional movement
- **Dynamic difficulty settings** (Easy, Medium, Hard) affecting game speed
- **Pause and resume functionality**
- **Collision detection** with boundaries and the snake's own body
- **Score tracking and UI rendering**
- **Sprite-based rendering** for snake head, body, tail, and food
- **Randomized food placement** with validation to avoid spawning on the snake

## Technical Highlights

- Grid-based movement system using a fixed **block size**
- Snake movement implemented through **array manipulation** (`unshift` and `pop`)
- **Image preloading** to prevent rendering lag
- Game state management for pause, reset, and difficulty control
- Rendering handled through **HTML5 Canvas API**

## Technologies Used

- JavaScript
- HTML5 Canvas
- CSS

## Author

Michael Galloway  