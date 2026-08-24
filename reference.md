# annetta.dev — Creative and Interaction Direction

## Overview

`annetta.dev` is the personal portfolio of Annetta, a 20-year-old software developer and IT student based in Jakarta, Indonesia. It showcases her products, experiments, and meme sites.

The site should leave visitors thinking: **“She is a delightfully weird person and an excellent engineer.”**

The experience takes place around a playful public pool. It should feel cute, cozy, polished, and lightly anime-inspired rather than childish or chaotic. The site begins as an immersive 3D pool scene and transitions into a highly interactive 2D portfolio.

Primary colors:

- Pool blue
- Aqua
- Warm white / off-white
- Sunny yellow
- Small pastel accent colors for floaties, toys, and project labels

The portfolio projects themselves should retain their individual identities. Do not force the pool or anime aesthetic into the products shown inside project popups.

## Experience principles

1. **Playful, but readable.** Interaction should reward curiosity without obstructing the portfolio content.
2. **Tactile, but not noisy.** Use buoyancy, easing, small reactions, and cursor feedback instead of constant exaggerated motion.
3. **One continuous world.** The 3D and 2D portions should feel visually connected even though they use different rendering approaches.
4. **Scroll is the timeline.** Important transition animations should track scroll progress precisely and work in reverse when the user scrolls upward.
5. **Polished anime public pool.** Avoid tropical-resort luxury, beach imagery, generic corporate gradients, and overly juvenile water-park styling.
6. **No sound.** All personality should come from visuals, motion, copy, and interaction.

## Site structure

1. Immersive 3D hero
2. 3D-to-2D pool-tile transition
3. About / bio
4. Project vending machine
5. Skills
6. Contact / pool closing time

## 1. Immersive 3D hero

The opening section fills the viewport and has no visible navigation initially.

### Scene

- A slightly elevated camera looks down toward a stylized public pool.
- The word **ANNETTA** is formed from individual chunky 3D inflatable letters floating on the water.
- The letters are colorful, glossy, soft, and partially submerged.
- A 3D model of Annetta lounges on a floatie beside the letters.
- Supporting props may include a rubber duck, colorful pool balls, a kickboard, an inflatable ring, and a lane-divider fragment.
- Keep the composition spacious enough that `ANNETTA` is immediately readable.
- Display the subtitle **“Software Developer / IT Student”** without social links.

### Motion and interaction

- Letters should bob, tilt, drift, and softly bump into one another.
- Water clicks create local ripples that affect nearby letters and props.
- Letters may be dragged and released with gentle momentum.
- The Annetta model floats with the same passive water motion but is not draggable and does not react to the pointer.
- Her pose remains intentionally still, like a display figure floating with the scene.
- Keep camera parallax extremely subtle.
- A clear but minimal scroll cue should appear after the scene settles.

Refer to `sample.md` for detailed water, buoyancy, raycasting, dragging, damping, and material behavior. Replace its example word `FIORA` with `ANNETTA` and treat the Annetta model as a non-draggable floating body.

## 2. Scroll-controlled 3D-to-2D transition

This should look continuous while using a technically reliable handoff.

### Orchestration

1. Pin the hero while the first part of the scroll controls the 3D camera.
2. Move the camera away from the floating composition and toward the pool edge.
3. Reveal the pool coping and blue-and-white public-pool tiles in perspective.
4. Rotate the camera until the tile surface faces it directly and fills the viewport.
5. At the closest visual match, crossfade from the WebGL tile surface to a matching 2D tile layer.
6. Unpin the scene and continue into the 2D page.

The handoff should be disguised through identical tile scale, colors, lighting, and camera alignment. It does not need to keep the remaining website inside WebGL.

All important camera and crossfade values should derive from scroll progress. Scrolling backward should reconstruct the transition cleanly.

### Pool tile art direction

Use the supplied visual reference as the design target for the pool tiles. The surface is a playful ceramic mosaic rather than a perfect checkerboard.

