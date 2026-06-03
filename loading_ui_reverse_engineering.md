# Loading Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Loading** library.

## 4. Gestures & Animation States
Micro-interactions and gesture mappings are configured via declarative motion states:
* **File: `registry/components/loading-ui/analyzing-image.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/bobbing-dots.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/morphing-infinity.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/pulsating-dots.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/spiral.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/text-shimmer-wave.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/components/loading-ui/text-shimmer.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.