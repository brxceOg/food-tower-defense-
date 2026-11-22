# Food Tower Defense — Art Direction

Visual source of truth for artwork, animation, battlefield presentation, and interface design.

## Overall identity
Food Tower Defense is a 2D pixel-art game. The battlefield, customers, food weapons, effects, menus, and HUD must feel like parts of one deliberately crafted pixel game.

The tone is colorful, playful, readable, and full of personality. The restaurant-defense premise should be obvious: food is ammunition, customers are approaching targets, and the restaurant is what the player protects.

Use established pixel-art games and classic pixel-game interfaces as references. Do not make the game resemble a modern website, dashboard, or mobile productivity app.

## Pixel-art integrity
- Use actual pixel-art assets and pixel-conscious rendering.
- Preserve crisp pixel edges. Avoid smoothing, blur, soft gradients, and fractional scaling that makes sprites muddy.
- Prefer integer scaling where practical and nearest-neighbor rendering for pixel-art assets.
- Keep sprite proportions and pixel density consistent.
- Harmonize detail level when combining assets from different sources.
- Effects and animations must use a compatible pixel scale.
- Do not recolor, crop, redraw, or rearrange supplied sprites without inspecting the source and preserving important details.
- Never guess sprite-sheet frame counts or animation order; inspect the sheet first.

## Supplied starting artwork
Three images were supplied:
- Two customer character images/sprite sheets.
- One pixel-art battlefield/map image with grassy terrain and a winding stone path.

These establish the initial character and environment direction. Inspect and integrate the actual assets where suitable. Do not assume filenames, dimensions, transparency, frame layout, or animation sequence until the files are inspected directly.

## Battlefield art
- Portrait-first, vertically scrollable game world.
- Terrain should read as a cohesive pixel-art map, not a flat HTML board.
- The customer route must be visually distinct from buildable ground.
- Use the supplied grassy terrain and winding stone path as the initial map reference.
- Buildable areas should be easy to identify without looking like generic web buttons.
- Turrets should sit naturally on terrain with clear footprints and readable silhouettes.
- The restaurant should be a strong visual destination at the end of the route.
- Maintain contrast between customers, projectiles, turrets, route, and terrain at phone size.
- The map should extend beyond the viewport as a continuous world without visible seams or abrupt jumps.

## Customer art and animation
- The supplied customer sheet is divided into measured 180 × 256 source cells. Extract the largest connected character silhouette from each walk-cycle cell independently, discard disconnected labels and neighboring artwork, then assemble the isolated sprites into a clean 4 × 2 sheet. Normalize all eight extracted sprites with one shared scale and a common bottom baseline so the animation does not jump or change size between frames.
- Keep each character's frame sequence separate and advance it on a per-customer timer at a steady, readable pace.
- Keep customers recognizable as the supplied characters.
- Use available walking and reaction animations where supported by the sheets.
- Movement follows the route smoothly while remaining crisp.
- Food hits need clear, brief feedback.
- Fully fed customers should play an eating/satisfied/happy reaction where available before leaving.
- Hunger/health indicators should be compact and consistent with the game UI.
- New customer types should feel like variations in the same character world.

## Food turrets and projectiles
Food weaponry is the defining visual hook. Weapons should be immediately recognizable as food-themed machines or stations.

Initial concepts: Ketchup Cannon, Mustard Cannon, Pizza Launcher, Burger Blaster, Soda Sprayer, Fry Flinger, and Ice Cream Machine.

- Give each turret a distinct silhouette and readable firing direction.
- Anchor turret bases visually to the map.
- Projectiles should clearly read as the food being fired.
- Firing, impact, feeding, slowing, and area effects must be readable at small mobile sizes.
- Use stylized pixel-art food, not realistic food photography.
- Upgrades may add details, attachments, or animation changes while keeping the turret recognizable.

## Pixel-game UI — mandatory
The entire player-facing interface must look and feel like a standard, thoughtfully designed pixel-art game UI. This is a core requirement, not a later polish task.

Use classic pixel-game UI as the reference for HUD frames, buttons, build menus, turret selection, currency/health/wave indicators, popups, upgrade panels, menus, icons, selection highlights, transitions, and game-over/results screens.

### No browser-native appearance
- No visible browser-native scrolling UI or scrollbar.
- No default browser text styling.
- No unstyled HTML controls or native-looking buttons, selects, sliders, or form elements.
- No generic web cards, dashboard panels, SaaS styling, or modern app navigation patterns.
- No reliance on system fonts for the visual identity.
- No visible page-layout behavior that breaks the illusion of a self-contained game.

HTML, CSS, and JavaScript may be used underneath, but all visible controls must be custom-styled and behave like game UI.

### UI visual language
- Crisp pixel borders, corners, separators, and panel frames.
- Illustrated, textured, or restrained game-world panel backgrounds where appropriate.
- Deliberately selected pixel fonts for headings and supporting text; prioritize readability at iPhone size.
- Custom pixel-art icons for currency, health, waves, turrets, and actions.
- Clear idle, pressed, selected, disabled, and unaffordable states; hover states where relevant.
- Restrained animation and immediate visual feedback.
- Consistent spacing, panel scale, border thickness, and icon treatment across screens.
- Pixel styling must never make text illegible.