- Use square tiles in warm white, medium cobalt blue, pool blue, and lighter periwinkle blue.
- Arrange the colors in an irregular, semi-random pattern. Some equal colors may touch; avoid a strict alternating checkerboard.
- Keep the tile grid aligned and evenly sized even though the colors vary.
- Separate tiles with narrow warm-white or pale-gray grout lines.
- Give each tile a glazed ceramic finish with soft gloss, slight surface waviness, and restrained specular highlights.
- Add subtle per-tile variation in blue tone, roughness, brightness, and normal direction so the surface does not look procedurally perfect.
- White tiles should be warm and slightly creamy rather than stark digital white.
- The 3D tiles may catch moving reflections and faint water light, but they should not look submerged.
- The matching 2D layer should preserve the same grid, color arrangement, grout width, and highlight placement during the crossfade.
- Outside the handoff, the 2D pattern may rearrange responsively, but it should retain the same approximate balance of white, medium blue, and light blue tiles.
- Avoid turquoise subway tiles, tiny bathroom mosaics, strict chessboard patterns, heavy cracks, dirty grout, and photorealistic grime.

The pattern should feel recognizable as a cheerful public-pool surface while remaining clean and polished enough for a portfolio.

### Navigation entrance

The conventional navigation appears only after the immersive hero has been left behind. It should contain:

- About
- Projects
- Skills
- Contact

Use a compact sticky header. Give it enough contrast over both tiles and off-white sections, and highlight the active section.

## 3. About / bio

The About section begins as a top-down view of 2D pool tiles.

### Reveal

- A walking anime Annetta frame sequence enters from the left.
- Her horizontal movement is controlled by scroll progress, not a one-time autoplay animation.
- The walk cycle is supplied as eight individual transparent PNG frames at `public/assets/characters/bio-walk/1.png` through `8.png`.
- Load the eight files once, preserve their numeric order, and advance frames naturally as she moves.
- Preload or decode all eight frames before revealing the character so the first walk cycle does not flicker.
- When scrolling stops, hold the most natural planted-foot frame rather than continuing to walk in place.
- As she walks, she reveals the bio content behind her through a mask, wipe, or trail.
- Reversing the scroll reverses her travel and the reveal without visibly corrupting the walk cycle.

### Content

Use temporary copy until final copy is provided:

> Hi, I’m Annetta — a software developer and IT student based in Jakarta. I like building useful products, playful internet experiments, and occasionally very unnecessary websites. I enjoy working across backend systems, interfaces, infrastructure, and the strange little details that make software feel alive.

Include:

- A portrait of Annetta
- The temporary introduction above
- Jakarta, Indonesia
- A short current-focus line

### Transition into off-white

After the bio, the complete tile grid gradually breaks into a warm off-white background. It is a color and layout transition, not literal cracked tiles.

Retain subtle traces of the pool world:

- Partial tile fragments near occasional edges
- Very faint wet marks
- Soft aqua shadows
- Sparse bubbles or ripple rings
- Small blue registration-like lines or pool markings

These traces should remain low contrast so content is easy to read.

## 4. Project vending machine

This section is its own full-screen anime composition with a supplied background, vending machine, and character asset. It does not need to visually share the exact background of adjacent sections.

Annetta stands beside the vending machine and invites the visitor to select a drink. Her character can use a subtle idle animation if the supplied asset supports it, but no complex response system is required.

### Machine behavior

- Each project is represented by a bottle or can with a unique label inspired by that project.
- Bottles are direct selection buttons.
- Selecting a bottle opens its project popup immediately; no bottle-drop animation is needed.
- Buttons should have clear hover, focus, pressed, and selected states.
- The machine must support additional projects later.
- If all projects cannot fit at once, use simple shelf paging or previous/next controls rather than shrinking bottles excessively.
- Keyboard users must be able to move through and select every product.

### Project popup

- Blur and dim the vending-machine scene behind the popup.
- Present the project screenshot inside a clean browser-window frame.
- Include project name, short description, screenshot, technology stack, role, year, and status.
- Show a **WIP** badge only after opening the popup when applicable.
- Provide a primary `Visit site` or `Download` action as appropriate.
- Provide a visible close button in the top corner.
- Also support `Escape`, backdrop click, and focus trapping.
- Restore focus to the selected bottle after closing.
- On mobile, use a scrollable near-full-screen sheet rather than a cramped centered modal.

### Initial project catalog

#### DPO

- Full name: Daftar Pencarian Orang
- Description: A bounty-poster generator and web toy made for sharing on Threads.
- URL: `https://dpo.annetta.dev`
- Status: Live
- Screenshot: Placeholder
- Stack: Placeholder
- Role: Placeholder
- Year: Placeholder

#### One Piece Bounty Poster Generator

- Description: A One Piece-themed tool for creating custom bounty posters.
- URL: `https://onepiece.annetta.dev`
- Status: WIP
- Screenshot: Placeholder
- Stack: Placeholder
- Role: Placeholder
- Year: Placeholder

