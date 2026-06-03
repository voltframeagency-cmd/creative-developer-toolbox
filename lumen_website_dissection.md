# Lumen Creative Website Template Dissection Report

This report dissects the architecture, layout systems, WebGL shaders, and motion design of the **Lumen Creative Website Template** located in `c:/Users/mahdi/Downloads/lumen-template`.

---

## 1. Directory Structure & Tech Stack
The project is built as a modular React application powered by Vite, TypeScript, Tailwind CSS, OGL (for WebGL rendering), and GSAP for state-of-the-art scroll animations.

```
lumen-template/
├── src/
│   ├── components/         # Reusable UI blocks and canvases
│   │   ├── ShaderCanvas.tsx # Hero interaction shader
│   │   └── WaveShader.tsx   # Pinned morphing ribbon wave shader
│   ├── context/            # React state providers (Theme, Shader presets)
│   ├── pages/
│   │   └── Home.tsx         # Core page orchestrating GSAP pins & timelines
│   ├── utils/              # Class mixers and calculations
│   └── App.tsx             # Lenis smooth-scroll setup and layout shell
```

---

## 2. Multi-Stage Scroll-Linked WaveShader
The core visual anchor of the page is the background ribbon wave shader inside `WaveShader.tsx`. It runs a custom WebGL program on a fullscreen triangle using the lightweight `OGL` library.

### GLSL Ribbon Algorithm
The fragment shader draws **5 distinct ribbons** (octaves) by calculating centerline offsets using sine functions, FBM, and 2D value noise:
1. **Centerline Formula**:
   $$\text{cl}(x, \text{phase}) = w_1 \sin(x \cdot f + t \cdot s + \text{phase}) \cdot A_m + w_2 \sin(x \cdot 2.3 + t \cdot 0.7 + \text{phase} \cdot 1.7) \cdot A_m \cdot 0.4 \cdot C$$
   Where $A_m$ is amplitude, $f$ is frequency, $s$ is speed, and $C$ is complexity.
2. **Domain Warping & Pinching**:
   Applies a localized warp offset via 2D noise (`n2`) and shrinks the ribbon thickness (`pinch = 0.55 + 0.45 * sin(xf * 0.6 + ts * 0.4 + phase)`) dynamically.
3. **Palette Mixer**:
   Iterates through the 5 layers, calculates color indexes based on base hue, coordinate position, and time, and blends between 5 custom vectors (`u_c0` to `u_c4`).

### Pinned Morph States
As the user scrolls through the value proposition slides, GSAP morphs the shader uniforms smoothly across three distinct configuration sets:

| Preset | Amplitude | Frequency | Complexity | Speed | Thickness | Warp | Hue (Base) |
|---|---|---|---|---|---|---|---|
| **aq[0] (Slide 1)** | `0.16` | `1.0` | `0.85` | `0.55` | `0.07` | `0.10` | `0.05` |
| **aq[1] (Slide 2)** | `0.26` | `0.45` | `0.45` | `0.40` | `0.11` | `0.03` | `0.30` |
| **aq[2] (Slide 3)** | `0.10` | `0.32` | `0.20` | `0.22` | `0.16` | `0.00` | `0.65` |

---

## 3. GSAP Motion Timelines & Pins
The value proposition slide transitions are choreographed using a pinned scroll timeline in `Home.tsx`.

1. **Pinning Duration**:
   The viewport pins the container (`sec2Ref`) for a scroll travel length of `slides.length * window.innerHeight` (300vh):
   ```typescript
   start: "top top",
   end: () => `+=${totalHeight}`,
   pin: true,
   scrub: true
   ```
2. **Panel Cross-Fading**:
   The slides fade out and in sequentially using opacity/visibility interpolation (`autoAlpha: 0` to `autoAlpha: 1`) over a duration offset of `0.15`.
3. **Word-by-Word Text Highlights**:
   Each word in the slide description is split into a separate span. GSAP steps through the words, shifting their opacity from `0.2` to `1.0` to create a scroll-read indicator:
   ```typescript
   staggerDuration = 0.7 / Math.max(words.length, 1);
   pinTl.to(word, { opacity: 1, duration: staggerDuration }, sIdx + wIdx * staggerDuration);
   ```

---

## 4. Custom Layouts & Micro-Animations
The template features clean layouts with highly polished cursor hooks:

* **Partners Corner Accents**:
  The partner grid cards feature 4 absolute-positioned corners that translate outward (`group-hover:-left-1.5`, etc.) and change border opacity on hover.
* **Character-by-Character Reveals**:
  Headers are split into individual characters. GSAP animates their vertical scale (`scaleY` from `0` to `1` with a `50% 100%` transform origin) as they enter the viewport.
* **FAQ Accordion Grids**:
  Details panels avoid fixed heights by utilizing CSS transition grid rows: `grid-template-rows: 0fr` to `1fr` combined with accordion vert-line rotations.
