# AsiaSat Sun Outage Calculator

AsiaSat 5 / 6 / 7 / 8 / 9 dropdown with an editable orbital slot.

## Method

Geometric only. The satellite is assumed geostationary at zero inclination.

- Look angles: Earth radius 6,378.137 km, GEO radius 42,164.17 km.
- Beamwidth: `θ = 70 λ / D` degrees. `λ = 0.299792458 / f_GHz` metres.
- Event while Sun–satellite separation is below `θ/2 + solar radius`.
- Tolerance versus an observed outage is about 5 to 10 minutes. Inclination, station-keeping and link margin are not modelled.

## Batch columns

`id, site, lat, lat_hemisphere, lon, lon_hemisphere, orbital_slot_east, year, band, frequency_ghz, antenna_m, timezone`

Hemisphere values: `North` / `South`, `East` / `West`. Band: `C`, `Ku`, `Ka` or `Custom`. Frequency is still required.
