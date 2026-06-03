# Efferd Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Efferd** library.

## 4. Gestures & Animation States
Micro-interactions and gesture mappings are configured via declarative motion states:
* **File: `src/lib/components/ui/floating-paths/floating-paths.svelte`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/auth/2/floating-paths.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/footer/2/footer.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `src/lib/components/efferd/footer/AnimatedContainer.svelte`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/footer/5/sticky-footer.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `src/lib/components/efferd/footer/AnimatedContainer.svelte`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/not-found/2/not-found.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/pricing/1/frequency-toggle.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/pricing/4/pricing-section.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `src/lib/components/efferd/pricing/pricing-four.svelte`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/testimonials/1/testimonials-columns.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.
* **File: `registry/blocks/testimonials/2/testimonials-section.tsx`**: Framer Motion gesture animations. Transitions opacity, translation, and scale properties dynamically.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.