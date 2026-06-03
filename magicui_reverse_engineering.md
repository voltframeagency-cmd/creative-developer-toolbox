# Magicui Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Magicui** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **Component Implementation (`retro-grid.tsx`)**: Shader uniforms: u_container_size, u_viewport_size, u_line_color, u_angle. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **Component Implementation (`hero-video-dialog.tsx`)**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`animated-list.tsx`)**: Spring values: Stiffness 350, Damping 40. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`dock.tsx`)**: Spring values: Stiffness 150, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`globe.tsx`)**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`smooth-cursor.tsx`)**: Spring values: Stiffness 400, Damping 45. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Default Spring Configuration**: Spring values: Stiffness 400, Damping 45. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (`border-beam-demo-4.tsx`)**: Spring values: Stiffness 60, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`magic-card.tsx`)**: Spring values: Stiffness 250, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`text-animate.tsx`)**: Spring values: Stiffness 300, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (`text-animate-demo-9.tsx`)**: Spring values: Stiffness 200, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`number-ticker.tsx`)**: Spring values: Stiffness 100, Damping 60. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`scroll-based-velocity.tsx`)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (`text-3d-flip-demo.tsx`)**: Spring values: Stiffness 160, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`text-3d-flip.tsx`)**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (`text-3d-flip-demo-2.tsx`)**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Implementation (`shiny-button.tsx`)**: Spring values: Stiffness 20, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.