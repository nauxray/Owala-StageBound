# StageBound

**StageBound** is a Windows 2D puzzle-platformer built on **Owala**, a custom C++20 game engine and level editor. It was developed by Team Owala at Singapore Institute of Technology and DigiPen Institute of Technology from September 2025 to April 2026.

Play as Eli, trapped in a theatre full of enemies, traps, and shifting platforms. Rotate the stage 90° at a time to send platforms sliding or falling. Clear a path to the exit portal, avoid enemies, or drop a platform on them. Platforms move along different axes, so the direction you rotate changes what moves and which routes open up.

## Controls

| Key | Action |
| --- | --- |
| A / D | Move left / right |
| W / Space | Jump |
| Q / E | Rotate the stage 90° left / right |
| F | Enter the exit portal |
| F1 | Show FPS |
| F11 | Toggle fullscreen |

## Engine and editor

- **Runtime** — The engine manages entities and components, 2D physics and collision, sprite animation, OpenGL rendering, and FMOD audio.
- **Level editing** — The Dear ImGui editor includes a scene viewport with move, rotate, and scale gizmos, an asset browser, an animation editor, and undo/redo.
- **Tools and data** — RapidJSON handles serialization for scenes and entities. The editor also includes a performance profiler and a build-size analyzer.

See the [Owala editor guide](editorGuide.pdf) for the editing workflow.

## Build and run on Windows

Install **Visual Studio 2022** with the **Desktop development with C++** workload, **CMake 4.1.1**, and **Git**. CMake downloads several dependencies during the first configuration, so that step needs an internet connection. The engine requests an OpenGL 3.3 context.

From the project root, generate the 64-bit Visual Studio solution:

```powershell
cmake -S . -B build -G "Visual Studio 17 2022" -A x64
```

Open `build/owala.sln` in Visual Studio, select one of the following as the startup project, and press **F5**:

| Target | What it launches |
| --- | --- |
| `StageBound` | The standalone game |
| `owala_Engine` | The Owala editor, configured for StageBound by `active_game.cmake` |

The build copies the game assets, data, and FMOD runtime beside each executable.

## Repository layout

| Path | Contents |
| --- | --- |
| [`StageBound/`](StageBound/) | Gameplay source, level data, and game assets |
| [`owala/`](owala/) | Engine runtime and shared systems |
| [`Editor/`](Editor/) | Level editor and development tools |
| [`cmake/`](cmake/) and [`lib/`](lib/) | Build modules and bundled libraries |
| [`Installer/`](Installer/) | Inno Setup configuration and installer resources |

## Team Owala

| Team member | Role |
| --- | --- |
| Anil Sitara | Programmer |
| Jordain Ng Ying Zhe | Tech Lead, Audio Lead |
| Lur Pei Hao, Stanley | Programmer, Audio Lead |
| Jason Lou | Programmer, Designer |
| Ng Jing Wen | Product Manager, Programmer |
| Yar Xuan | Programmer, Designer |
| Cello Tan | Design Lead, Artist |
| Goh Jia Hui | Art Lead |
| Lim Yi Xuan | Artist |
