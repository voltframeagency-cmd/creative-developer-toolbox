# Bklit Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Bklit** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **`Gauge` Props**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `src/charts/gauge.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `src/charts/funnel-chart.tsx`**: Spring values: Stiffness 300, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/gauge.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/live-x-axis.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/live-y-axis.tsx`**: Spring values: Stiffness 180, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/pie-slice.tsx`**: Spring values: Stiffness 400, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/radar-area.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/radar-axis.tsx`**: Spring values: Stiffness 80, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/radar-grid.tsx`**: Spring values: Stiffness 100, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/radar-labels.tsx`**: Spring values: Stiffness 80, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `src/charts/ring.tsx`**: Spring values: Stiffness 400, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Example 2**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.