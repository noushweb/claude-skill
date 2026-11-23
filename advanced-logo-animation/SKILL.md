---
name: advanced-logo-animation
description: Creates premium, original logo animations from an uploaded logo and optional reference animation. Analyzes reference motion, proposes creative directions, asks for missing assets, and delivers production-ready HTML/SVG/CSS/JS animations with masking, refined easing, responsive layouts, reduced-motion fallbacks, and export guidance. Use for logo reveals, brand stings, app splashes, social animations, loaders, and animated wordmarks.
---

# Advanced Logo Animation

## Mission

Create a polished, original, professional logo animation tailored to the user’s brand.

The final result must feel intentional, premium, and brand-appropriate. It must never distort, obscure, or compromise the recognition of the original logo.

## Required assets

At the start of every task, ask the user for:

1. **Original logo**
   - SVG is strongly preferred.
   - PNG, JPG, or WebP may be accepted, but ask whether a clean vector version is available.
   - Ask for transparent-background files when possible.

2. **Brand guidelines**
   - Primary and secondary colors
   - Fonts or typography direction
   - Logo clear-space and minimum-size rules
   - Any elements that must not be altered

3. **Reference animation, optional**
   - MP4, MOV, WebM, GIF, screen recording, frame sequence, or public URL
   - Ask the user to upload a short sample, ideally 3–15 seconds
   - If no reference is provided, proceed to the idea-generation stage

4. **Output requirements**
   - Platform: website, Instagram Reel, TikTok, YouTube intro, app splash, presentation, email, etc.
   - Aspect ratio: 1:1, 16:9, 9:16, 4:5, or custom
   - Duration
   - Loop behavior: one-shot, seamless loop, or interaction-triggered
   - Background: transparent, solid color, gradient, video-ready, or dark/light
   - Sound design: none, mood only, or full sound brief

Do not begin production until the logo is available or the user explicitly asks for a placeholder concept.

## Reference animation workflow

If the user uploads or links a reference animation, analyze it before proposing a design.

### What to extract

Identify and document:

- Animation category: logo reveal, brand sting, loader, kinetic typography, 3D motion, UI transition, or abstract motion graphic
- Canvas dimensions, duration, frame rate, and loop point
- Reveal order and visual hierarchy
- Element entrances, exits, transformations, overlaps, and holds
- Timing, rhythm, pacing, and dramatic pauses
- Easing character: smooth, snappy, elastic, mechanical, liquid, cinematic, playful
- Camera or scene motion: zoom, pan, rotation, parallax, depth, perspective
- Effects: masking, wipes, mattes, gradients, glows, light sweeps, particles, distortion, trails, grain
- Color, contrast, background, and typography treatment
- Sound cues, if audio is supplied

### Motion blueprint

Before implementation, produce this report:

```text
Reference analysis
- Format / duration / aspect ratio:
- Animation category:
- Core motion idea:
- Beat map:
- Reveal hierarchy:
- Easing and pacing:
- Visual effects:
- Loop strategy:
- What to retain:
- What to adapt for this brand:
- Technical approach:
```

### Originality rule

Use the reference as a **motion-language reference**, not a template to copy.

Preserve transferable principles such as:
- Pacing and rhythm
- Reveal hierarchy
- Easing personality
- Masking or transition technique
- Emotional tone
- Visual hierarchy

Do not reproduce:
- The reference logo, wordmark, mascot, or proprietary visual identity
- Exact proprietary assets, sound design, or recognizable brand-specific effects
- A near-identical composition that could cause brand confusion

The final animation must use the user’s own logo, colors, typography, and brand personality.

## No reference provided

If the user does not provide a reference animation:

1. Analyze the uploaded logo.
2. Propose **three distinct professional directions**.
3. Explain each direction in one or two sentences.
4. Ask the user to choose one, request changes, or approve a recommendation.

Use directions such as:

- **Precision build:** geometric elements assemble cleanly into the final mark.
- **Draw-on reveal:** strokes trace the logo before fills, colors, or wordmark appear.
- **Masked reveal:** shapes, gradients, or moving masks uncover the logo with controlled timing.
- **Light and depth:** subtle shine, shadow, parallax, or dimensional movement creates a premium feel.
- **Liquid energy:** organic morphing, fluid transitions, or ripple effects for expressive brands.
- **Kinetic wordmark:** letters animate with rhythm, weight, and clear brand personality.
- **Minimal luxury:** restrained movement, elegant easing, generous negative space, and a refined settle.
- **Cinematic sting:** dramatic build-up, impact moment, and confident final hold.

If the user provides an idea, expand it into a clear creative direction and confirm the approach before building.

## Creative development

### Analyze the logo

Identify:
- Symbol, monogram, wordmark, tagline, and secondary elements
- Geometry, symmetry, grid structure, negative space, strokes, and fills
- Brand personality and appropriate motion vocabulary
- Animation-safe layer groupings
- Technical risks: thin strokes, gradients, complex details, raster artwork, small text, and legibility

### Create a storyboard

Present a concise beat map:

| Time | Visual event | Motion intent |
|---|---|---|
| 0.0–0.4s | Stage or background enters | Establishes atmosphere |
| 0.3–1.2s | Symbol builds, draws, or reveals | Creates recognition |
| 1.0–1.8s | Wordmark appears | Reinforces brand name |
| 1.6–2.4s | Accent, texture, or detail settles | Adds polish |
| Final | Logo reaches approved final state | Delivers brand clarity |

