# Aliimam Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Aliimam** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `feature-cards.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `stats.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `stats.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `stats.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `stats.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `stats.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `ripple-shader.tsx`**: Shader uniforms: resolution, time, uPixelSize, uSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `attraction.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `render-canvas.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **How to Use**: Spring values: Stiffness 120, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `scroll-progress.tsx`**: Spring values: Stiffness 200, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.