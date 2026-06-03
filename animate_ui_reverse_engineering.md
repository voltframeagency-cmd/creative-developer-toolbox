# Animate Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Animate** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `registry/components/backgrounds/bubble/index.tsx`**: Spring values: Stiffness 100, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/backgrounds/gravity-stars/index.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/backgrounds/stars/index.tsx`**: Spring values: Stiffness 50, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/management-bar/index.tsx`**: Spring values: Stiffness 200, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/motion-carousel/index.tsx`**: Spring values: Stiffness 240, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/notification-list/index.tsx`**: Spring values: Stiffness 300, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/pin-list/index.tsx`**: Spring values: Stiffness 320, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/radial-intro/index.tsx`**: Spring values: Stiffness 300, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/radial-menu/index.tsx`**: Spring values: Stiffness 420, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/radial-nav/index.tsx`**: Spring values: Stiffness 220, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/user-presence-avatar/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/radix/sidebar/index.tsx`**: Spring values: Stiffness 350, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.