Adapt timings to the requested duration and platform.

## Professional animation standards

### Motion principles

Apply:
- Clear hierarchy: guide the viewer from the most important element to supporting details
- Anticipation before major movements
- Overlap so elements do not all move at exactly the same moment
- Follow-through and settle for a natural finish
- Secondary motion only when it supports the brand
- A confident final hold or seamless loop

### Easing

Never rely on generic linear motion for the main reveal. Use refined cubic-bezier curves:

- `cubic-bezier(0.22, 1, 0.36, 1)` — premium ease-out
- `cubic-bezier(0.65, 0, 0.35, 1)` — balanced ease-in-out
- `cubic-bezier(0.83, 0, 0.17, 1)` — decisive ease-in-out
- `cubic-bezier(0.16, 1, 0.3, 1)` — smooth, luxurious settle

Define duration and easing through CSS custom properties:

```css
:root {
  --motion-fast: 300ms;
  --motion-base: 700ms;
  --motion-slow: 1200ms;
  --ease-premium: cubic-bezier(0.22, 1, 0.36, 1);
  --ease-decisive: cubic-bezier(0.83, 0, 0.17, 1);
}
```

### Masking and reveals

Use masking deliberately to create high-end transitions:

- **Shape masks:** reveal the logo through a circle, rectangle, diagonal, custom path, or brand-shaped mask.
- **Gradient masks:** create soft, cinematic light sweeps or fade transitions.
- **Clip-path reveals:** uncover elements in a precise, controlled sequence.
- **Stroke draw-on:** trace outlines before fills appear.
- **Layered mattes:** separate background, symbol, wordmark, and accents for depth.
- **Negative-space motion:** use the logo’s own negative space as part of the reveal.

Masking must enhance the logo, not hide or distort it.

## Technical implementation

### Preferred stack

Use this priority:

1. **Self-contained animated SVG** for simple, portable reveals.
2. **HTML + CSS + SVG** for precise sequencing, responsive behavior, and accessible fallbacks.
3. **JavaScript timeline** only when needed for complex sequencing, scroll control, interactive states, or advanced morphing.
4. **Lottie / After Effects specification** when the user needs a designer-editable or video-production-ready deliverable.

### SVG preparation

Before animating:
- Preserve the original logo geometry, proportions, and approved colors.
- Convert raster logos to clean vector artwork only when feasible; otherwise recreate a simplified vector version and clearly disclose limitations.
- Remove unused groups, masks, filters, and definitions.
- Use semantic IDs and classes:
  - `#logo-background`
  - `#logo-symbol`
  - `#logo-wordmark`
  - `#logo-accent`
  - `#logo-tagline`
- Set a tight `viewBox` around the actual artwork.
- Convert text to outlines or provide font-loading instructions; do not rely on unavailable external fonts.
- Keep the final frame visually identical to the approved logo.

### Code requirements

- Provide a runnable deliverable with no unnecessary dependencies.
- Use separate files when useful: `index.html`, `styles.css`, `motion.js`, and `logo.svg`.
- Animate `transform` and `opacity` wherever possible for smooth performance.
- Avoid animating layout properties such as `width`, `height`, `top`, and `left` in high-frequency motion.
- Use `animation-fill-mode: both` or `forwards` to preserve final states.
- Ensure the animation is responsive and does not cause layout shift or horizontal scrolling.
- Comment the code clearly so timing, easing, masks, and layers can be edited easily.

## Accessibility

Always include:

```css
@media (prefers-reduced-motion: reduce) {
  .logo-animation *,
  .logo-animation *::before,
  .logo-animation *::after {
    animation: none !important;
    transition: none !important;
  }
}
```

Provide a static final logo state for users who disable motion. Do not use flashing effects or motion as the only way to communicate brand information.

## Deliverables

Provide:

1. Creative direction and concept explanation.
2. Reference analysis, if a reference was supplied.
3. Beat-by-beat storyboard.
4. Complete, runnable animation code.
5. Standalone HTML preview when applicable.
6. Clean SVG source.
7. Reduced-motion fallback.
8. Export guidance for MP4, WebM, GIF, Lottie, or social platforms.
9. Optional sound-design brief.
10. Clear revision options: speed, easing, reveal order, colors, masks, loop point, and background.

## Quality checklist

Before delivering, verify:

- The final frame matches the original logo.
- The animation has a clear beginning, development, and resolution.
- The wordmark remains readable.
- Colors and proportions follow the brand.
- Masking and transitions feel intentional, not decorative.
- Easing and timing feel premium.
- The loop is seamless if requested.
- The implementation works responsively.
- Reduced-motion users receive a usable static version.
- The result is original and not a copy of the reference animation.

## Interaction example

**User:** “Here is my logo. Make it professional.”

Response:
1. Ask for brand colors, target platform, duration, aspect ratio, and whether they have a reference animation.
2. If no reference is supplied, propose three directions.
3. Wait for the user’s choice or approval.
4. Build the selected animation with a storyboard, code, preview, and export guidance.

**User:** “Here is my logo and a reference video.”

Response:
1. Analyze the reference and produce the motion blueprint.
2. Explain what motion principles will be retained and how they will be adapted.
3. Confirm the direction with the user if the reference strongly suggests a particular style.
4. Create an original, brand-specific implementation using the user’s logo and visual system.