#### One Call Away

- Description: An app that helps people remember and stay connected with the people who matter to them.
- URL: `https://onecallaway.annetta.dev`
- Status: WIP
- Screenshot: Placeholder
- Stack: Placeholder
- Role: Placeholder
- Year: Placeholder

#### Cozy Pomodoro

- Description: A relaxing Pomodoro app with an animal companion that keeps the user company while they focus.
- URL: `https://cozyapp.annetta.dev`
- Status: WIP
- Screenshot: Placeholder
- Stack: Placeholder
- Role: Placeholder
- Year: Placeholder

#### Chord Analyzer

- Description: An app that analyzes an MP3 or YouTube video and displays synchronized chord diagrams in real time.
- URL: Placeholder
- Status: Placeholder
- Screenshot: Placeholder
- Stack: Placeholder
- Role: Placeholder
- Year: Placeholder

Project data should live in a reusable data structure rather than being hard-coded into individual vending slots.

## 5. Skills

Display numerical ratings from 1–10:

- Frontend — 8/10
- Backend — 8/10
- Infrastructure / DevOps — 7/10
- Design — 7/10
- Product Management — 7/10
- AI — 8/10

### Animation concept: pool lanes

Each skill is represented as a horizontal public-pool lane rather than a conventional corporate progress bar.

- The lane fills with aqua color up to its rating.
- A tiny floating ball, kickboard, or stylized swimmer travels with the leading edge.
- A numbered pool marker at the end displays the exact score.
- Lane dividers gently oscillate when the cursor passes nearby.
- Hovering or focusing a skill creates one restrained ripple and emphasizes the score.
- The fill animation is driven by section scroll progress and can reverse.
- Do not use pool depth as a metaphor for competence.

Keep labels and numbers legible without requiring interaction.

## 6. Contact / pool closing time

The final section resembles the quiet closing-time edge of a public pool. Use the warm off-white background with restrained blue tile traces and a slightly more golden light.

The central sign reads:

> POOL CLOSED  
> DON’T BE A STRANGER

Place the primary email action beneath it:

`annettaarslan@gmail.com`

Style the action like a softly illuminated public-facility EXIT sign while keeping the email unmistakable. Clicking it should open a `mailto:` link. Add a secondary copy-email interaction with visible success feedback.

## 2D interaction language

The 2D portion should remain highly interactive, but interactions should be contextual:

- Pool traces react with small ripples near the pointer.
- Loose decorative objects can drift, rotate slightly, or be nudged.
- Important text and controls never move away from the user.
- Tile highlights may follow the pointer softly.
- Cards and buttons use gentle compression and rebound.
- Vending buttons feel mechanical; skill lanes feel buoyant; contact lighting feels calm.
- Avoid applying the same wobble effect to every element.

Potential 2D decorative objects include kickboards, inflatable mattresses, waterproof cards, goggles, towels, sunscreen, beach balls, rubber ducks, pool noodles, lane dividers, depth markers, ladders, drains, wet footprints, bubbles, and caustic-light patches.

## Motion system

- Use spring-like easing with damping for interactive objects.
- Reserve larger movement for section transitions.
- Keep idle animation slow and low amplitude.
- Drive scroll sequences from normalized progress values rather than scattered trigger-only animations.
- Avoid long periods where scrolling produces no visible progress.
- Prevent layout shifts by reserving image and canvas dimensions.
- Pause off-screen animation loops and expensive observers.
- Support `prefers-reduced-motion` with fades, short translations, static water, and no pinned cinematic camera sequence.

## Responsive behavior

Mobile should retain the concept and interaction rather than becoming a static substitute.

- Reduce water simulation resolution, geometry complexity, particle counts, and post-processing.
- Shorten the pinned 3D transition distance.
- Keep the full `ANNETTA` word readable before allowing independent letter drift.
- Disable letter dragging when it conflicts with page scrolling; tapping water may still create ripples.
- Scale the character and machine together so their intended composition is preserved.
- Allow vending shelves to page horizontally.
- Use larger touch targets and avoid hover-only information.
- Keep the skill-lane labels outside narrow animated tracks when needed.
- Test low-power mode and mid-range mobile hardware.

## Performance and implementation guidance

