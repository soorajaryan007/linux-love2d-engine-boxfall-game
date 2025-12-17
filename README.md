
````md
## Blockfall 🎮

Blockfall is a simple 2D arcade dodge game built using the **LÖVE (Love2D)** engine.  
The player controls a square that must dodge falling blocks for as long as possible.  
The score increases with survival time.

---

## 🕹️ Gameplay

- Move left and right to dodge falling blocks
- Score increases the longer you survive
- Collision ends the game
- Click **Start / Start Again** to play

---

## 🎮 Controls

| Action | Key / Input |
|-----|-----------|
| Move Left | `A` |
| Move Right | `D` |
| Start / Restart | Mouse Click |

---

## 🛠️ Tech Stack

- **Engine:** LÖVE (Love2D)
- **Language:** Lua
- **Platform:** Linux (Ubuntu tested)

---

## 📦 Installation (Ubuntu)

### 1️⃣ Install LÖVE
```bash
sudo apt update
sudo apt install love -y
````

Verify installation:

```bash
love --version
```

---

### 2️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/blockfall.git
cd blockfall
```

---

### 3️⃣ Run the Game

```bash
love .
```

The game window will open.

---

## 🧱 Project Structure

```
blockfall/
├── main.lua
└── README.md
```

---

## 🧠 Architecture Overview

The game follows a **state-driven architecture**, commonly used in game engines.

### 🔹 Game States

* `start` – Initial screen with Start button
* `play` – Main gameplay loop
* `gameover` – Game over screen with final score

State transitions control game logic and rendering.

---

### 🔹 Core Components

#### Player

* Position-based movement using keyboard input
* Screen boundary constraints
* Axis-aligned bounding box (AABB) collision detection

#### Blocks

* Spawn at random horizontal positions
* Fall vertically with constant speed
* Destroyed when off-screen

#### Score System

* Time-based scoring using delta time (`dt`)
* Frame-rate independent
* Displayed as integer, stored internally as float

---

### 🔹 Game Loop

The engine provides:

* `love.update(dt)` → Handles input, physics, collisions, scoring
* `love.draw()` → Handles rendering
* `love.mousepressed()` → Handles UI interaction

---

## 🎯 Collision Detection

Collision detection uses simple **AABB (Axis-Aligned Bounding Box)** logic:

```lua
function checkCollision(a, b)
    return a.x < b.x + b.size and
           b.x < a.x + a.w and
           a.y < b.y + b.size and
           b.y < a.y + a.h
end
```

---

## 🚀 Future Improvements

* Increasing difficulty over time
* High score persistence
* Sound effects
* Keyboard-based start option
* Mobile or web version

---

## 📜 License

This project is open-source and free to use for learning and experimentation.


