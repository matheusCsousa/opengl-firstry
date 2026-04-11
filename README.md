# OpenGL — First Triangle

First OpenGL project in C++. Renders a subdivided equilateral triangle using a VAO/VBO/EBO pipeline with GLFW, GLAD, and custom GLSL shaders.

Example:

![triangle](https://learnopengl.com/img/getting-started/shaders3.png)

## What it does

Draws a triangle split into 3 inner triangles via an index buffer (EBO), rendered in a flat orange color (`vec4(1.0, 0.5, 0.2, 1.0)`). The vertex positions are calculated mathematically to form an equilateral triangle.

## Dependencies

| Library | Purpose |
|---|---|
| GLFW | Window creation and input |
| GLAD | OpenGL function loader |
| GLM | Math (included, not used yet) |
| stb_image | Image loading (included, not used yet) |

GLFW and GLEW static libraries are bundled in `lib/`. GLAD source is in `src/glad.c`.

## Build

Requires CMake and a C++17 compiler with OpenGL support.

```bash
cmake -B build
cmake --build build
cd build && ./build
```

On Arch/Manjaro, install dependencies:

```bash
sudo pacman -S cmake glfw-x11 mesa
```

## Project Structure

```
.
├── src/
│   ├── main.cpp         # Window setup, vertex data, render loop
│   ├── glad.c           # GLAD OpenGL loader
│   ├── Shader/          # Shader program (compile, link, activate)
│   ├── VAO/             # Vertex Array Object wrapper
│   ├── VBO/             # Vertex Buffer Object wrapper
│   └── EBO/             # Element Buffer Object wrapper
├── Shaders/
│   ├── default.vert     # Passthrough vertex shader (GLSL 330)
│   └── default.frag     # Solid color fragment shader
├── lib/
│   ├── libglfw3.a
│   ├── libGLEW.a
│   └── stb_image/
└── CMakeLists.txt
```
