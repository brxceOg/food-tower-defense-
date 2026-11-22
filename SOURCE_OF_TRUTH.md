# Food Tower Defense — Source of Truth

Living design and implementation reference. Update this document whenever an approved game rule or project constraint changes.

## Project identity
- Project: Food Tower Defense
- Repository: https://github.com/brxceOg/food-tower-defense-
- Target: iPhone Safari first; desktop browser support is welcome.
- Hosting: GitHub Pages.
- Format: 2D pixel-art tower defense.
- Orientation: Portrait-first.
- Premise: Defend a busy restaurant by placing food-themed turrets that automatically feed approaching customers before they reach the restaurant.

## Core game loop
1. Customers enter the map and follow a winding route toward the restaurant.
2. Purchase food turrets from the in-game build menu.
3. Place turrets on designated buildable grass tiles.
4. Turrets automatically target customers in range and fire food projectiles.
5. Food hits reduce customer hunger/health.
6. When hunger/health reaches zero, the customer is satisfied, reacts happily/eats where animation permits, and leaves the route.
7. Customers that reach the restaurant damage its health.
8. Complete waves, earn currency, and build or upgrade defenses.
9. When restaurant health reaches zero, the run ends.

## Battlefield and camera
- The battlefield is a vertically scrollable play area larger than the visible phone viewport.
- The map is portrait-oriented and should feel like a continuous game world, not a webpage.
- Customers follow a winding path toward the restaurant.
- Every clear grass tile on the printed 15 × 13 map grid is buildable when unoccupied. Build eligibility is sampled from the actual map artwork; stone path, restaurant, and tiles covered by environmental props are excluded automatically.
- Turrets remain fixed to world positions while the camera moves.
- Use custom touch-driven camera movement. Do not use browser-native document/page scrolling.
- HUD and build controls remain fixed while the battlefield camera moves.
- Map expansion is a possible future progression feature, not a confirmed first-version requirement.

## Waves and run structure
- The game is wave-based, not endless continuous traffic.
- Display a clear wave counter during gameplay.
- Each wave contains a defined group of customers.
- The player can prepare defenses before starting the next wave.
- Building and upgrading remain available during active waves unless explicitly changed later.
- Completing a wave awards currency.
- Later waves increase challenge through customer quantity, durability, speed, and variety.
- Special customers or boss-like encounters may appear at milestones; exact cadence is TBD.
- Show wave progress or remaining customers in the HUD.
- No lives/continue system is currently planned: the run ends when restaurant health reaches zero.

## Customers and feeding
- Customers are the targets moving along the route.
- Use the supplied customer artwork where suitable.
- Customers have hunger/health; food hits reduce it.
- Customer classes may vary in health, speed, reward, and behavior. Exact roster and balance are TBD.
- Fully fed customers should visibly react and then leave the battlefield.
- A customer reaching the restaurant damages its health.
- Avoid having customers simply vanish when defeated; provide readable feeding/satisfaction feedback.

## Turrets and combat
Turrets are food-based weapons, not conventional fantasy or military towers.
- Automatically acquire eligible customers within range.
- Placed turrets use an enlarged visual footprint that remains centered on the selected build tile, with a subtle contact shadow so each weapon appears seated on top of the grass rather than flat inside a small grid cell.
- Flip each turret sprite horizontally to face its current in-range target (left or right); do not rotate or tilt the sprite. Keep the turret anchored to its tile.
- Fire visible food projectiles.
- Have distinct range, firing rate, feeding power, projectile behavior, and upgrade paths.
- Initial concepts:
  - Ketchup Cannon: fast attacks, lower feeding power.
  - Mustard Cannon: medium feeding power, longer range.
  - Chip Tosser (replaces Pizza Launcher): heavy or area feeding with tossed-chip projectiles.
  - Burger Blaster: powerful single-target feeding, slower cadence.
  - Soda Sprayer: slows customers.
  - Fry Flinger: rapid volleys.
  - Ice Cream Machine: temporary crowd control/freezing.
- These are concepts, not a promise that every weapon ships in the first build. Costs, stats, and unlock order are TBD.
- Selecting a placed turret opens a custom inspection/upgrade interface. Selling may be included.
- Placement must validate buildable terrain and affordability.

## Economy and progression
- Currency is earned through successful feeding and/or wave completion; exact formulas are TBD.
- Turrets are purchased from the build menu and placed on valid tiles.
- Turrets should support upgrades with clear costs and visible improvements.
- Balance should reward strategic placement and varied defenses.
- Land expansion remains optional/future until specified.

## HUD and screens
Gameplay HUD communicates:
- Current wave.
- Currency.
- Restaurant health.
- Wave progress or remaining customers.
- Start-next-wave control.

Build menu:
- Fixed to the screen while the battlefield scrolls.
- Shows turret pixel-art icon, name, and cost.
- Supports touch-friendly selection and placement.
- Clearly indicates unavailable or unaffordable options.

Expected screens: main menu (details TBD), gameplay, turret inspection/upgrade, wave-clear feedback, and game-over/results.

## Game over and score records
When restaurant health reaches zero:
- End the run and show a dedicated results screen.
- Show final wave, total customers fed, total money earned, final score, and personal bests where available.
- Provide retry and return-to-menu actions.
- Save personal bests locally in the initial implementation.

Track useful run statistics from the beginning:
- Highest wave reached.
- Total customers fed.
- Total currency earned.
- Waves completed/survived.
- Final score.
- Playtime, if practical.

