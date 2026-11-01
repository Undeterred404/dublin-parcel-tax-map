# Dublin, CA Property Tax Parcel Map

Interactive map of **all 24,140 property tax parcels in Dublin, California** — assessed values and estimated property taxes by locality (Tax Rate Area), with drill-down to individual parcels/houses.

**Live map:** https://undeterred404.github.io/dublin-parcel-tax-map/

## What it shows
- **Locality overlay:** 43 Tax Rate Areas (the official tax localities — every parcel in a TRA shares one composite tax rate), shaded by total net assessed value, with per-TRA parcel counts and estimated tax totals.
- **Drill-down:** zoom to street level to see every parcel boundary, colored by net assessed value; click a parcel for APN, address, land/improvement values, exemptions, net assessed value, and an estimated tax range. Search works by street address or APN.
- **Tables:** totals by TRA and by ZIP code.

## Data & methodology
- Parcel data: Alameda County Assessor's official ArcGIS parcel service (`Parcels/FeatureServer`), snapshot verified Nov 1, 2026 — 24,140 Dublin parcels, $25,083,551,342 total net assessed value. The map's parcel layer reads the county service live.
- Assessed values are Proposition 13 roll values, not market values.
- **Tax figures are estimates.** No public bulk file of actual per-parcel taxes exists. Estimated tax = net assessed value × rate, shown as a range: 1.0000% (official FY2025-26 countywide base levy) to 1.220% (CA Board of Equalization Alameda county-average rate). Estimates exclude direct charges, special assessments, and Mello-Roos CFD charges.
- The county's exact per-TRA composite rates (report "51-427 Composite Tax Rates", Auditor-Controller) are hosted behind a SharePoint login wall and were not programmatically retrievable; loading those 43 rates is the planned accuracy upgrade.
- 2,273 parcels (9.4%) have $0 net value (common areas / exempt). 135 APNs appear on multiple parcel rows, so drill-down is keyed to the parcel, not the APN alone.

## Files
- `index.html` — the whole app (Leaflet + Esri Leaflet via CDN).
- `data/tra-boundaries.geojson` — TRA polygons dissolved from the county parcel boundaries, with per-TRA stats.
- `data/locality-stats.json` — aggregate stats by TRA, ZIP, and use code.

Built for public transparency: know what your neighborhood pays, then ask your city and county officials better questions.
