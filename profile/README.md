<p align="center">
  <img src="icons/vertexnova_logo_medallion_with_text.svg" alt="VertexNova" width="320"/>
</p>

<p align="center">
  <strong>A modular C++20 game and graphics engine, layered from the operating system and GPU drivers to the application.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-20-blue.svg" alt="C++ Standard"/>
  <img src="https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20iOS%20%7C%20Android%20%7C%20Web-lightgrey.svg" alt="Platforms"/>
  <img src="https://img.shields.io/badge/license-Apache%202.0-green.svg" alt="License"/>
</p>

<p align="center">
  <a href="https://learnvertexnova.com">Website</a>
  ·
  <a href="https://vertexnova.github.io">vnerhi WebGPU samples</a>
</p>

VertexNova is a cross-platform engine built as independent libraries: one concern per repository, a shared CMake convention, and a single render-hardware interface over Vulkan, Metal, and WebGPU.

This organization hosts those libraries. Public modules are meant to be cloned, read, and built. The renderer and RHI stay private while their APIs stabilize.

## Architecture

<p align="center">
  <img src="diagrams/architecture.svg" alt="VertexNova game engine architecture: stacked layers from operating system and GPU drivers to the application" width="100%"/>
</p>

<p align="center">
  <em> Orange is private (<code>vnerhi</code>, <code>vnegfx</code>). Dotted is future work (<code>vnerobot</code>, <code>vneai</code>, <code>vnexr</code>).</em>
</p>

## Showcase

Silent 1080p reel of `vnegfx` samples on iOS (Metal) plus desktop stills: volume, slice, CSG, OIT, mesh picking.  
Run the `vnerhi` WebGPU demos in the browser at [vertexnova.github.io](https://vertexnova.github.io). Docs and site: [learnvertexnova.com](https://learnvertexnova.com).

<p align="center">
  <a href="showcase/vertexnova-showcase.mp4">Watch vertexnova-showcase.mp4</a> (44s)
</p>

<p align="center">
  <img src="showcase/stills/01-volume-isosurface.png" alt="Volume isosurface" width="32%"/>
  <img src="showcase/stills/02-volume-dvr.png" alt="Volume DVR" width="32%"/>
  <img src="showcase/stills/03-volume-slicer.png" alt="Volume slicer" width="32%"/>
</p>
<p align="center">
  <img src="showcase/stills/04-csg-dragon.png" alt="Mixed CSG" width="32%"/>
  <img src="showcase/stills/05-oit-engine.png" alt="A-buffer OIT" width="32%"/>
  <img src="showcase/stills/06-mesh-picking.png" alt="Mesh picking" width="32%"/>
</p>

## Explore the public stack

`vnerhi` (RHI) and `vnegfx` (renderer) are private. The modules around them are public and follow the same C++20 / CMake layout.

| Layer | Repository | Role |
|-------|------------|------|
| Visualization | [vnescene](https://github.com/vertexnova/vnescene) | Cameras, lights, and GPU-friendly scene state |
| Visualization | [vneinteraction](https://github.com/vertexnova/vneinteraction) | Camera manipulators and input-to-motion controllers |
| Visualization | [vneio](https://github.com/vertexnova/vneio) | Mesh, image, volume, and DICOM I/O |
| Visualization | [vneshaderc](https://github.com/vertexnova/vneshaderc) | Offline GLSL to SPIR-V / MSL / WGSL / HLSL |
| Platform | [vnewindow](https://github.com/vertexnova/vnewindow) | Native windows (Win32, Cocoa, X11, Wayland, UIKit, Android, Web) |
| Platform | [vneevents](https://github.com/vertexnova/vneevents) | Keyboard, mouse, touch, and window events |
| Core | [vnemath](https://github.com/vertexnova/vnemath) | Vectors, matrices, geometry, graphics clip-space helpers |
| Core | [vnelogging](https://github.com/vertexnova/vnelogging) | Synchronous and asynchronous logging |
| Core | [vneutils](https://github.com/vertexnova/vneutils) | CLI parsing and shared helpers |
| Core | [vnecommon](https://github.com/vertexnova/vnecommon) | Platform detection, macros, non-copyable bases |

## Why it is structured this way

- **One library per concern** — scene, I/O, windowing, math, and logging can be learned and tested on their own.
- **GPU backends behind an RHI** — application code does not talk to Vulkan, Metal, or WebGPU directly.
- **Independent CI** — each repository configures, builds, and tests with the same CMake pattern.

## Build a public library

```bash
git clone --recursive https://github.com/vertexnova/<repo>.git
cd <repo>
cmake -S . -B build -DBUILD_TESTS=ON
cmake --build build -j
ctest --test-dir build
```

See each repository README for module-specific options, samples, and integration notes.

## Status

VertexNova is under active development. The public modules above are the stable entry points. `vnerobot`, `vneai`, and `vnexr` are planned and not part of the current public surface.

## Contributing

Contributions are welcome once the public API and contribution workflow are finalized.  
For now, please open an issue to discuss proposals, bugs, or feature requests.

## License

See individual repositories for license information. Most use Apache License 2.0.
