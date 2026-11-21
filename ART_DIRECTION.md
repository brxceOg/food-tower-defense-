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
