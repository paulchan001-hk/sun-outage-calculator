# AsiaSat Sun Outage Calculator

Static page for GitHub Pages. No build step and no server.

It replaces the fixed AsiaSat 5 / 6 / 7 / 8 / 9 dropdown with an editable orbital slot, and adds Ka-band beside C and Ku.

## What changed

- Any GEO longitude, East positive and West negative. Fleet presets still fill the slot.
- C (4.00 GHz), Ku (12.25 GHz) and Ka (20.20 GHz) nominal downlink centres. The frequency field is editable for the actual carrier.
- Both seasonal windows are calculated. The current tool asks the user to pick one.
- Client-side batch CSV, so the page can be hosted as plain GitHub Pages.
- Look angles, 3 dB beamwidth and closest approach are shown with the event table.

## Publish

1. Create a repository, or use an existing one.
2. Upload this folder. `index.html` must sit at the site root, or in the folder you want as the page URL.
3. In GitHub: Settings → Pages → Deploy from branch → `main` → `/ (root)`.
4. The page is then at `https://<user>.github.io/<repo>/`.

No Jekyll config is required.

## Method

Geometric only. The satellite is assumed geostationary at zero inclination.

- Look angles: Earth radius 6,378.137 km, GEO radius 42,164.17 km.
- Beamwidth: `θ = 70 λ / D` degrees. `λ = 0.299792458 / f_GHz` metres.
- Event while Sun–satellite separation is below `θ/2 + solar radius`.
- Tolerance versus an observed outage is about 5 to 10 minutes. Inclination, station-keeping and link margin are not modelled.

AsiaSat 8 is preset at 105.5° E, matching the fleet page. Confirm the live slot before an operational notice. The previous calculator listed 105.3° E.

## Batch columns

`id, site, lat, lat_hemisphere, lon, lon_hemisphere, orbital_slot_east, year, band, frequency_ghz, antenna_m, timezone`

Hemisphere values: `North` / `South`, `East` / `West`. Band: `C`, `Ku`, `Ka` or `Custom`. Frequency is still required.
