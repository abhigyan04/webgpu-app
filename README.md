# WebGPU Fluid Simulation

This workspace contains a WebGPU-powered stable fluids demo that implements a GPU-based fluid simulation and interactive dye rendering in the browser.

## What has been done

- Built a stable fluids solver using WebGPU compute shaders based on Jos Stam's "Stable Fluids" method.
- Implemented a full compute pipeline with ping-pong textures for velocity, pressure, dye, curl, and divergence.
- Added vorticity confinement to preserve swirling motion and keep the flow visually rich.
- Included interactive mouse-driven splats that inject velocity and dye into the simulation at runtime.
- Structured the demo with a control HUD for adjusting vorticity, pressure iterations, dye fade, and splat size.
- Used WebGPU bind groups, samplers, and multiple dispatch passes to keep the simulation running entirely on the GPU.

## Files

- `fluid-sim.html` - main demo page with the stable fluids simulation and WebGPU setup.
- `index.html` - alternate entry point if present; the primary fluid demo is in `fluid-sim.html`.

## Capabilities

- Real-time fluid simulation in the browser using WebGPU compute.
- Interactive input: drag to inject velocity and dye into the flow.
- Adjustable simulation parameters for visual tuning.
- GPU-accelerated pressure projection and advection for smooth behavior.
- High-resolution dye field with lower-resolution velocity and pressure grids for performance.
- Demonstrates advanced WebGPU concepts like compute passes, texture read/write, ping-pong buffering, and bind group layouts.

## Challenges

- WebGPU setup is more complex than WebGL: acquiring adapters, requesting devices, and handling asynchronous initialization.
- Managing multiple compute passes and `GPUTexture` ping-pong resources requires careful coordination.
- Implementing stable fluid mechanics in shaders means translating mathematical steps into compute dispatches.
- Browser compatibility is still evolving: not every browser or GPU driver supports WebGPU reliably.
- Performance tuning is necessary to balance grid resolution, iteration count, and frame rate.

## Future of WebGPU

- WebGPU is the next-generation browser graphics and compute API, offering more direct access to modern GPU features than WebGL.
- It unlocks browser-based simulations, procedural generation, real-time physics, and machine learning workloads with native GPU acceleration.
- As browser support matures, WebGPU will enable richer interactive applications and cross-platform compute workloads without plugins.
- This demo is a starting point for more advanced fluid rendering, particle systems, GPU-based physics, and visual effects in the browser.

## Usage

1. Open `fluid-sim.html` in a browser with WebGPU support.
2. The canvas renders a fluid field with dye and velocity interaction.
3. Drag on the canvas to inject dye and control the flow.

## Requirements

- A browser with WebGPU enabled (Chrome, Edge, or Safari with WebGPU support).
- A GPU and operating system compatible with WebGPU.

## Notes

This project is intended as a minimal but practical WebGPU demo for experimenting with compute shaders, GPU-driven simulation, and real-time interactive rendering.