## Mobile presentation
- Portrait-first composition.
- Battlefield occupies the space between fixed HUD and fixed build controls.
- HUD and build menu stay fixed while the map camera scrolls.
- Use custom touch-driven camera movement, not document/page scrolling.
- Touch targets must be comfortable without making the UI resemble a generic mobile app.
- Keep essential information readable without obscuring too much battlefield.
- Preserve crisp pixel scaling across iPhone viewport sizes.
- Prevent accidental text selection, browser callouts, and disruptive page gestures where practical.


## Enhanced pixel-art and 2.5D visual direction

The target is **premium, expressive pixel art with subtle 2.5D depth**—not bare-bones or deliberately crude pixel art, and not fully 3D.

Use the visual idea of a paper-craft world: characters and objects can feel like dimensional, layered pieces placed into a richly illustrated game environment. The Paper Mario comparison is a useful directional reference for the balance of flat, readable character designs and dimensional presentation; do not copy its characters or exact assets.

### Shape, depth, and shading
- Aim for polished, carefully constructed pixel art with appealing silhouettes, deliberate palettes, rich details, and consistent lighting.
- Give characters, turrets, food, props, and environment a subtle sense of volume through stepped pixel shading, highlights, ambient occlusion, and cast/contact shadows.
- Use layered forms and restrained perspective cues so objects feel like crafted pieces with thickness, rather than flat stickers.
- Characters may retain mostly flat, graphic front-facing designs while receiving dimensional shading, layered limbs/accessories, subtle side thickness, and soft pixel shadows.
- Use tasteful bevels, raised surfaces, rounded volume, and material-specific highlights where they suit the object.
- The map may use gentle height variation, layered terrain edges, raised path borders, dimensional props, and depth-aware shadows.
- Maintain a coherent light direction and consistent shadow behavior across the whole scene.
- Depth should improve readability and charm, never obscure the clean pixel silhouettes.

### Keep it pixel art—not full 3D
- Do not turn the game into a fully 3D-rendered scene.
- Do not use smooth polygonal 3D models as a replacement for pixel-art sprites.
- Do not apply generic 3D bevel filters or blurry gradients to pixel assets.
- Dimensionality should be authored in the pixel-art style: stepped shading, carefully placed highlights, layered sprite parts, pixel shadows, and limited perspective.
- Preserve crisp pixel edges and the established pixel scale even when suggesting volume.
- Avoid a flat, unshaded, low-detail appearance; the intended finish is richer and more tactile than basic pixel art.

## Custom pixel combat effects — required

Combat effects must be custom-designed pixel art and treated as a major part of the game's visual identity. Do not rely on generic CSS flashes, emoji, stock particles, or plain circles as final combat feedback.

Create a consistent effect language for:
- Food projectile trails and flight.
- Muzzle flashes and turret firing recoil.
- Food impact splats, crumbs, sauce bursts, and hit sparks.
- Feeding/eating reactions and satisfaction celebrations.
- Area-of-effect bursts for pizza or other splash weapons.
- Soda spray, sticky puddles, slowing effects, and ice/freeze effects.
- Customer damage feedback and clear defeat/satisfied cues.
- Turret upgrade or activation effects.
- Wave-start, wave-clear, and game-over presentation.

Effects should be distinctive to the food or weapon causing them. For example, sauce impacts can create a small stylized splat; pizza impacts can scatter toppings or crumbs; soda can leave a brief fizzy splash; ice cream can create a frosty pixel burst. These are visual direction examples, not fixed mechanics.

### Effect animation and readability
- Use authored sprite animations or carefully drawn pixel-particle sequences with consistent pixel density.
- Give effects a clear beginning, readable peak, and quick resolution.
- Layer effects correctly in front of or behind characters and turrets.
- Keep effects legible on a phone without overwhelming customer sprites or the route.
- Use varied but controlled timing, scale, and silhouettes to make different weapons feel satisfying.
- Avoid excessive screen shake, full-screen flashes, visual noise, and effects that hide important gameplay.
- Where appropriate, use subtle squash/stretch or layered frame changes while preserving the pixel-art look.

## Motion and feedback
- Keep animations expressive but controlled so busy waves remain readable.
- Customers visibly walk along the route.
- Turrets communicate firing.
- Food projectiles travel visibly from turret to target.
- Hits produce compact pixel-art impact feedback.
- Satisfied customers react before leaving.
- Buttons and panels respond immediately.
- Wave starts, wave clears, and game over have distinct game-like transitions.
- Avoid excessive shake, flashes, or effects that obscure play.

## Consistency rules
- Every new asset must match the established pixel scale, palette, outline/shading approach, and detail level.
- Reuse the same visual language across gameplay and menus.
- Do not use emoji as substitutes for finished game icons.
- Do not use generic icon libraries as final game-facing artwork.
- Do not use generated mockup images as the actual UI implementation.
- Do not replace supplied assets with placeholders when real assets are available.
- If an asset's purpose or animation is unclear, inspect it and ask rather than guessing.

