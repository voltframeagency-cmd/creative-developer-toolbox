# Odysseyui Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Odysseyui** library.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `registry/primitives/effects/auto-height/index.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/avatar-group/index.tsx`**: Spring values: Stiffness 300, Damping 17. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/alert-dialog/index.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/dialog/index.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/menu/index.tsx`**: Spring values: Stiffness 350, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/popover/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/preview-card/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/progress/index.tsx`**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/radio/index.tsx`**: Spring values: Stiffness 200, Damping 16. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/switch/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/toggle-group/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/tooltip/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/blur/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/buttons/flip/index.tsx`**: Spring values: Stiffness 280, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/texts/counting-number/index.tsx`**: Spring values: Stiffness 90, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/cursor/index.tsx`**: Spring values: Stiffness 500, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/effect/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/fade/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/headless/dialog/index.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/headless/popover/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/headless/switch/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/highlight/index.tsx`**: Spring values: Stiffness 350, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/hover-card/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/image-zoom/index.tsx`**: Spring values: Stiffness 200, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/magnetic/index.tsx`**: Spring values: Stiffness 100, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/icons/menu/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/ai/model-selector/index.tsx`**: Spring values: Stiffness 350, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/texts/morphing/index.tsx`**: Spring values: Stiffness 125, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/community/notification-list/index.tsx`**: Spring values: Stiffness 300, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/pinned-list/index.tsx`**: Spring values: Stiffness 320, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/pricings/pricing-1/index.tsx`**: Spring values: Stiffness 280, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/components/pricings/pricing-4/index.tsx`**: Spring values: Stiffness 280, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/alert-dialog/index.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/dialog/index.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/dropdown-menu/index.tsx`**: Spring values: Stiffness 350, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/popover/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/progress/index.tsx`**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/radio-group/index.tsx`**: Spring values: Stiffness 200, Damping 16. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/sheet/index.tsx`**: Spring values: Stiffness 150, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/switch/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/toggle-group/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/tooltip/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/scroll-progress/index.tsx`**: Spring values: Stiffness 250, Damping 40. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/texts/scrolling-number/index.tsx`**: Spring values: Stiffness 90, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/slide/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/texts/sliding-number/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/spring/index.tsx`**: Spring values: Stiffness 200, Damping 16. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/tabs/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/base/tabs/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/headless/switch/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 300, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/radix/tabs/index.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/tilt/index.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/animate/tooltip/index.tsx`**: Spring values: Stiffness 300, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/primitives/effects/zoom/index.tsx`**: Spring values: Stiffness 200, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **File: `registry/components/animate/card-stroke/index.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `registry/components/animate/footer/index.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `registry/components/preloaders/greetings/index.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.