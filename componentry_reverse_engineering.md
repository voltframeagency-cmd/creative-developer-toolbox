# Componentry Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Componentry** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `components/ui/animated-gradient.tsx`**: Shader uniforms: u_time, u_pixelRatio, u_resolution, u_scale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/closing-plasma.tsx`**: Shader uniforms: u_res, u_time, u_mouse, u_isDark. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/dither-prism-hero.tsx`**: Shader uniforms: uTime, uResolution, uMouse, uMouseIntensity. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/hero-geometric.tsx`**: Shader uniforms: uTime, uResolution, uColor1, uColor2. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/image-ripple-effect.tsx`**: Shader uniforms: uTexture, uDisplacement, winResolution, uStrength. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/particle-galaxy.tsx`**: Shader uniforms: uTime, uSize, uPulsate, uPulsateSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/webgl-liquid.tsx`**: Shader uniforms: u_res, u_time, u_colorDeep, u_colorMid. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `components/ui/collection-surfer.tsx`**: Spring values: Stiffness 100, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/eye-tracking.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/github-calendar.tsx`**: Spring values: Stiffness 260, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/letter-cascade.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/liquid-blob.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/magnet-lines.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/magnetic-dock.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/particle-galaxy.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/scroll-based-velocity.tsx`**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/scroll-choreography.tsx`**: Spring values: Stiffness 400, Damping 50. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/showcase-card.tsx`**: Spring values: Stiffness 150, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/text-repel.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **File: `components/ui/layered-stack.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.