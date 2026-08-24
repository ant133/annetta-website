Create a polished, animated HTML webpage featuring the 3D word **“FIORA”** floating naturally on the surface of a tranquil pond.

### Core Visual
- The word **FIORA** should be built from individual chunky 3D letters.
- Each letter should look **soft, bouncy, colorful, glossy, and slightly squishy**, like an opaque jelly toy or inflatable pool float.
- Give every letter its own vibrant pastel color while keeping the overall palette cohesive and playful.
- Use rounded forms, glossy reflections, soft highlights, subtle translucency only around the edges, and realistic contact shadows.
- The letters should float partially submerged in the water rather than hovering above it.

### Water & Environment
Create a beautiful stylized pond with:
- continuously moving procedural ripples
- subtle waves and surface distortion
- reflections of the letters
- soft refraction around submerged portions of the letters
- gentle lighting and ambient reflections
- a calm, dreamy atmosphere

The water should feel physically connected to the letters. As waves pass underneath them, each letter should naturally:
- bob up and down
- tilt slightly
- rotate
- drift horizontally
- bump softly into neighboring letters

The letters should behave like lightweight floating objects with buoyancy and soft physics rather than following fixed animations.

### Mouse Interaction
Make the scene highly interactive.

**Mouse hover / movement**
- Moving the cursor across the letters should create small localized disturbances.
- The effect should feel as though a tiny invisible creature is walking or pressing on top of the floating letters.
- Letters near the cursor should gently compress, tilt, wobble, or sink slightly before bouncing back.
- Nearby water should respond with tiny ripples.

**Clicking the water**
- Clicking anywhere on the pond should generate a soft circular ripple from the exact click position.
- The ripple should propagate outward naturally and gradually fade.
- When the wave reaches the floating letters, they should react physically by bobbing, rotating, and drifting slightly.

**Dragging letters**
- Allow users to click and drag individual letters across the pond.
- While dragging, the letter should remain connected to the water surface rather than becoming completely rigid.
- The dragged letter should tilt and lag slightly behind the cursor, giving it a soft, elastic feel.
- Dragging should disturb the surrounding water and create a subtle wake/ripples.
- When released, the letter should preserve some momentum, glide briefly, wobble, and gradually settle back into natural floating motion.

### Physics & Motion
The animation should feel **soft, playful, and organic**.

Implement:
- buoyancy
- damping
- spring-like movement
- inertia
- subtle collisions between letters
- wave-driven movement
- momentum after dragging

Avoid stiff or robotic animations.

The five letters should begin relatively close together so the word **FIORA** is immediately readable, but they should still be independent floating objects capable of separating slightly and bumping into one another.

### Camera & Composition
- Use a slightly elevated perspective looking down toward the pond.
- Keep **FIORA** centered as the visual focus.
- Add subtle perspective depth without making the camera angle dramatic.
- The scene should fill the browser viewport.
- Make it responsive on desktop and mobile.
- If appropriate, allow extremely subtle camera parallax based on mouse position.

### Style Direction
Aim for a visual feeling somewhere between:

**premium 3D web experience + playful inflatable toys + dreamy interactive pond**

The result should feel tactile enough that users instinctively want to poke, drag, and play with the letters.

Avoid making the scene look like a generic particle demo, flat CSS animation, or simple text floating over a water texture. The letters and water should exist together as one believable interactive 3D environment.

### Technical Requirements
- Deliver it as a functional browser-based HTML experience.
- Use WebGL / Three.js where appropriate.
- Use real 3D geometry for the letters rather than HTML text overlays.
- Use raycasting for cursor interaction with the water and individual letters.
- Prefer procedural/generated materials and effects so the experience does not depend heavily on external image assets.
- Use smooth requestAnimationFrame-based animation.
- Keep performance stable and animations fluid.
- Handle browser resizing correctly.
- Organize the code cleanly so visual parameters such as wave strength, buoyancy, damping, colors, glossiness, and interaction forces can easily be adjusted.

Most importantly, prioritize **believable interaction and satisfying motion** over excessive visual effects. The experience should immediately make someone want to click the pond and play with the floating “FIORA” letters.