## Future leaderboards
- Global, weekly, and friends leaderboards are future features, not part of the initial local/offline implementation.
- Genuine shared leaderboards require an online backend; do not simulate them with local-only data.
- Keep score calculation and run-stat collection separate from display/storage so a backend can be added later.
- Do not claim leaderboard functionality exists until a shared backend is implemented.

## Platform and input
- iPhone Safari is the primary target.
- Portrait play and touch interaction are first-class requirements.
- Prevent accidental page scrolling, text selection, callout menus, and browser gestures from interfering where practical.
- Implement custom touch/pointer handling for camera movement, placement, and menus.
- Keep controls comfortably tappable on small screens.
- Desktop mouse input may be supported without compromising mobile behavior.
- Preserve pixel-art sharpness and readable UI at different viewport sizes.

## Technical direction
- Use HTML, CSS, and JavaScript, hosted on GitHub Pages.
- Browser technologies are implementation details; the player-facing experience must feel like a complete game, not a website.
- Keep gameplay state, rendering, input, UI, and persistence organized independently.
- Persist local progress and personal bests in browser storage.
- Structure score/stat tracking for future leaderboard integration.
- Avoid adding a framework or backend without a clear need.

## Supplied assets
The user supplied three initial images in the project discussion:
1. Customer character artwork/sprite sheet.
2. A second customer character artwork/sprite sheet.
3. Pixel-art battlefield/terrain reference featuring grass and a winding stone route.

Inspect the actual files in the repository before integrating. Do not assume filenames, dimensions, frame counts, transparency, or animation order. Preserve the intended pixel-art style and avoid unrelated placeholders. Maintain an asset inventory and record animation details and attribution when verified.

## Development workflow
- Inspect the current repository and implementation before changing it.
- Read this document and ART_DIRECTION.md before relevant implementation or art changes.
- Make focused, complete changes; do not substitute snippets or mockups when implementation is requested.
- Preserve approved mechanics, artwork, visual decisions, and saved progress.
- Test at narrow/mobile viewports and verify touch interactions.
- Verify GitHub Pages deployment before describing a change as live.
- Share a playable URL only after confirming deployment succeeded.

## Open decisions
Do not silently assume answers for: final branding/title; exact map dimensions and route; one map versus multiple stages; initial turret roster/costs/stats/upgrades; customer classes and wave balance; currency and scoring formulas; restaurant health and damage values; main menu/meta-progression/unlocks; land expansion; sound/music; leaderboard backend and account model.


## Turret initial orientation
- On placement, every turret initially faces toward the customer spawn point at `route[0]`, so players can immediately read its defensive direction before a wave begins. Calculate the left/right flip from the turret's world X position relative to `route[0].x`, and account for source-art facing: Chip Tosser's source sprite faces the opposite way from Ketchup Cannon and Burger Blaster, so its flip sign must be inverted.
- During combat, turrets may turn to face their current eligible target; when no target is available, they retain their spawn-facing orientation.


## Chip Tosser replacement (2026-11-22)
- The user-supplied `IMG_1368.jpeg` replaces the former Pizza Launcher artwork and shop title with Chip Tosser.
- Preserve the existing Pizza Launcher gameplay values and the legacy internal `pizza` type for compatibility with existing placed towers. The shop and player-facing tower name must say Chip Tosser.
- Extract the four top-row idle poses and sixteen individual toss/reload poses from the lower three rows. Preserve full artwork, remove only edge-connected gray sheet background, and normalize all frames to a shared transparent 200 × 200 canvas with one scale and bottom baseline.
- Use the separate chip-toss motion artwork as the tower's food projectile. Keep the ketchup/mustard cannon and its combined sauce projectile unchanged.


## Build selection and placement feedback
- The build grid is hidden during normal play and appears only while a turret is selected from the build menu.
- A successful placement consumes that selection: clear the active shop-button state and hide the build grid immediately after the turret is placed.
- The player must select a build-menu turret again before placing another one. Existing placed turrets remain directly tappable for inspection.


## Map aspect ratio and fit
- The original battlefield art is 1200 × 896 (75:56). Show the entire image at a uniform scale, centered inside the available arena; never stretch or crop the artwork to force a portrait aspect ratio.
- On portrait phones, use the surrounding grass-color area to fill any unused space above/below the landscape-proportioned map. The map, tile grid, route, towers, customers, and effects must share the same fitted world dimensions.


## Edge-to-edge map presentation
- The battlefield covers the entire available arena from edge to edge. Scale the 1200 × 896 map uniformly using a centered cover fit; crop the overflow at the arena boundaries rather than stretching the map or leaving a contrasting background visible.
- Keep the world coordinate plane at the same 75:56 aspect ratio and enlarge it to cover the arena. The printed tile grid, route, towers, customers, and effects all remain aligned to that plane.


## Centered fully-visible battlefield fit (latest correction)
- Display the complete 1200 × 896 (75:56) map at the largest uniform scale that fits inside the available arena between the fixed HUD and build menu.
- Center the map horizontally and vertically in the arena. Preserve its original aspect ratio and show all four edges; do not crop, stretch, or use a cover fit. The arena's grass-colored background may remain visible around the map on portrait screens.
- Keep the world coordinate plane, map image, build-grid SVG, route, towers, customers, and effects aligned to the same fitted 75:56 dimensions.
- This centered contain fit supersedes earlier full-viewport and edge-to-edge cover-fit presentation notes.