- Use WebGL / Three.js only for the immersive hero and tile handoff.
- Use HTML, CSS, SVG, Canvas, or lightweight sprite animation for the 2D sections.
- Lazy-load vending, project, and sprite assets after the hero is usable.
- Compress GLB files and textures; use KTX2/Draco or Meshopt where supported.
- Prefer generated procedural ripples and simple shaders over large video textures.
- Cap device pixel ratio on high-density displays.
- Keep project content usable if WebGL is unavailable.
- Target smooth interaction over excessive reflections, particles, or post-processing.
- Define visual parameters centrally: colors, wave strength, buoyancy, damping, gloss, ripple force, scroll durations, and reduced-motion behavior.

## Loading, fallback, and failure states

The site must remain understandable while large visual assets are loading or when an advanced feature is unavailable.

### Initial loading experience

- Render the page shell, accessible title, subtitle, and loading status immediately; do not leave a blank canvas.
- Use a small pool-admission ticket or simple floating pool marker as the visual loader.
- Show determinate progress only when it represents real asset progress. Otherwise use a calm indeterminate loop without a fake percentage.
- Load only the hero-critical assets before entering the experience. Defer the vending scene, project screenshots, and walk frames until afterward.
- Reveal the hero once its minimum viable scene is ready instead of waiting for every site asset.
- Provide a visible `Skip intro` action during loading and throughout the pinned hero sequence.
- Avoid autoplay sound or a click-to-enter gate.

### Lightweight fallback hero visual

Create a static poster from the final approved 3D hero composition after its camera and lighting are locked. It should show the top-down pool, floating `ANNETTA` letters, lounging Annetta, and a small selection of pool props. Export it as:

- `public/assets/fallback/hero-poster.webp` for desktop
- `public/assets/fallback/hero-poster-mobile.webp` with a tighter mobile crop
- An optional low-quality placeholder of either image for an immediate blurred preview

Overlay the real HTML title, subtitle, navigation escape, and buttons rather than baking text into the poster. Use the poster while WebGL loads, when reduced data is requested, and when WebGL fails. This keeps the fallback visually faithful without requiring a second illustration system.

### Fallback behavior

- If WebGL is unavailable or initialization fails, replace the 3D hero with a lightweight static or gently layered 2D composition containing the name, subtitle, and a direct path into About.
- If the compressed GLB fails, try the uncompressed source only when its additional download is reasonable; otherwise use the 2D fallback.
- If a nonessential image fails, preserve layout dimensions and show a styled placeholder rather than broken-image UI.
- If a project screenshot is missing, the popup must still provide useful text and actions.
- When JavaScript is unavailable, expose the core bio, project list, email, and navigation as readable HTML where practical.
- Log development errors clearly, but never expose stack traces or debug overlays to production visitors.

## Navigation, URLs, and scroll escape routes

- Use stable anchors: `#about`, `#projects`, `#skills`, and `#contact`.
- Navigation links must work when opened directly, refreshed, copied, or used with browser back and forward controls.
- Selecting a section from inside the pinned hero should exit the hero cleanly before moving to the destination.
- `Skip intro` should move to About, reveal the navigation, and place focus appropriately without replaying the full transition.
- Do not permanently remember that a visitor skipped the intro unless that behavior is later made configurable. A session-only preference is acceptable.
- Respect reduced-motion preferences when scrolling to anchors.
- Prevent scroll locking from remaining active after a modal closes, an animation is interrupted, the route changes, or the viewport is resized.
- Update the URL for major sections without adding excessive history entries during ordinary scrolling.
- Give keyboard and assistive-technology users a conventional `Skip to content` link before the animated experience.

### Skip-intro behavior

When selected, `Skip intro` should:

1. Stop the pinned hero timeline and release any scroll lock.
2. Crossfade the hero out in approximately 200–300 milliseconds.
3. Move directly to `#about` without playing the 3D-to-2D camera move.
4. Reveal the sticky navigation.
5. Move keyboard focus to the About heading while avoiding an unexpected focus jump for pointer users.
6. Pause or dispose of expensive hero rendering once it is no longer visible.

Store the choice only in `sessionStorage`. During the same browser tab session, direct navigation to another section should not replay the intro. A fresh visit in a new session may show the hero normally.

## Footer

Use a compact footer after the closing-time contact scene. It should be quieter than the main CTA and include:

- Copyright with the current year
- `Built by Annetta`
- Email
- Reserved positions for GitHub, LinkedIn, and Résumé links if they are added later
- A small optional line: `No running near the pool.`

External links should clearly indicate their destinations, open predictably, and never depend on icon recognition alone.

