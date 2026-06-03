# Chamaacui Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Chamaacui** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `registry/chamaac/astral-flow/astral-flow.tsx`**: Shader uniforms: uTime, uResolution, uColor1, uColor2. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/electric-mist/electric-mist.tsx`**: Shader uniforms: uTime, uResolution, uColor, uSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/grid-bloom/grid-bloom.tsx`**: Shader uniforms: iTime, iResolution, uColor, uSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/liquid-chrome/liquid-chrome.tsx`**: Shader uniforms: uTime, uTimeScale, uColor, uColor2. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/nebula/nebula.tsx`**: Shader uniforms: uTime, uColor1, uColor2, uColor3. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/synthesis/synthesis.tsx`**: Shader uniforms: uResolution, uTime, uColor1, uColor2. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/water-caustic/water-caustic.tsx`**: Shader uniforms: iTime, iResolution, uColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `registry/chamaac/waves/waves.tsx`**: Shader uniforms: u_time, u_speed_x, u_speed_y, u_amp. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `registry/chamaac/ai-input/ai-input.tsx`**: Spring values: Stiffness 200, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `registry/chamaac/dancing-letters/dancing-letters.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.