# Solace Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Solace** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `src/registry/blocks/hero-section/one/circular-gallery.tsx`**: Shader uniforms: modelViewMatrix, projectionMatrix, tMap, modelViewMatrix. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `src/registry/blocks/footer-section/one/index.tsx`**: Spring values: Stiffness 260, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/footer-section/social-cloud.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/components/ui/animated-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/blocks/team-section/five/index.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.