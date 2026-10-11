# Little Tower Crane

A 3D building game for young kids (around age 5), made for phones and tablets.

A tower crane stands on a busy city construction site. Tap a block and the crane lifts it, then find the spot where it fits in the floor plan. Fill a floor and the tower grows; finish every floor and you have built a skyscraper.

Around the site the city keeps going: an excavator loads a dump truck, a bulldozer and a cement mixer work the site, cars stop at traffic lights, and people walk by. Day turns to night and back, and it sometimes rains or snows.

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
