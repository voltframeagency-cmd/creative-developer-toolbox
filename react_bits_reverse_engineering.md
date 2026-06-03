# React_bits Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **React_bits** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `ASCIIText.tsx`**: Shader uniforms: uTime, mouse, uEnableWaves, mouse. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `GhostCursor.tsx`**: Shader uniforms: iTime, iResolution, iMouse, iOpacity. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LaserFlow.tsx`**: Shader uniforms: iTime, iResolution, iMouse, uWispDensity. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `MagicRings.tsx`**: Shader uniforms: uRingCount. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `MetaBalls.tsx`**: Shader uniforms: iResolution, iTime, iMouse, iColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `MetallicPaint.tsx`**: Shader uniforms: u_tex. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `PixelTrail.tsx`**: Shader uniforms: resolution, mouseTrail, gridSize, pixelColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Ribbons.tsx`**: Shader uniforms: uResolution, uDPR, uThickness, uTime. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `ShapeBlur.tsx`**: Shader uniforms: u_mouse, u_resolution, u_pixelRatio, u_shapeSize. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `SplashCursor.tsx`**: Shader uniforms: texelSize, uTexture, uTexture, value. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `CircularGallery.tsx`**: Shader uniforms: modelViewMatrix, projectionMatrix, tMap, modelViewMatrix. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `FlyingPosters.tsx`**: Shader uniforms: modelViewMatrix, projectionMatrix, normalMatrix, uPosition. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `InfiniteMenu.tsx`**: Shader uniforms: uWorldMatrix, uViewMatrix, uProjectionMatrix, uCameraPosition. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `ProfileCard.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Aurora.tsx`**: Shader uniforms: uTime, uAmplitude, uResolution, uBlend. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Balatro.tsx`**: Shader uniforms: iTime, iResolution, uSpinRotation, uSpinSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Ballpit.tsx`**: Shader uniforms: thicknessPower, thicknessScale, thicknessDistortion, thicknessAmbient. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Beams.tsx`**: Shader uniforms: time, uSpeed, uNoiseIntensity, uScale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `ColorBends.tsx`**: Shader uniforms: uCanvas, uTime, uSpeed, uRot. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `DarkVeil.tsx`**: Shader uniforms: uResolution, uTime, uHueShift, uNoise. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Dither.tsx`**: Shader uniforms: resolution, time, waveSpeed, waveFrequency. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `EvilEye.tsx`**: Shader uniforms: uTime, uResolution, uNoiseTexture, uPupilSize. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `FaultyTerminal.tsx`**: Shader uniforms: iTime, iResolution, uScale, uGridMul. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `FloatingLines.tsx`**: Shader uniforms: iTime, iResolution, animationSpeed, enableTop. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Galaxy.tsx`**: Shader uniforms: uTime, uResolution, uFocal, uRotation. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `GradientBlinds.tsx`**: Shader uniforms: iResolution, iMouse, iTime, uAngle. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Grainient.tsx`**: Shader uniforms: iResolution, iTime, uTimeSpeed, uColorBalance. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `GridDistortion.tsx`**: Shader uniforms: time, uDataTexture, uTexture, resolution. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `GridScan.tsx`**: Shader uniforms: iResolution, iTime, uSkew, uTilt. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Hyperspeed.tsx`**: Shader uniforms: uAmp, uFreq, uFreq, uAmp. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Iridescence.tsx`**: Shader uniforms: uTime, uColor, uResolution, uMouse. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LightPillar.tsx`**: Shader uniforms: uTime, uResolution, uMouse, uTopColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LightRays.tsx`**: Shader uniforms: iTime, iResolution, rayPos, rayDir. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Lightning.tsx`**: Shader uniforms: iResolution, iTime, uHue, uXOffset. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LineWaves.tsx`**: Shader uniforms: uTime, uResolution, uSpeed, uInnerLines. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LiquidChrome.tsx`**: Shader uniforms: uTime, uResolution, uBaseColor, uAmplitude. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `LiquidEther.tsx`**: Shader uniforms: px, boundarySpace, px, center. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Orb.tsx`**: Shader uniforms: iTime, iResolution, hue, hover. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Particles.tsx`**: Shader uniforms: modelMatrix, viewMatrix, projectionMatrix, uTime. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `PixelBlast.tsx`**: Shader uniforms: uTexture, uStrength, uTime, uFreq. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `PixelSnow.tsx`**: Shader uniforms: uTime, uResolution, uFlakeSize, uMinFlakeSize. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Plasma.tsx`**: Shader uniforms: iResolution, iTime, uCustomColor, uUseCustomColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `PlasmaWave.tsx`**: Shader uniforms: iTime, iResolution, uOffset, uRotation. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Prism.tsx`**: Shader uniforms: iResolution, iTime, uHeight, uBaseHalf. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `PrismaticBurst.tsx`**: Shader uniforms: uResolution, uTime, uIntensity, uSpeed. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Radar.tsx`**: Shader uniforms: uTime, uResolution, uSpeed, uScale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `RippleGrid.tsx`**: Shader uniforms: iTime, iResolution, enableRainbow, gridColor. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Silk.tsx`**: Shader uniforms: uTime, uColor, uSpeed, uScale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `SoftAurora.tsx`**: Shader uniforms: uTime, uResolution, uSpeed, uScale. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `Threads.tsx`**: Shader uniforms: iTime, iResolution, uColor, uAmplitude. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `CircularText.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `CountUp.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `FallingText.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **How to Use**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `RotatingText.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ScrollVelocity.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `Carousel.tsx`**: Spring values: Stiffness 300, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `ChromaGrid.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Props**: Spring values: Stiffness 150, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `Dock.tsx`**: Spring values: Stiffness 150, Damping 12. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `InfiniteMenu.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **Component Props**: Spring values: Stiffness 260, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `Stack.tsx`**: Spring values: Stiffness 260, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `TiltedCard.tsx`**: Spring values: Stiffness 100, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `Ballpit.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `Waves.tsx`**: Spring-driven animations active. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## 3. GSAP Motion & Scroll Choreography
Complex timelines and scroll-linked pinning are handled via GSAP's optimized rendering cycles:
* **File: `ScrambledText.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `ScrollFloat.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `ScrollReveal.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **Component Props**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `Shuffle.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **Component Props**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `SplitText.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `TextType.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **Component Props**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `AnimatedContent.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `BlobCursor.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `Crosshair.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `Cubes.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `FadeContent.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `ImageTrail.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `PixelTransition.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `StickerPeel.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `TargetCursor.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `BounceCards.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `BubbleMenu.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `CardNav.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `CardSwap.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `ChromaGrid.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `FlowingMenu.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `MagicBento.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `Masonry.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `PillNav.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `StaggeredMenu.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `DotGrid.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.
* **File: `GridMotion.tsx`**: GSAP animation triggers. Leverages `ScrollTrigger` bounds checking to calculate scroll-bound coordinates.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.