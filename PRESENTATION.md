#  Pong Game — Open Source Project Presentation

##  Overview

**Repository**: [jeremiahtorralba/PongGame](https://github.com/jeremiahtorralba/PongGame)  
**Language**: C++  
**Library**: SDL2 (Simple DirectMedia Layer 2)  
**Category**: Game Development, 2D Graphics  

This project is a modern recreation of the classic **Pong** arcade game using the **SDL2** graphics library in C++. It showcases real-time 2D rendering, basic collision detection, keyboard event handling, and object-oriented programming principles.

---
##  Objectives

- Understand the use of SDL2 in real-time 2D game development.
- Learn the structure of a game engine using C++.
- Analyze event handling, rendering, collision detection, and object-oriented design.
- Explore areas for improvement and possible contributions.

---

##  Architecture & Components (Breadth-wise Understanding)

The Pong Game is built using a clean class-based approach centered around a `GameEngine` class that handles all core functionality: window creation, game loop, object logic, and rendering.

###  File Breakdown
##  File: `gameengine.cpp`

### Description:
This file implements the `GameEngine` class, which is the **core controller** of the game. It is responsible for initializing SDL, handling the game loop, managing game objects (like paddles and ball), processing input, updating game state, rendering graphics, and cleaning up resources on exit.

### Key Responsibilities:
- SDL and TTF initialization.
- Creating and managing the main SDL window and renderer.
- Loading fonts and textures.
- Managing game objects (`Ball`, `Paddle`, `AIPaddle`).
- Handling the main game loop: input → update → render.
- Detecting collisions and updating scores.
- Singleton pattern to ensure one instance of the engine.

---

##  File: `source.cpp`

### Description:
This is the **entry point** of the application. It contains the `main()` function and is responsible for bootstrapping the game by calling the `GameEngine`.

### Key Responsibilities:
- Calls `GameEngine::getInstance()->Run()` to start the game.
- Handles any preliminary setup or shutdown logic if needed.

---

##  File: `sprite.cpp`

### Description:
This file contains the implementation of the `Sprite` class, which serves as the **base class** for drawable game entities like paddles and the ball.

### Key Responsibilities:
- Handles the loading of textures from image files or rendering text.
- Stores and manages texture data and position.
- Provides a `Draw()` method to render the sprite using SDL.

### Used By:
- `Paddle`, `AIPaddle`, and `Ball` classes inherit from `Sprite`.

---

##  File: `README.md`

### Description:
This file contains **screenshots** for the Pong game project. It helps users understand what the project outlook is and how is the game played.

##  Game Loop Flow

1. **Initialize SDL & Create Window**
2. **Start Loop**:
   - Process SDL events (keyboard input)
   - Update game objects (ball, paddle positions)
   - Check for collisions
   - Render updated game state
3. **Repeat until exit event**

---

##   Analysis

### A. **Approaches Taken**

- Procedural and Object-Oriented mix (functions and classes used together).
- SDL2 library handles all rendering, input, and timing.
- Custom physics for ball speed, direction, and bounce logic.
- Clear game boundaries and scoring system based on ball crossing paddles.

### B. **Key Data Structures**

- **Classes/Structs**:
  - `Paddle`: Holds position and movement methods.
  - `Ball`: Contains direction vector, speed, and reset logic.
- **Primitive Types**:
  - `int`, `float` for positions, velocities.
  - `SDL_Rect`: SDL’s structure for rendering rectangles.
- **Enums / Flags**:
  - Used to define states like movement direction.

### C. **Tradeoffs Made**

| Choice | Tradeoff |
|--------|----------|
| No AI | Keeps logic simple for 2-player mode |
| Fixed screen resolution | Easier rendering but not scalable |
| No time-based movement | Game speed tied to frame rate |

---

##  Understanding SDL2 in the Project

| SDL2 Feature | Usage |
|--------------|-------|
| `SDL_CreateWindow` | Initializes window for rendering |
| `SDL_Renderer` | Renders paddle, ball, background |
| `SDL_Event` | Handles keyboard input (W/S and Up/Down keys) |
| `SDL_Delay` | Simple method for frame rate control |
| `SDL_Quit` | Cleans up resources |

---
##  Scope for Contribution

This project offers multiple areas to contribute:

###  Enhancement Ideas
- Add AI opponent for single-player mode.
- Improve physics with acceleration and spin.
- Add a main menu and difficulty selection.
- Integrate score display using `SDL_ttf`.
- Add background music and sound effects with `SDL_mixer`.
- Frame-rate independent movement using delta time.

---


##  Submission Info

- **Team Members**:  
  - Farzan Bhalara - 202301248

  **Final Repo Fork**:  https://github.com/202301248/PongGame 


