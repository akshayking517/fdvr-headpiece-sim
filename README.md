# 20 mW Headpiece Bench

Interactive companion to the essay *The Architecture Behind Full-Dive Virtual
Reality* — specifically its retinal-projection headpiece, the near-term
device that draws its power wirelessly from a room-scale transmitter instead
of carrying a battery.

Two pages, both self-contained (no build step, no dependencies beyond two
Google Fonts):

- **`index.html`** — builds 5,000 headpieces at random from the essay's own
  ranges for every uncertain part, and shows how many actually close on room
  power alone. Click any dot, or a preset, to load that headpiece into the
  bench below it.
- **`single-design.html`** — the original single-design bench: set each part
  by hand and watch it against the room-power and thermal ceilings, plus a
  5,000-run Monte Carlo histogram and sensitivity (tornado) chart.

## Running it

Nothing to install. Open `index.html` in a browser, or serve the folder:

```
python3 -m http.server 8000
```

## Publishing with GitHub Pages

Settings → Pages → Deploy from a branch → `main`, folder `/ (root)`. The site
will serve `index.html` at the repo's Pages URL.

## Model

Head-side load = receive power (delivered bit rate × energy per bit) +
projector power (light ÷ wall-plug efficiency) + tracking + conversion loss.
Room delivery = field strength (1.0 mW/cm², the exposure limit) × capture
area × harvesting efficiency. The thermal ceiling is 94.8 W/m² of scalp
contact (84.8 W/m² if the device blocks all heat loss to room air), from a
four-layer tissue heat-transfer model held to a 1 °C rise. Full derivation is
in the essay.

`social/` holds pre-cropped screenshots of the hero card (light and dark) for
sharing the page on X/social — regenerate them if the numbers on the page
change (the Monte Carlo run is reseeded each time you click "Build another
5,000," and on every fresh page load).
