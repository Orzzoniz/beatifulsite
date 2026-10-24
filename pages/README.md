# Pages

Five demo landing pages built with the Hallmark design skill (`.claude/skills/hallmark`), one per theme. Every product is made up; each page says so in its footer.

| Page | Theme | Made-up product |
| --- | --- | --- |
| [waymark](waymark/index.html) | Furrow | Path wardens log broken stiles, gates and fallen trees on a survey map |
| [frank](frank/index.html) | Coral | An API that prints and posts real paper letters |
| [lapse](lapse/index.html) | Cobalt | Alerts one minute after a cron job misses its run |
| [bramble](bramble/index.html) | Dose | A household app for who gave the pet its medicine, and when |
| [settle](settle/index.html) | Dusk | Pays every supplier overnight on one evening approval |

## Open a page

Each folder is self-contained: open its `index.html` in a browser, or serve the folder:

```
python3 -m http.server --directory pages 8000
```

Then visit `http://localhost:8000/waymark/` (or any other folder name).

## How they are built

- Plain HTML, CSS and JavaScript in one file per page, no build step.
- Animation uses [Motion](https://motion.dev) 13.5.1, loaded from jsDelivr: spring reveals as sections scroll in, spring presses on buttons, and one scroll-linked moment per page (Waymark's work sheet opens flat, Frank's letter slides into its envelope, Lapse's clock runs with the scroll, Bramble's tray tilts flat, Settle's bars grow).
- If Motion cannot load, the same reveals run on plain CSS. Under the system's reduced-motion setting nothing moves, and every page reads fully with JavaScript turned off.
- Movement is transform and opacity only, plays once, and pauses off screen.
- Fonts load from Google Fonts. Frank embeds General Sans from Fontshare (ITF Free Font License).
- Waymark's survey map and Lapse's character field are drawn live on a canvas; `waymark/map-still.webp` is the still shown before the script runs.
- Sign-up forms are not connected to anything and say so when submitted.

## Photographs

From Wikimedia Commons, credited in each page's footer:

- `waymark/swaledale.jpg`: Kreuzschnabel, CC BY-SA 3.0
- `settle/hills.jpg`: Caleb Riston, CC0
- `settle/harbour.jpg`: ArildV, CC BY-SA 4.0
