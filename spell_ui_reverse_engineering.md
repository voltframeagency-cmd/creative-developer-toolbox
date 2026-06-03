# Spell Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Spell** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `registry/spell-ui/animated-gradient.tsx`**: Shader uniforms: u_time, u_pixelRatio, u_resolution, u_scale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/spell-ui/fallback-avatar.tsx`**: Shader uniforms: R, T. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/spell-ui/light-rays.tsx`**: Shader uniforms: u_resolution, u_mouse, u_time, u_intensity. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `registry/spell-ui/highlighted-text.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.