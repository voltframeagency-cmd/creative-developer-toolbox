# Cult Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Cult** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **Demo Code (animated-number-demo.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Component Source Code (animated-number.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Demo Code (pixel-heading-character-demo.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Component Source Code (pixel-heading-character.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Animation Modes**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Show Font Label**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **PixelHeading Props**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **PixelHeadingMode Type**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Available Pixel Fonts**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Component Source Code (shader-lens-blur.tsx)**: Shader uniforms: u_mouse, u_resolution, u_pixelRatio, u_time. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Component Source Code (svg-shapes-animated.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **Component Source Code (svg-shapes.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **Component Source Code (animated-number.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (code-block.tsx)**: Spring values: Stiffness 500, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (dock.tsx)**: Spring values: Stiffness 320, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (dynamic-island.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (expandable-demo.tsx)**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (expandable.tsx)**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (family-button.tsx)**: Spring values: Stiffness 400, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (feature-carousel.tsx)**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (gradient-button-group.tsx)**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (logo-carousel.tsx)**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (morph-surface.tsx)**: Spring values: Stiffness 550, Damping 45. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **With Custom Spring Config**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (neumorph-button.tsx)**: Spring values: Stiffness 400, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (text-animate.tsx)**: Spring values: Stiffness 100, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (three-d-carousel.tsx)**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (youtube-video-player.tsx)**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.