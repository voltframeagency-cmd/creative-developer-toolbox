# Chanhdai Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Chanhdai** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `src/registry/components/elastic-slider/elastic-slider.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/registry/components/fluid-gradient-text/fluid-gradient-text.tsx`**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.