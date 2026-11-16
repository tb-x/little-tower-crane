# Little Tower Crane

A 3D building game for young kids (around age 5), made for phones and tablets.

A tower crane stands on a busy city construction site. Tap a block and the crane lifts it, then find the spot where it fits in the floor plan. Fill a floor and the tower grows; finish every floor and you have built a skyscraper.

Around the site the city keeps going: an excavator loads a dump truck, a bulldozer and a cement mixer work the site, cars stop at traffic lights, and people walk by. Day turns to night and back, and it sometimes rains or snows.

- While a block hangs on the hook, the camera moves in over the floor being built so every spot shows. Over the tower the block turns into a pale see-through outline, the drop spots and the green "it fits here" shadow are always drawn on top, and the crane's mast and arm fade when they are in the way.
- Blocks waiting in the yard look like real building parts: orange lifting eyes on top for the crane's slings (cut off once the block is set down), rusty starter bars with hooked ends (covered when the floor's slab drops on), and darker corner posts.
- The round arrow buttons in the bottom corners (shown while carrying a block) walk the camera a quarter of the way round the tower, to look from another side. Each new block starts from the front again. On a keyboard: Q and E turn, the arrow keys move the block and Enter drops it.
- The floor gauge in the top-left corner is a little tower: lit floors are done, the blinking one is being built. A yellow sign with the same number hangs on the corner of the tower.
- Every tower has its own look: village shutters, brick town house, pastel balconies, glass tower, art deco, ship portholes, garden tower or office ribbons, each with matching block colours and its own roof (roof garden, water tower, helipad, gold spire, ship's flag). The next tower gets the next look, and the game remembers on this device how many towers were built.
- People move in as the blocks land: they wave from their new windows, wander about, and all wave when their floor is finished. Windows get curtains, blinds, pot plants, glazing bars, flower boxes, air conditioners, pictures on the wall, lamps and TVs glowing inside, a pigeon, a teddy or the odd cat; balconies get washing lines, chairs, flags, bicycles and barbecues.
- The site and the streets are busy: workers with hard hats, striped vests, tool belts and gloves (hammers and shovels in hand when they work), operators and drivers in the glass cabs of every machine and in the crane's cab, exhaust puffs from the machines, and people walking with backpacks and bags, some with a dog on a lead or a child holding their hand. Cars come as saloons, hatchbacks, SUVs, pick-ups and sports cars with drivers and passengers behind the glass, and the bus carries passengers.
- The machines are worked out in detail: the excavator's and bulldozer's hydraulic rams stretch and shorten as the arm and blade move, tracks have toothed sprockets and shoe edges, the excavator has hoses, a work light, a mirror and a striped counterweight, the bulldozer has a rounded hood and cab, a curved blade and round-ended tracks, the dump truck and mixer have grilles, sun visors, wheel fenders and twin rear wheels, the mixer drum has steel rings and a loading hopper, and the tower crane has a ladder in its mast, foot plates and ballast at its base, a walkway along the jib, a hoist winch, a light on the jib's tip, a wheeled trolley and a striped pulley hook block.
- When the roof is on, the building site packs up: the crane swings its arm away and folds down, and the fence, huts, machines and workers vanish in puffs of dust. Then a garden grows round the new tower: a lawn, paved paths, a fountain with two ducks, flower beds, blossom trees, hedges, benches (some with someone sitting), lamp posts, a playground with a slide, swings and a sandbox, people out for a walk and butterflies. Building the next tower brings the site back.
- 🏠 in the corner goes back to the list of all games.

**Play:** https://tb-x.github.io/little-tower-crane/

## Play offline (add to Home Screen)

On iPhone or iPad, open the game in Safari, tap **Share → Add to Home Screen**, then open it once from the new icon while online. After that it starts full screen and works without internet. Changes arrive on their own: the next online launch downloads them and the one after shows them.

(How: `manifest.webmanifest` gives the icon and full-screen mode; `sw.js`, a service worker, keeps a copy of every file the game uses, including three.js and the fonts. The icons `icon-180.png` and `icon-512.png` are rendered from `icon.svg` in headless Chrome.)

## Running locally

It is a single `index.html` with no build step. [three.js](https://threejs.org/) 0.160 loads from jsDelivr. Serve the folder over HTTP, for example:

```bash
python -m http.server 8765
```

Then open http://localhost:8765. All sounds are synthesized in the browser.

## Tuning knobs

Near the camera code in `index.html`:

- `CARRY_DIST`: how close the camera comes to the floor while a block is carried (25; phones in portrait move back a little).
- `CARRY_ELEV` / `CARRY_ELEV_TALL`: how steeply it looks down then, in radians (0.86 on wide screens, 1.0 on tall ones).
- `CAM_EASE`: how quickly the camera glides between the yard view and the carry view (2.2).

In the facade section:

- `THEMES`: the tower looks, in the order they're used: facade style, block colours, roof crown and `people` (the chance that a placed block gets a resident).
- `windowLife`: how often windows get curtains (30%), blinds (12%), plants and cats.

Finished floors are merged into a few meshes (`bakeFloor`) so a tall tower stays quick on phones.

The number of towers built is kept in `localStorage` as `towercrane.towers`; clearing it starts again from the village look.
