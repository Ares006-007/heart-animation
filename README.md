# Heart Animation

A simple, responsive heart particle animation rendered on an HTML5 canvas. The animation draws a pulsating heart shape using many small particles that smoothly move along a parametric heart curve.

## Demo

You can view the live demo here:

- https://ares006-007.github.io/HEART-ANIMATION/

## Features

- Heart shape generated from a mathematical parametric equation and sampled into multiple point layers for depth.
- Particle system where each particle follows target points on the heart, creating smooth trails.
- Pulsating effect controlled by time-based scaling factors applied to the heart points.
- Responsive canvas that adjusts to the current viewport size on resize events.
- Mobile-aware behavior that reduces particle count and resolution for better performance on smaller devices.

## Project Structure

- `index.html` – Basic HTML file that defines the canvas element where the heart is rendered. [file:3]
- `script.js` – Core animation logic, including heart point generation, particle system, pulse loop, and resize handling. 
- `style.css` – Styles to make the canvas cover the full viewport and set the semi-transparent background.

## How It Works

The script first normalizes `requestAnimationFrame` across browsers, then detects whether the visitor is on a mobile device to adjust performance-related parameters. [file:2] It computes a set of base points from a heart parametric equation, scales and centers them, and uses these as targets for a collection of particles that move and leave traces, producing the glowing heart effect. [file:2]

During each animation frame, a pulse function updates the scaled heart positions, particles advance toward their assigned targets with some randomness, and their trails are drawn as tiny rectangles on the canvas with a slight fade overlay to create motion blur. [file:2]

## Getting Started

1. Clone or download this repository.
2. Open `index.html` in any modern browser.
3. Resize the window to see the animation adapt to different screen sizes.

No build step or dependencies are required; everything runs client-side in the browser.

## Customization

You can tweak the animation by editing `script.js`:

- Change the heart size by modifying the scale values passed into `scaleAndTranslate`.
- Adjust particle density by changing `traceCount` and the loop that fills the particle array. 
- Modify color and opacity by updating the `f` property that uses an HSLA string when particles are created. 
- Tune smoothness and speed using `config.traceK` and `config.timeDelta`. 

You can also adjust the background color or transparency in `style.css` by editing the `background-color` of the `canvas` rule. 

## Browser Support

The animation relies on:

- HTML5 `<canvas>` 2D rendering context.
- `requestAnimationFrame` (with fallbacks implemented for older browsers).

Any modern desktop or mobile browser with JavaScript enabled should be able to run the animation.

## License

This project is provided for learning and personal use. You may modify and reuse the code; please add attribution to the original author if you publish a modified version.
