# Skiper Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Skiper** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `skiper63.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `skiper64.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `skiper61.tsx`**: Spring values: Stiffness 131, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `skiper25.tsx`**: Spring values: Stiffness 300, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `skiper67.tsx`**: Spring values: Stiffness 100, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **File: `skiper39.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `skiper17.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.