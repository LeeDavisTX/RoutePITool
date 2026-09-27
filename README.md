# Route PI Tool

Calculate pipeline PI (point of intersection) angles, stations and mileposts from a KML or KMZ route line.

**Use it:** https://leedavistx.github.io/RoutePI/

## What it does

- Upload a KML or KMZ holding **one continuous, single-part route line** (multi-part lines or files with several lines are rejected).
- Measures the horizontal deflection at every vertex on the WGS84 ellipsoid, left or right, in decimal degrees and D° MM' SS".
- Classes each PI as **free stress**, **field bend** or **fitting** from two cutoffs you set (defaults 1° and 18°).
- Stations the line (`204+74.58`) and adds mileposts from the start station and start MP you choose (ft, US survey ft or m).
- Labels: `P.I. < 45° 04' 20" LT.` and `P.I. < 45° 04' 20" LT. @ STA. 204+74.58`.

## Exports

Excel, CSV, KML (fittings, field bends, free stress and milepost markers), GeoJSON and a milepost list. All share one column layout:

`ORDER, POINT_TYPE, PI_NO, UNITS, STATION, MILEPOST, LEG_AHEAD, AZIMUTH_IN, AZIMUTH_OUT, H_PI_DD, H_PI_DMS, H_DIRECTION, FITTING_NO, BEND_TYPE, LABEL, DESCRIPTION, LATITUDE, LONGITUDE`

- **PI_NO** numbers field bends and fittings. **FITTING_NO** numbers fittings only.
- **UNITS** is `FT/MI`, `USFT/MI` or `M/KM`.
- For AutoCAD SHX fonts, find-and-replace `°` with `%%d`.

## Privacy

Everything runs in your browser. Route files are never uploaded anywhere.

## Publishing

This repo holds the finished app as a single `index.html`. GitHub Pages serves it directly: **Settings → Pages → Deploy from a branch → main / (root)**. To update the app, replace `index.html`.
