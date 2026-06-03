# Iconiq Creative Engineering & Reverse-Engineering Manual

This manual dissects the kinetic structures, physics setups, WebGL rendering routines, and easing curves of the **Iconiq** library.

## 1. WebGL & Shader Mathematics
The library implements high-fidelity pixel shaders and canvas renderings using coordinate mapping algorithms:
* **File: `b-slider.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `r-slider.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.
* **File: `slider.tsx`**: Custom WebGL fragment shader. Processes normalized screen coordinates `vUv` mapped to viewports to run noise deformations.

## 2. Spring Physics & Easing Configurations
To simulate mass, friction, and responsive bounce, the following components use custom spring presets:
* **File: `accordion.tsx`**: Spring values: Stiffness 138, Damping 27. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `alert.tsx`**: Spring values: Stiffness 340, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `avatar.tsx`**: Spring values: Stiffness 400, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-accordion.tsx`**: Spring values: Stiffness 138, Damping 27. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-alert-dialog.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-avatar.tsx`**: Spring values: Stiffness 340, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-button.tsx`**: Spring values: Stiffness 640, Damping 38. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-checkbox.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-checkbox-group.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-collapsible.tsx`**: Spring values: Stiffness 420, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-combobox.tsx`**: Spring values: Stiffness 300, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-context-menu.tsx`**: Spring values: Stiffness 600, Damping 38. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-dialog.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-hover-card.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-popover.tsx`**: Spring values: Stiffness 240, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-progress.tsx`**: Spring values: Stiffness 84, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-radio-group.tsx`**: Spring values: Stiffness 400, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-select.tsx`**: Spring values: Stiffness 520, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-slider.tsx`**: Spring values: Stiffness 200, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-tabs.tsx`**: Spring values: Stiffness 260, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-toggle.tsx`**: Spring values: Stiffness 280, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `b-tooltip.tsx`**: Spring values: Stiffness 400, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `button.tsx`**: Spring values: Stiffness 640, Damping 38. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `button-group.tsx`**: Spring values: Stiffness 420, Damping 34. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `calendar.tsx`**: Spring values: Stiffness 400, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `card.tsx`**: Spring values: Stiffness 95, Damping 19. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `checkbox.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `checkbox-group.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `combobox.tsx`**: Spring values: Stiffness 500, Damping 35. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `context-menu.tsx`**: Spring values: Stiffness 600, Damping 38. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `dialog.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `drawer.tsx`**: Spring values: Stiffness 220, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `dropdown.tsx`**: Spring values: Stiffness 260, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `faq-pro.tsx`**: Spring values: Stiffness 150, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `file-upload.tsx`**: Spring values: Stiffness 80, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `hover-card.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `input-group.tsx`**: Spring values: Stiffness 300, Damping 20. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `popover.tsx`**: Spring values: Stiffness 240, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-accordion.tsx`**: Spring values: Stiffness 138, Damping 27. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-alert-dialog.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-avatar.tsx`**: Spring values: Stiffness 340, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-checkbox.tsx`**: Spring values: Stiffness 500, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-collapsible.tsx`**: Spring values: Stiffness 420, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-context-menu.tsx`**: Spring values: Stiffness 600, Damping 38. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-dialog.tsx`**: Spring values: Stiffness 300, Damping 25. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-dropdown.tsx`**: Spring values: Stiffness 260, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-hover-card.tsx`**: Spring values: Stiffness 280, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-popover.tsx`**: Spring values: Stiffness 240, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-progress.tsx`**: Spring values: Stiffness 84, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-radio-group.tsx`**: Spring values: Stiffness 400, Damping 22. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-select.tsx`**: Spring values: Stiffness 520, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-slider.tsx`**: Spring values: Stiffness 200, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-tabs.tsx`**: Spring values: Stiffness 260, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-toggle.tsx`**: Spring values: Stiffness 260, Damping 18. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `r-tooltip.tsx`**: Spring values: Stiffness 400, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `radiogroup.tsx`**: Spring values: Stiffness 300, Damping 28. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `select.tsx`**: Spring values: Stiffness 460, Damping 34. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `slider.tsx`**: Spring values: Stiffness 180, Damping 26. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `table.tsx`**: Spring values: Stiffness 380, Damping 32. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `tabs.tsx`**: Spring values: Stiffness 260, Damping 30. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `text-inertia.tsx`**: Spring values: Stiffness 58, Damping 16. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `toggle.tsx`**: Spring values: Stiffness 210, Damping 15. Uses standard Hooke's Law configuration to decay oscillations cleanly.
* **File: `tooltip.tsx`**: Spring values: Stiffness 400, Damping 24. Uses standard Hooke's Law configuration to decay oscillations cleanly.

## Component Layout & CSS Stacking
All components utilize isolated stacking contexts (`z-index`), border masks (`overflow-hidden`), and smooth hardware-accelerated transforms (`will-change`, `transform3d`) to prevent rendering lag.