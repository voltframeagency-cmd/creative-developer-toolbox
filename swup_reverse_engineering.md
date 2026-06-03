# Swup Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Swup** library.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **Configuration Example**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **GSAP Integration (with JS Plugin)**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.