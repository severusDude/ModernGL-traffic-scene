# ModernGL Traffic Scene

A 3D interactive traffic simulation built with **ModernGL** and **Pygame** for a Computer Graphics final exam (Ujian Akhir Semester — Mata Kuliah Grafika Komputer).

> Forked from [unormiesable/OpenGL_Traffic](https://github.com/unormiesable/OpenGL_Traffic)

---

## Features

- Real-time 3D traffic scene rendered with ModernGL (OpenGL 3.3+)
- Two camera modes: **Fly** and **Orbit**
- Dynamic car spawning and removal per lane (up to 4 lanes)
- Adjustable traffic light timing
- GLSL shader pipeline with texture and point light support
- OBJ model loading via PyWavefront

---

## Project Structure

```
ModernGL-traffic-scene/
├── main.py               # Entry point — window, event loop
├── scene.py              # Scene graph and object management
├── scene_renderer.py     # Render loop and draw calls
├── camera.py             # Fly & orbit camera logic
├── model.py              # Single model loader/renderer
├── comp_model.py         # Composite model (multi-mesh)
├── mesh.py               # Mesh data abstraction
├── vbo.py                # Vertex Buffer Object helpers
├── vao.py                # Vertex Array Object helpers
├── shader_program.py     # GLSL shader compilation & linking
├── texture.py            # Texture loading
├── point_light.py        # Point light uniforms
├── shaders/              # GLSL vertex & fragment shaders
├── objects/              # OBJ 3D model files
├── textures/             # Texture image files
└── images/               # Screenshots / assets
```

---

## Requirements

| Package     | Version                        |
| ----------- | ------------------------------ |
| Python      | ≥ 3.11 (see `.python-version`) |
| moderngl    | 5.12.0                         |
| glcontext   | 3.0.0                          |
| pygame      | 2.6.1                          |
| numpy       | 2.2.5                          |
| pyglm       | 2.8.0                          |
| PyWavefront | 1.3.3                          |

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/severusDude/ModernGL-traffic-scene.git
cd ModernGL-traffic-scene
```

### 2. Create a virtual environment

**Windows:**
```bash
python -m venv venv
venv\Scripts\activate
```

**Linux / macOS:**
```bash
python -m venv venv
source venv/bin/activate
```

> Alternatively, if you use [uv](https://github.com/astral-sh/uv), a `uv.lock` is already included:
> ```bash
> uv sync
> ```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the program

```bash
python main.py
```

---

## Controls

### General

| Key                 | Action                           |
| ------------------- | -------------------------------- |
| `` ` `` (Backquote) | Toggle cursor visibility         |
| `TAB`               | Switch camera mode (Fly ↔ Orbit) |

### Camera — Fly Mode *(default)*

| Key / Input | Action        |
| ----------- | ------------- |
| `W`         | Move forward  |
| `S`         | Move backward |
| `A`         | Strafe left   |
| `D`         | Strafe right  |
| `Q`         | Move down     |
| `E`         | Move up       |
| Mouse       | Look around   |
| `SHIFT`     | Move faster   |
| `CTRL`      | Move slower   |

> Movement is relative to the camera's local coordinate system.

### Camera — Orbit Mode

| Key / Input | Action                   |
| ----------- | ------------------------ |
| `↑`         | Orbit up                 |
| `↓`         | Orbit down               |
| `←`         | Orbit left               |
| `→`         | Orbit right              |
| Mouse       | Orbit in mouse direction |
| `SHIFT`     | Orbit faster             |
| `CTRL`      | Orbit slower             |

### Scene — Spawn Cars

| Key | Action            |
| --- | ----------------- |
| `1` | Add car to Lane 1 |
| `2` | Add car to Lane 2 |
| `3` | Add car to Lane 3 |
| `4` | Add car to Lane 4 |

### Scene — Remove Cars

| Key | Action                 |
| --- | ---------------------- |
| `6` | Remove car from Lane 1 |
| `7` | Remove car from Lane 2 |
| `8` | Remove car from Lane 3 |
| `9` | Remove car from Lane 4 |

> Each lane starts with **4 cars** (minimum: 4, maximum: 7).

### Traffic Light Timing

| Key | Action             |
| --- | ------------------ |
| `F` | Decrease wait time |
| `G` | Increase wait time |

> Default wait time: **2 units** — range: **0.5 – 5 units**.

---

## Tech Stack

- **[ModernGL](https://moderngl.readthedocs.io/)** — Python OpenGL wrapper
- **[Pygame](https://www.pygame.org/)** — Window management & input handling
- **[PyGLM](https://github.com/Zuzu-Typ/PyGLM)** — OpenGL mathematics (vectors, matrices)
- **[NumPy](https://numpy.org/)** — Array / buffer operations
- **[PyWavefront](https://github.com/greenmoss/PyWavefront)** — OBJ model loading
- **GLSL** — Vertex and fragment shaders

---

## License

This project is for academic purposes. See the upstream repository [unormiesable/OpenGL_Traffic](https://github.com/unormiesable/OpenGL_Traffic) for the original license.