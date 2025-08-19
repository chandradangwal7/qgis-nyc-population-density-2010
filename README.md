# QGIS Day 2 — NYC Population Density (2010)

<!-- Use the exact filename with spaces as-is -->
<img src="New York Population Density .png" alt="NYC Population Density 2010 choropleth by NTA" width="900">

**Open the high-res PDF:**  
[New York Density data Pdf 2 Project.pdf](New%20York%20Density%20data%20Pdf%202%20Project.pdf)


This repository contains my Day 2 QGIS exercise: a choropleth of New York City **Neighborhood Tabulation Areas (NTAs)** showing **2010 population density** (people per square mile). I filtered the population table to `Year = 2010`, joined it to NTA polygons by `NTACode`, computed density from polygon area (ft² → mi²), styled a graduated map with custom class breaks, and designed a print layout.

## Highlights
- **Join:** NTA polygons ↔ population table on `NTACode` (Year = 2010).
- **Density:** `5280*5280 * ("Population" / "Shape_Area")` and `Density_Round = round("Density", 0)`.
- **Symbology:** YlOrBr ramp, 6 classes, last class relabeled as `> 100000`.
- **Layout:** title, legend, scale bar, north arrow, and credits block.

## Files in this repo
- `NewYork Population Density Project.qgz` — QGIS project  
- `nynta_with_population.gpkg` — joined NTA layer with population  
- `New_York_City_Population_By_Neighborhood_Tabulation_Areas.csv` — source table (attribute-only)  
- `New York Population Density .png` — exported layout (preview above)  
- `New York Density data Pdf 2 Project.pdf` — high-resolution layout PDF  
- `ne_10m_land.shp` — sample land shapefile (note: requires sidecar files to be fully usable)

## Sources & Credits
Data: **NYC Open Data** (NTAs; 2010 Census/ACS).  
Tutorial: **Ujaval Gandhi — Spatial Thoughts**.  
Map: **Chandra Dangwal** (QGIS).

## Reproduce
1. Open `NewYork Population Density Project.qgz` in QGIS.  
2. If any layers show as missing, browse to `nynta_with_population.gpkg` and the CSV to relink.  
3. The saved symbology and print layout will load with the project.
