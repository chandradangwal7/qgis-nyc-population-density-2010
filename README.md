# QGIS Day 2 — NYC Population Density (2010)

<img src="maps/nyc_density_2010.png" alt="NYC Population Density 2010 choropleth" width="900">

This repository contains my Day 2 QGIS exercise: a choropleth of New York City **Neighborhood Tabulation Areas (NTAs)** showing **2010 population density** (people per square mile). I filtered population to Year=2010, joined by `NTACode`, computed density from area (ft² → mi²), styled a graduated map with custom class breaks, and built a print layout.

## Highlights
- **Join:** NTA polygons ↔ population table on `NTACode` (Year = 2010).
- **Density:** `5280*5280 * ("Population" / "Shape_Area")` and `Density_Round = round("Density", 0)`.
- **Symbology:** YlOrBr, 6 classes, last bin relabeled to `> 100000`.
- **Layout:** title, legend, scale bar, north arrow, credits.

## Files
- `NYC_Population_Density.qgz` — QGIS project  
- `data/nynta_with_population.gpkg` — joined layer with population  
- `maps/nyc_density_2010.png` — exported map preview (used above)  
- `maps/nyc_density_2010.pdf` — high-res layout (print)  

## Sources & Credits
Data: **NYC Open Data** (NTAs; 2010 Census/ACS).  
Tutorial: **Ujaval Gandhi — Spatial Thoughts**.  
Map: **Chandra Dangwal** (QGIS).

## Reproduce
Open the `.qgz`, ensure the `data/` layer paths are valid, and the map will render with saved symbology and layout.
