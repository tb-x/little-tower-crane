# Little Tower Crane

A 3D building game for young kids (around age 5), made for phones and tablets.

A tower crane stands on a busy city construction site. Tap a block and the crane lifts it, then find the spot where it fits in the floor plan. Fill a floor and the tower grows; finish every floor and you have built a skyscraper.

Around the site the city keeps going: an excavator loads a dump truck, a bulldozer and a cement mixer work the site, cars stop at traffic lights, and people walk by. Day turns to night and back, and it sometimes rains or snows.

**Play:** https://tb-x.github.io/little-tower-crane/

## Running locally

It is a single `index.html` with no build step. [three.js](https://threejs.org/) 0.160 loads from jsDelivr. Serve the folder over HTTP, for example:

```bash
python -m http.server 8765
```

Then open http://localhost:8765. All sounds are synthesized in the browser.
