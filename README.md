# Antenna Aimer

A simple, offline compass PWA for aiming a directional antenna (such as a UHF TV Yagi) at a target bearing, using the compass sensor in your phone or tablet.

**Live app:** https://myoung8223.github.io/antenna-aimer/

## Features

- Big heading readout plus a **"TURN LEFT / TURN RIGHT X°"** bar that turns green when you're on target
- Compass dial with your target bearing marked
- Works held **flat** (reads where the top edge points), **upright** (reads where the back camera points), or **face-down overhead** (handy for sighting an antenna mounted above you)
- **Declination** setting, so the reading matches true bearings from maps and antenna sites
- Adjustable "on target" tolerance and smoothing
- **Set target = current** button to save a heading you found by peaking signal strength
- Warns when readings are unsteady or the device has no compass sensor
- Keeps the screen awake while open
- Installs as a PWA and runs **fully offline**; settings are saved on the device

## Usage

1. Find your target bearing. Antenna sites such as [RabbitEars](https://www.rabbitears.info/) give the azimuth to each station from your address. Bearings use the standard convention: 0° is north, increasing **clockwise** (90° east, 180° south, 270° west).
2. Enter that bearing as the target. If you're using a true (map) bearing, enter your local magnetic declination (east positive, west negative) from the [NOAA calculator](https://www.ngdc.noaa.gov/geomag/calculators/magcalc.shtml#declination).
3. Line the device up with the antenna boom, pointing toward the directors (the short-element end), and turn until the bar reads **ON TARGET**.
4. For best results, fine-tune with your TV's signal-strength screen, sweeping slowly by about ±15° around the compass heading.

### Holding the device face-down overhead

Keep the top edge pointing forward along the boom and flip the device side to side (around its long axis). The left/right instructions and dial then still match your own left and right.

### Accuracy tips

- Device compasses are easily thrown off by nearby metal. Stay a few feet from masts, brackets, gutters and meter boxes.
- If readings drift, wave the device in a figure-8 to recalibrate.
- A typical small UHF Yagi has a beamwidth of roughly 30–60°, so a few degrees of compass error rarely matters.

## Requirements

- A device with a **magnetometer (compass sensor)**. Many budget phones (for example, the Samsung Galaxy A12) and most laptops don't have one; the app will say so.
- A browser that supports orientation sensors: Chrome or Samsung Internet on Android (via `deviceorientationabsolute`), or Safari on iOS (tap **Start compass** to grant permission).
- Served over HTTPS (GitHub Pages does this).

## Offline use

Open the app once while online, then use your browser's **Add to Home screen** / **Install app** option. After that it runs entirely offline. The compass reads only on-device sensors and needs no network or location access. The NOAA link is the only thing that needs a connection.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole app (HTML, CSS and JavaScript) |
| `manifest.json` | PWA manifest (name, icons, display mode) |
| `sw.js` | Service worker that caches the app for offline use |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` | App icons |

When you change any file, bump `VERSION` in `sw.js` so installed copies pick up the update.

## Credits

Developed by Mike Young with assistance from Claude (Anthropic).

## License

[MIT](LICENSE)
