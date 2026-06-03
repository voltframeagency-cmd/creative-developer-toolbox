# Unlumen Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Unlumen** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `registry/components/backgrounds/pixel-liquid-bg/index.tsx`**: Shader uniforms: px, boundarySpace, px, center. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **Demo Code**: Spring values: Stiffness 400, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/animated-list/index.tsx`**: Spring values: Stiffness 350, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/apple-switch/index.tsx`**: Spring values: Stiffness 700, Damping 48. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code**: Spring values: Stiffness 360, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/favicon-search/index.tsx`**: Spring values: Stiffness 400, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/file-tree/index.tsx`**: Spring values: Stiffness 500, Damping 40. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/hover-expand/index.tsx`**: Spring values: Stiffness 280, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/hover-feature-cards/index.tsx`**: Spring values: Stiffness 300, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/motion-faqs-accordion/index.tsx`**: Spring values: Stiffness 280, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/pinned-list/index.tsx`**: Spring values: Stiffness 380, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Demo Code**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/side-by-side-slide/index.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **`Dock` Props**: Spring values: Stiffness 300, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/dock/index.tsx`**: Spring values: Stiffness 400, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/motion-navigation-menu/index.tsx`**: Spring values: Stiffness 400, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/unlumen/sidebar-001/index.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **File: `registry/components/unlumen/horizontal-depth-fade/index.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `registry/components/unlumen/orbital-image-wheel/index.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.