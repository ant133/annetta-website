# ANNETTA Website — Status & Next Steps

Last updated: 24 August 2026

## Current status

The website is already a functional, responsive interactive portfolio with a clear public-pool theme. The core experience is built with vanilla HTML, CSS, JavaScript, and Three.js—without a frontend framework or build step.

### What is working

- Intro loader with an admission ticket and a working **Skip intro** action.
- Interactive 3D pool hero with:
  - Floating `ANNETTA` letters.
  - Click-and-drag letter interaction on desktop and mobile.
  - Buoyant pool objects with shared water movement.
  - Lounging Annetta GLB that floats and rotates subtly but cannot be grabbed.
  - Pool-floor texture, lighting, shadows, caustics, ripples, and mobile scaling.
  - Clickable code-sculpted social pillow floaties for Instagram, Threads, GitHub, and Email.
  - Three code-generated colorful beach balls using lightweight sphere geometry and canvas textures.
  - Lightweight fallback when WebGL or the module fails.
- 3D-to-2D tiled transition.
- About section with a scroll-driven Annetta walking sequence.
  - One right-facing walker only.
  - Anchored to a fixed horizontal baseline inside the tiled document section.
  - Starts as the About scene enters after the 3D-to-2D handoff.
- Project section presented as a vending-machine scene.
  - Desktop composition uses the machine, Annetta, heading, and clickable bottles already pictured inside the machine artwork.
  - Mobile hides the vending character and centers the machine.
  - Transparent native buttons turn five illustrated bottles into project selectors without drawing duplicate drinks.
  - Project dialogs use project-specific artwork and current project content.
  - Vending scene entrance animation is implemented.
- Skills section presented as swimming lanes.
- Final corridor beat with the mirrored right-to-left walking animation and the copy:
  - “...I forgot to bring my towel”
- Contact section with a **Send email** CTA.
- Footer with active Instagram, Threads, GitHub, and Email links.
- Responsive layouts, reduced-motion support, basic accessibility, metadata, and loading/performance safeguards.

### Current placeholders or unfinished areas

- The skills lanes still use simple ball/board markers instead of swimmers.
- The Projects composition and bottle-hotspot alignment still need browser/device layout review.
- The social floaties have their primary click/hover behavior; more elaborate physical micro-interactions remain optional.
- `styles.css` contains accumulated override rules from multiple iterations and should eventually be consolidated carefully.
- The site still needs final browser/device testing and a production deployment check.

## Planned improvements

### 1. Position-triggered corridor slip — complete

Scroll-velocity running behavior was deliberately scrapped. The final corridor behavior is position-triggered:

- Annetta walks right-to-left as the corridor enters view.
- Crossing the fixed corridor trigger starts a time-driven slip, impact, reaction, and recovery sequence.
- Forward scrolling is held briefly so the important frames cannot be skipped.
- The sequence runs once until the visitor scrolls back before its reset point.
- Reduced-motion mode does not play the slip sequence.

No running-cycle asset or velocity state machine is planned.

### 2. Final social-media floaties — complete

The floaties remain lightweight, code-sculpted Three.js geometry because external GLB generation is no longer planned. Each pillow now has a separate top panel and a canvas-vector logo decal for:

- Instagram
- Threads
- GitHub
- Email

Current implementation:

- Uses centered Three.js groups for floating and rotation.
- Keeps consistent physical dimensions and visual weight.
- Generates small in-memory canvas textures instead of downloading image or GLB assets.
- Uses lightweight glossy materials.
- Follows the existing buoyancy system.
- Opens the corresponding account or email action on click/tap.
- Lifts slightly on hover and produces an impulse plus ripple when activated.
- Uses the matching active links in the footer; LinkedIn has been removed.

Optional later polish:

- Slight tilt toward the pointer.
- Brighter material or highlight when interactive.

### 3. Additional pool props — first pass complete

Three colorful beach balls are now generated entirely in Three.js with sphere geometry and in-memory canvas panel textures. Mobile renders two to keep the pool composition restrained.

Possible later additions, only if the scene still needs them:

- Small kickboard.
- Optional goggles or toy boat.

The rubber duck is no longer planned while external asset-generation credits are unavailable.

### 4. Swimming Annetta image — complete

A separate static swimming Annetta image is positioned at the bottom of the contact section before the footer and remains visually separate from the walking and lounging versions.

### 5. Replace Skills markers with swimmers

Replace the current circular/board lane markers with top-down swimmer spritesheet animations.

Recommended behavior:

- Each lane has a small looping swimmer.
- Swimmer position remains tied to the skill score or section progress.
- Frame playback is time-driven, while horizontal movement is scroll-driven.
- Slight timing offsets prevent all swimmers from moving identically.
- Swimmers use a top-down perspective and a consistent scale.

Assets needed:

- One reusable top-down swimming loop of approximately 8–12 frames, or a small set of color variants.
- Transparent background and identical frame dimensions.

### 6. Adjust the portfolio section — layout review remains

Project content, URLs, artwork, statuses, roles, and technology metadata have received their content pass. The remaining work is layout validation and refinement:

- Recheck heading, vending machine, and character balance on common desktop sizes.
- Recheck machine centering and project-button usability on mobile.
- Verify the five transparent project hotspots remain aligned with the illustrated middle-row bottles at every breakpoint.
- Keep important project information discoverable without requiring excessive exploration.
- Project-list semantics now use list-item wrappers so the interactive controls retain their native button role.

### 7. Typography and copywriting pass — complete

The current typography, hierarchy, and copy are considered complete. Revisit only if layout QA exposes a wrapping or readability problem.

### 8. More floatie micro-interactions

Optional polish for the code-generated pool objects:

- Pointer proximity creates subtle ripples.
- Hover increases clearcoat, brightness, or buoyant lift.
- Tap produces a small squash, rotation impulse, and expanding ripple.
- Social floaties already communicate clickability through hover lift and a pointer cursor.
- Props collide softly without becoming chaotic.
- Mobile gestures must not interfere with normal vertical scrolling.
- Add limits and damping so objects naturally return to their home areas.

## Recommended implementation order

1. Replace Skills markers with top-down swimmers.
2. Review and refine the Projects composition and bottle-hotspot alignment across breakpoints.
3. Perform browser, touch, keyboard, reduced-motion, and performance QA.
4. Add optional floatie/ball micro-interactions only after scene layout is stable.
5. Consolidate CSS overrides after visual behavior is approved.

## Final QA checklist

- Test Chrome, Safari, Firefox, and Edge.
- Test mouse, trackpad, touch, and keyboard interaction.
- Test narrow mobile, large mobile, tablet, laptop, and wide desktop layouts.
- Test slow scrolling, fast scrolling, reverse scrolling, and sudden direction changes.
- Test with reduced motion enabled.
- Test with WebGL unavailable and under a slow network.
- Confirm that every social and project link works.
- Check that no animation traps scrolling or blocks content.
- Measure loading time, frame rate, layout shift, and asset sizes.
- Confirm that all large image and GLB files are optimized before deployment.

## Immediate next action

Replace the Skills lane markers with top-down swimmers, then perform a focused responsive review of the revised vending-machine project hotspots.