## Asset inventory
As assets are added, record file path/name, intended use, source/creator and license, dimensions/transparency, sprite frame dimensions/count, verified animation names/order, and any processing required.

## Art review checklist
- Does it read as pixel art at actual iPhone size?
- Are edges crisp and pixel density consistent?
- Does it match the supplied character/map artwork?
- Is its purpose immediately understandable?
- Does the UI look like a pixel game rather than a webpage?
- Are any browser-native controls, fonts, scrollbars, or default elements visible?
- Does the battlefield remain readable during active combat?
- Are touch interactions visually clear?


## Verified repository artwork (2026-11-21)
The four user-supplied source files are present in the repository root and are used as source artwork; preserve the originals.

| File | Verified dimensions | Intended use |
|---|---:|---|
| `IMG_1357.jpeg` | 160 × 119 | 4 × 4 food-turret / firing-state sheet. Condiment turret states occupy the upper rows; pizza-cannon states occupy the lower rows. |
| `IMG_1359.jpeg` | 160 × 119 | Full battlefield composition: winding stone route, grass, restaurant, and environmental props. |
| `IMG_1363.jpeg` | 1440 × 768 | 8 × 3 customer sprite layout with two character designs and feeding/progression poses. The first four cells of the top row and first four of the second row are used as initial walk cycles. |
| `IMG_1364.gif` | 1632 × 1344 | UI reference sheet containing buttons, icons, controls, pop-up panels, and pixel-font glyph samples. |
| `IMG_1365.jpeg` | Newly supplied male-customer sheet | Six isolated walk-cycle frames across the upper row and one isolated knockback/reaction pose in the lower row; use a shared scale and bottom baseline. |

The current runtime extracts transparent character/turret cutouts from the JPEG sprite sheets by removing the neutral gray sheet background. Cropping is calculated from the loaded image's actual dimensions rather than assuming a high-resolution export. The source files remain unchanged. The GIF is retained as the UI reference for the next interface-art integration pass.


### Male customer knockback extraction correction (2026-11-21)
- `IMG_1365.jpeg` has six walk frames in the top row, but its lower-row knockback pose is centered across the two middle columns rather than contained in one standard cell.
- Extract the knockback pose from the combined middle-bottom region, then isolate its largest connected character silhouette against the sheet background. Do not crop it to a single walk-cell boundary.
- Keep the reaction on the same normalized scale and bottom baseline as the walk cycle. Its transparent output canvas may be wider than a walk frame; render that reaction image wider than the normal customer box so the complete pose remains visible without shrinking or clipping it.
- Preserve all six existing walk-frame crops and the original source image.


### Female customer sprite-sheet replacement (2026-11-22)
- `IMG_1366.jpeg` replaces the prior female customer walk-cycle source in the runtime. Preserve `IMG_1363.jpeg` as an original legacy asset; do not use it for the active female walk animation.
- Extract six walk frames independently from the six cells across the top row. Keep the order left-to-right.
- The lower-left knockback pose spans beyond one standard cell. Extract it from the combined first two cells of the bottom row, isolate the complete connected character silhouette, and normalize it with the same scale and bottom baseline as the six walk frames.
- Keep the knockback image canvas wide enough to retain the full pose and render it with the dedicated wide hit-pose treatment. The female hit pose must be wired to the female customer reaction slot, not substituted for the male reaction.


### Initial turret facing (2026-11-22)
- Newly placed turrets must initially face toward the customer spawn point at the beginning of the route. Determine the left/right flip from the turret's world X position relative to `route[0].x`.
- Once an eligible customer enters range, normal target-facing logic may turn the turret toward that customer. When no target is available, retain the spawn-facing orientation.


### Turret sprite-sheet animation integration (2026-11-22)
- Use the supplied `IMG_1357.jpeg` as a 4 × 4 sheet with 300 × 224 source cells at its 1200 × 896 raster dimensions.
- Ketchup and mustard turrets use their corresponding idle and firing frames from the first two rows. Pizza and burger cannon turrets use the idle, firing, blast, and smoke sequence from the third row.
- All animation frames must be rendered inside the existing fixed turret element footprint. Never resize the turret element between frames; preserve the same facing flip and anchor while changing only the image source.
- Trigger the firing sequence from the existing projectile launch event and return to the idle frame automatically. Keep nearest-neighbor pixel rendering.


### Turret animation frame scale consistency (2026-11-22)
- Do not independently scale each turret animation cel to its own trimmed bounds. This makes narrow firing poses appear smaller or larger than idle art.
- For each turret family, compute a robust shared scale from the median visible width and height across its frames, so one unusually large or poorly trimmed cel cannot shrink every pose. Apply that same scale to every frame in the family.
- Preserve each complete 300 × 224 source cell on a matching 300 × 224 transparent output canvas. Remove only the edge-connected neutral sheet background; do not trim the visible bounds or independently rescale the pose, because this can clip artwork or make frames appear tiny. Display the cell with `object-fit: contain` in the enlarged fixed turret footprint so all frame artwork remains visible at a consistent source scale. Preserve the same turret element size, anchor, and facing flip while only swapping the image source.
