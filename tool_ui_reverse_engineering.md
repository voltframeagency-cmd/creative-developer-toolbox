# Tool Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Tool** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **Component Usage Example**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **`SliderConfig` Schema Properties**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/tool-ui/parameter-slider/math.ts`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/tool-ui/parameter-slider/parameter-slider.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/tool-ui/parameter-slider/schema.ts`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `components/tool-ui/weather-widget/generated/weather-runtime-core.generated.ts`**: Shader uniforms: u_time, u_resolution, u_timeOfDay, u_moonPhase. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.