# VertexNova

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-20-blue.svg" alt="C++ Standard"/>
  <img src="https://img.shields.io/badge/platforms-Windows%20%7C%20macOS%20%7C%20Linux%20%7C%20iOS%20%7C%20Android%20%7C%20Web-lightgrey.svg" alt="Platforms"/>
  <img src="https://img.shields.io/badge/license-Apache%202.0-green.svg" alt="License"/>
</p>

VertexNova is a modular, cross-platform C++ graphics and visualization stack designed for learning, clarity, and long-term maintainability.  
This organization hosts the core libraries that power the VertexNova engine and related tooling.

## Repositories

Core modules (names may evolve as the project grows):

| Repository | Description | Status |
|------------|-------------|--------|
| **[vnecommon](https://github.com/vertexnova/vnecommon)** | Shared types, macros, core definitions | ✅ Available |
| **[vnelogging](https://github.com/vertexnova/vnelogging)** | Logging framework and sinks | ✅ Available |
| **[vnemath](https://github.com/vertexnova/vnemath)** | Math types and operations (vectors, matrices, transforms) | 🚧 In Progress |
| **[vnecmake](https://github.com/vertexnova/vnecmake)** | Shared CMake modules | ✅ Available |
| **vneutils** | Utility helpers (files, strings, timing, etc.) | 📋 Planned |
| **vnecrosswindow** | Cross-platform windowing and input abstraction | 📋 Planned |
| **vnecrossgl** | Cross-graphics API abstraction (OpenGL / Vulkan / Metal) | 📋 Planned |

## Architecture

```
┌─────────────────────────────────────────────────────────┐
│                     Application                          │
├─────────────────────────────────────────────────────────┤
│   vnecrossgl (Rendering)  │  vnecrosswindow (Platform)  │
├───────────────────────────┴─────────────────────────────┤
│              vnemath  │  vneutils  │  vnelogging        │
├─────────────────────────────────────────────────────────┤
│                      vnecommon                           │
└─────────────────────────────────────────────────────────┘
```

**Dependency Flow:**
- `vnecommon` → used by all libraries
- `vnemath` + `vneutils` → foundation layer
- `vnecrosswindow` → platform I/O abstraction
- `vnecrossgl` → rendering backend abstraction

## Goals

- **Modular design**: each library can be built and tested independently
- **Cross-platform support**: Windows, macOS, Linux, iOS, Android, and Web (as applicable)
- **Multi-backend rendering**: consistent API across multiple graphics backends
- **Developer friendly**: clean architecture, readable code, strong CI and testing

## Getting Started

Most repositories follow a similar build pattern:

```bash
git clone --recursive https://github.com/vertexnova/<repo>.git
cd <repo>
cmake -S . -B build -DBUILD_TESTS=ON
cmake --build build -j
ctest --test-dir build
```

See each repository's README for module-specific requirements, examples, and integration notes.

## Status

VertexNova is under active development. APIs and repository boundaries may change as the architecture stabilizes.

## Contributing

Contributions are welcome once the public API and contribution workflow are finalized.  
For now, please open an issue to discuss proposals, bugs, or feature requests.

## License

See individual repositories for license information. Most use Apache License 2.0.
