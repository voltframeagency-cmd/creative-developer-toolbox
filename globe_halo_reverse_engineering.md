# Globe_halo Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Globe_halo** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **Component Source Code**: Spring values: Stiffness 120, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.