# Scrollx Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Scrollx** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `components/ui/cosmic-background.tsx`**: Shader uniforms: uTime, uResolution, uMouse, uIntensity. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/followcursor.tsx`**: Shader uniforms: uResolution, uDPR, uThickness, uTime. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/globe.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/ui/globe-wireframe.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `components/ui/alert-dialog.tsx`**: Spring values: Stiffness 150, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/border-glide.tsx`**: Spring values: Stiffness 100, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/card-tilt.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/checkbox-pro.tsx`**: Spring values: Stiffness 400, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/checklist-cell.tsx`**: Spring values: Stiffness 320, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/cursorimagetrail.tsx`**: Spring values: Stiffness 150, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/draggable-avatar.tsx`**: Spring values: Stiffness 400, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/dropdown-menu.tsx`**: Spring values: Stiffness 260, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/flipflow.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/followcursor.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/glass.tsx`**: Spring values: Stiffness 200, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/globe.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/heroui.tsx`**: Spring values: Stiffness 120, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/layer-stack.tsx`**: Spring values: Stiffness 100, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Props & API Reference**: Spring values: Stiffness 150, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/magicdock.tsx`**: Spring values: Stiffness 100, Damping 5. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/media-card.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/morphotextflip.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/motion-navbar.tsx`**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/navbar-flow.tsx`**: Spring values: Stiffness 100, Damping 11. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/pagination.tsx`**: Spring values: Stiffness 400, Damping 10. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/popover.tsx`**: Spring values: Stiffness 400, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/profilecard.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/radio-group.tsx`**: Spring values: Stiffness 600, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/select.tsx`**: Spring values: Stiffness 260, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/shiny-button.tsx`**: Spring values: Stiffness 150, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/side-sheet.tsx`**: Spring values: Stiffness 400, Damping 40. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/statscarousel.tsx`**: Spring values: Stiffness 50, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/statscount.tsx`**: Spring values: Stiffness 50, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/toast.tsx`**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/tooltip.tsx`**: Spring values: Stiffness 400, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `components/ui/top-sheet.tsx`**: Spring values: Stiffness 400, Damping 40. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.