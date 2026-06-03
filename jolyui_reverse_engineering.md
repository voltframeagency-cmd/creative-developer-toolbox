# Jolyui Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Jolyui** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `ui/ai-prompt-box.tsx`**: Spring values: Stiffness 300, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/animated-toast.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/animated-tooltip.tsx`**: Spring values: Stiffness 500, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/button.tsx`**: Spring values: Stiffness 400, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/date-wheel-picker.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/dock.tsx`**: Spring values: Stiffness 150, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/expanded-map.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/falling-text.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/feedback-widget.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/github-star.tsx`**: Spring values: Stiffness 100, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/magnetic.tsx`**: Spring values: Stiffness 26, Damping 4. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/number-counter.tsx`**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/pricing-01.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/rotate-text.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/scroll-text.tsx`**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/segmented-button.tsx`**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ui/sticky-navbar.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.