# Fancy Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Fancy** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **Demo Code (text-highlighter-scroll-demo.tsx)**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **Component Source Code (letter-3d-swap.tsx)**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Letter3DSwapProps**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-demo.tsx)**: Spring values: Stiffness 200, Damping 21. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (vertical-cut-reveal.tsx)**: Spring values: Stiffness 190, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-line-demo.tsx)**: Spring values: Stiffness 250, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-word-demo.tsx)**: Spring values: Stiffness 250, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-stagger-demo.tsx)**: Spring values: Stiffness 200, Damping 21. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-letter-random-demo.tsx)**: Spring values: Stiffness 200, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (vertical-cut-reveal-scroll-demo.tsx)**: Spring values: Stiffness 200, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (text-rotate-demo.tsx)**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (text-rotate.tsx)**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (text-rotate-multiline-demo.tsx)**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (text-rotate-stagger-demo.tsx)**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (text-rotate-step-demo.tsx)**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **TextRotateProps**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (scroll-and-swap-text.tsx)**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (underline-to-background.tsx)**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (box-carousel.tsx)**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Drag Interaction**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **BoxCarousel Props**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (elastic-line-demo.tsx)**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (elastic-line.tsx)**: Spring values: Stiffness 300, Damping 5. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (gravity-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (gravity.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **MatterBody component**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (gravity-non-draggable-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (gravity-body-types-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (gravity-svg-bodies-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **MatterBody**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (cursor-attractor-and-gravity-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (cursor-attractor-and-gravity.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (cursor-attractor-and-gravity-image-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (cursor-attractor-and-gravity-svg-demo.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (css-box.tsx)**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (simple-marquee-demo.tsx)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (simple-marquee.tsx)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (simple-marquee-drag-demo.tsx)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code (simple-marquee-3d-demo.tsx)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Source Code (marquee-along-svg-path.tsx)**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Alternative: D3-based Path Scaling**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.