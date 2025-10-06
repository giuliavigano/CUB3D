# 🎯 CUB3D - Raycasting Engine

<div align="center">

![CUB3D](https://img.shields.io/badge/CUB3D-Raycasting%20Engine-blue)
![Language](https://img.shields.io/badge/Language-C-orange)
![Graphics](https://img.shields.io/badge/Graphics-MiniLibX-green)

*A 3D rendering engine based on raycasting, inspired by Wolfenstein 3D*

</div>

## 🎯 What is CUB3D?

**CUB3D** is a 3D rendering engine that implements **raycasting** to create a pseudo-3D environment from a 2D map. Inspired by classic FPS games like Wolfenstein 3D, it demonstrates fundamental computer graphics concepts by casting rays from the player's position to render walls with textures in real-time.

**Key Features:**
- ✨ Real-time raycasting rendering
- 🎨 Textured walls, floors, and ceilings  
- 🎮 Smooth WASD movement and mouse look
- 🗺️ 2D map converted to 3D perspective

## 🚀 Installation and Compilation

### 📋 Prerequisites

Make sure you have installed:
- **GCC** (GNU Compiler Collection)
- **Make** 
- **X11** development libraries
- **XExt** development libraries

On Ubuntu/Debian:
```bash
sudo apt-get update
sudo apt-get install gcc make xorg libxext-dev libbsd-dev
```

### 🔨 Compilation Process

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd CUB3D
   ```

2. **Compile the project:**
   ```bash
   make
   ```

3. **Run the program:**
   ```bash
   ./cub3d
   ```

### 🧹 Makefile Commands

| Command | Description |
|---------|------------|
| `make` | Compiles the entire project |
| `make clean` | Removes object files |
| `make fclean` | Removes all generated files |
| `make re` | Completely recompiles the project |

## 🎮 Controls

| Key | Action |
|-----|--------|
| **W/S** | Move forward/backward |
| **A/D** | Strafe left/right |
| **← →** | Rotate camera |
| **ESC** | Exit |

## 🎨 How Raycasting Works

**Raycasting** creates a 3D perspective by casting rays from the player's position for each pixel column on screen:

```
Player Position → Cast Ray → Hit Wall → Calculate Distance → Draw Vertical Line
```

### 🔑 Key Concepts

**1. DDA Algorithm (Digital Differential Analyzer)**
- Steps through the 2D map grid
- Finds the first wall intersection for each ray
- Determines which side of the wall was hit

**2. Perspective Projection** 
```
Wall Height = Screen Height / Perpendicular Distance
```

**3. Texture Mapping**
- Maps wall textures based on hit position
- Applies floor/ceiling textures using distance

### 🧮 Core Mathematics
- **Vector operations** for ray direction calculation
- **Trigonometry** for rotation and movement
- **Linear interpolation** for smooth texture sampling

## 🖼️ Visual Result

The engine transforms a 2D map into a 3D first-person view:

```
2D Map View          →          3D Rendered View
┌─────────────┐                 ┌─────────────┐
│ 1 1 1 1 1 1 │                 │ ░░░░ ▓▓▓▓▓  │
│ 1 0 0 0 0 1 │       ===>      │ ░██░ ▓▓▓▓▓  │
│ 1 0 P 0 0 1 │                 │ ░██░       │
│ 1 0 0 0 0 1 │                 │ ░██░       │
│ 1 1 1 1 1 1 │                 │ ████████████ │
└─────────────┘                 └─────────────┘
```

**Features:**
- Textured walls with proper perspective
- Floor and ceiling rendering
- Smooth movement and rotation
- Real-time 60 FPS rendering

---

<div align="center">

### 🎓 42 School Project

*Demonstrates mastery of computer graphics, mathematics, and C programming*

</div>