## SEO and sharing

- Provide a unique page title and concise meta description centered on Annetta’s software work.
- Set the canonical URL to the final production domain.
- Add Open Graph and social-card metadata with a dedicated share image.
- Provide favicon, SVG icon where supported, Apple touch icon, web-app manifest icons, and theme colors.
- Add semantic `Person` and portfolio/creative-work structured data only for information actually present on the page.
- Generate `sitemap.xml` and `robots.txt` for production.
- Ensure essential bio and project text exists in crawlable HTML rather than only inside WebGL, Canvas, images, or closed dialogs.
- Use descriptive project headings, image alt text, and link labels.
- Do not index staging deployments or placeholder project pages.

Suggested initial metadata:

- Title: `Annetta — Software Developer & IT Student`
- Description: `Annetta is a software developer and IT student in Jakarta building useful products, playful web experiments, and delightfully unnecessary websites.`
- Canonical URL: `https://annetta.dev/`

## Performance budgets

Treat these as initial targets to validate on the deployed site, not reasons to remove the site’s identity.

- Keep the first-load transfer for hero-critical assets near or below 5 MB on desktop and use a lighter mobile asset path where possible.
- Keep noncritical vending, project, and sprite assets out of the initial critical request chain.
- Aim for Largest Contentful Paint within 2.5 seconds and Interaction to Next Paint within 200 milliseconds at the 75th percentile on representative devices and connections.
- Keep layout shift effectively unnoticeable by reserving dimensions for canvases, sprites, images, and popups.
- Target 60 frames per second on capable desktops and a stable minimum of 30 frames per second on supported mid-range mobile devices.
- Cap the rendering pixel ratio and lower water resolution, reflection quality, shadow resolution, antialiasing, and post-processing before reducing interaction responsiveness.
- Avoid individual textures larger than necessary; define desktop and mobile texture variants for expensive assets.
- Pause rendering or reduce it to a very low update rate when the page is hidden or the 3D hero is fully off-screen.
- Test production builds with network throttling and CPU slowdown, not only on a development machine.

### Production asset-size measurement

“Production asset size” means the number of compressed bytes a visitor actually downloads after the final build—not the editable source-file size shown in a design tool. Record both each file’s transferred size and the combined size of the initial requests. In particular, measure:

- GLB models after geometry and texture compression
- PNG/WebP/AVIF images after export optimization
- JavaScript and CSS after bundling, minification, and compression
- Fonts and shader files
- The eight walking frames as one combined animation cost
- The hero-critical total separately from deferred project and vending assets

Use the browser Network panel and a production build report to find unexpectedly large assets and decide what must be compressed, resized, converted, or lazy-loaded.

### Mobile quality presets

Provide two mobile presets selected from capability signals and a short startup performance sample. Do not use user-agent strings as the only decision.

**Mobile Standard**

- Cap device pixel ratio at 1.5
- Use medium water/reflection resolution
- Use one main directional light with limited soft shadows
- Keep ripple clicks and passive buoyancy
- Disable expensive depth-of-field, bloom, and screen-space reflection passes
- Target a stable 30–60 frames per second

**Mobile Lite**

- Cap device pixel ratio at 1.0
- Use low-resolution water simulation and simplified reflections
- Disable realtime shadows and nonessential particles
- Reduce the number of active floating props
- Disable letter dragging while retaining tap ripples and scroll motion
- Prefer the static fallback hero if stable performance cannot be maintained

Allow users to continue into the 2D portfolio regardless of which preset succeeds.

## Browser support

- Support the latest two stable major versions of Chrome, Edge, Firefox, and Safari.
- Support Safari on iOS/iPadOS 17 and newer as the practical mobile baseline.
- Treat Android Chrome from roughly the last three years as the primary Android target, with graceful degradation on weaker devices.
- Require modern JavaScript modules, CSS custom properties, and WebGL 2 for the complete hero.
- Provide the static hero fallback when WebGL 2, required graphics limits, or key APIs are unavailable.
- Internet Explorer and legacy embedded webviews are not supported.
- Test at minimum on desktop Chrome, desktop Safari, iPhone Safari, and one mid-range Android Chrome device before launch.

## Hosting and routing

