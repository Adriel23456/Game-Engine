# 2D Game Engine Using A SFMLCmakeSetup

A custom, lightweight C++ game engine designed for efficient 2D game development with advanced rendering and physics capabilities.

## Overview

This 2D Game Engine is a modular C++ framework developed to provide game developers with a powerful yet accessible toolset for creating 2D games. Built from the ground up with performance in mind, the engine features an optimized rendering pipeline, realistic physics simulation, and sophisticated memory management techniques to ensure smooth gameplay even with limited resources.

## Architecture

The engine is built on a modular architecture that separates core functionalities into independent, interconnected systems:

### Core Systems

- **Rendering Pipeline**: Optimized 2D rendering with support for sprites, animations, particle systems, and custom shaders
- **Physics Engine**: Real-time collision detection and resolution with configurable material properties
- **Memory Manager**: Custom allocation strategies for efficient resource handling and reduced fragmentation
- **Asset Management**: Streamlined loading, caching, and unloading of game resources
- **Input System**: Flexible input handling supporting keyboard, mouse, and gamepad devices
- **Audio Engine**: Spatial audio system with dynamic mixing capabilities
- **Scene Graph**: Hierarchical object management with component-based design

## Features

- Lightweight core with minimal external dependencies
- Hardware-accelerated 2D rendering
- Robust physics simulation
- Entity-component-system (ECS) architecture
- Event-driven messaging system
- Cross-platform compatibility (Windows primary focus)
- Comprehensive debugging tools
- Hot-reloading of assets
- Editor tools for level design and asset management
- Single executable deployment

## Installation

### Prerequisites

- C++17 compatible compiler
- CMake 3.15+
- DirectX 11 SDK (for Windows)
- Git

### Building from Source

```bash
# Clone the repository
git clone https://github.com/username/2d-game-engine.git
cd 2d-game-engine

# Create build directory
mkdir build && cd build

# Configure and build
cmake ..
cmake --build . --config Release

# The executable will be generated in the bin folder
```

## Usage

### Creating a New Game

```cpp
#include "Engine.h"

class MyGame : public Engine::Game {
public:
    bool Initialize() override {
        // Game initialization code
        return true;
    }
    
    void Update(float deltaTime) override {
        // Game update logic
    }
    
    void Render() override {
        // Custom rendering
    }
};

int main() {
    MyGame game;
    Engine::Run(&game, 800, 600, "My 2D Game");
    return 0;
}
```

### Deployment

After building your game, the `deploy` script will create a standalone folder with the game executable and all necessary resources:

```bash
./scripts/deploy.sh MyGame
```

This will create a `MyGame` folder containing:
- `MyGame.exe` - The game executable
- `assets/` - Game assets (textures, sounds, etc.)
- `config/` - Configuration files
- Any required DLLs or dependencies

## Project Structure

```
2d-game-engine/
├── src/
│   ├── core/
│   │   ├── memory/
│   │   ├── math/
│   │   └── debug/
│   ├── renderer/
│   ├── physics/
│   ├── audio/
│   ├── input/
│   └── systems/
├── include/
│   └── public API headers
├── examples/
│   ├── basic/
│   └── advanced/
├── tools/
│   ├── editor/
│   └── assetpipeline/
├── tests/
├── docs/
└── scripts/
    └── deploy.sh
```

## Development Roadmap

- [x] Core engine architecture
- [x] Basic rendering pipeline
- [x] Physics simulation framework
- [x] Memory management system
- [ ] Complete audio implementation
- [ ] Particle system enhancements
- [ ] Editor UI improvements
- [ ] Networking capabilities
- [ ] Mobile platform support
- [ ] Documentation and tutorials

## Performance Optimizations

- Custom memory allocators reduce fragmentation and overhead
- Batch rendering minimizes draw calls
- Spatial partitioning accelerates physics calculations
- Asset streaming prevents memory spikes
- Multi-threading for resource loading and physics calculations

## Contributing

Contributions are welcome! Please read the [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct and the process for submitting pull requests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Special thanks to all contributors and testers
- Inspired by modern game engine architectures and best practices in C++ development