- Deploy the production build as a static GitHub Pages site.
- Use a single-page document with hash anchors for the main sections; no client-side router is required for the first release.
- Use `https://annetta.dev/` as the canonical address.
- Configure `annetta.dev` as the GitHub Pages custom domain, verify ownership, configure the required apex DNS records, and enable `Enforce HTTPS`.
- Configure `www.annetta.dev` as well and redirect it consistently to the chosen canonical apex domain.
- Do not use wildcard DNS records for GitHub Pages.
- Publish a root-level `404.html` for unknown paths.
- Ensure build-time asset URLs work from both the temporary `*.github.io` preview and the custom root domain.
- Offline/PWA support is explicitly out of scope for the first release.

## Utility and error pages

### 404 page

- Reuse the closing-time public-pool language without loading the full 3D experience.
- Suggested heading: `POOL CLOSED`
- Suggested supporting copy: `This lane doesn’t seem to exist.`
- Provide clear actions to return home or view projects.

### General error state

- Use calm, direct copy explaining that part of the pool failed to load.
- Offer `Try again`, `Continue without 3D`, and `Go home` where appropriate.
- Never make decorative animation a requirement for recovering from an error.

### Offline behavior

- If offline support is implemented, cache the lightweight shell and core portfolio content rather than attempting to cache every 3D and project asset.
- Clearly label external project links that cannot open while offline.

## Accessibility

- Maintain readable contrast over water, tiles, and anime backgrounds.
- Provide semantic headings and a logical reading order independent of animation.
- Give every graphical control an accessible name.
- Provide alt text for meaningful images and empty alt text for decoration.
- Ensure modal focus management and keyboard navigation work correctly.
- Never encode project status or skill score by color alone.
- Make the experience functional with reduced motion, keyboard-only navigation, and without WebGL.

## Asset organization

Place supplied and generated assets under:

```text
public/
  assets/
    3d/
      annetta.glb
      annetta.optimized.glb
      textures/
    characters/
      bio-walk/
        1.png
        2.png
        3.png
        4.png
        5.png
        6.png
        7.png
        8.png
      vending/
        annetta.png
    vending/
      background.png
      machine.png
      bottles/
        dpo.png
        one-piece.png
        one-call-away.png
        cozy-pomodoro.png
        chord-analyzer.png
    projects/
      dpo/
      one-piece/
      one-call-away/
      cozy-pomodoro/
      chord-analyzer/
    fallback/
      hero-poster.webp
      hero-poster-mobile.webp
    seo/
      social-card-placeholder.png
      favicon-placeholder.svg
    downloads/
      resume-placeholder.pdf
```

If the eventual framework uses `static/` instead of `public/`, preserve the internal `assets/` structure and move the root accordingly.

Keep transparent PNG artwork separate by role. GLB files may embed their textures; otherwise store textures in `public/assets/3d/textures/`. Use lowercase kebab-case filenames and avoid spaces.

Prefer `annetta.optimized.glb` in production and retain `annetta.glb` as the uncompressed source/fallback. Future letter, duck, and pool-prop models should be added beside these files with descriptive lowercase kebab-case names.

## Content still needed

- Final bio and current-focus copy
- Final portrait
- Final 3D inflatable letters, rubber duck, and additional pool-prop GLBs
- Project screenshots
- Project stacks, roles, years, and final statuses
- Chord Analyzer name, URL, and status
- Final project bottle-label artwork

## Prerequisites and decisions still needed

These additions can be scaffolded now, but final production behavior requires:

### Loading and fallbacks

- Replace the fallback poster placeholders with renders from the final approved hero composition
- Final hero asset sizes to determine the real preload list
- A decision on whether `annetta.glb` should be downloaded as a fallback or kept only as a source file

### Navigation and URLs

- GitHub repository and Pages publishing workflow details
- Final confirmation of whether `annetta.glb` remains a source-only file

### Footer

- Final copyright/byline wording
- Replace placeholder GitHub, LinkedIn, and résumé links when available
- Replace `public/assets/downloads/resume-placeholder.pdf` with the final résumé

### SEO and sharing

- Final title and meta description approval
- Replace the placeholder with a final 1200 × 630 social sharing image
- Replace placeholder favicon/app icons and confirm the browser theme color
- Whether staging deployments should be password-protected or marked `noindex`

### Performance

- A production build and deployed test URL
- Baseline measurements on at least one mid-range phone and one typical laptop
- Compressed sizes for every GLB, texture, PNG sequence, and vending asset
- A defined mobile quality preset and fallback threshold

### Utility pages

- A lightweight illustration or tile treatment for the 404 page
- Offline support is deferred until after the first release
