# Freetown Spatial Flood Risk & Catchment Prioritization Model

A production-grade, end-to-end geospatial machine learning pipeline designed to evaluate topographical and hydrological flood vulnerability across catchments in Freetown, Sierra Leone.

## Project Overview
Urban flooding in coastal and mountainous cities like Freetown requires data-driven decision support. This project processes multi-resolution environmental rasters to predict localized flood hazard risk at a pixel level and aggregates results by catchment zones for municipal planning.

## Key Features & Methodology
- **Multi-Raster Spatial Alignment:** Dynamically resamples and aligns digital elevation models (`freetown_dem.tif`) and hydrological runoff routing grids (`freetown_routing.tif`) using `rasterio`.
- **Machine Learning Core:** Trained and tuned an **XGBoost Regressor**, achieving an \(R^2\) of ~0.9994, with feature importance proving that elevation drives 99.97% of spatial variance.
- **Zonal Catchment Prioritization:** Automatically extracts zonal statistics across vector boundaries (`Freetown_catchments.geojson`) to identify critical risk hotspots (e.g., Catchment 4).
- **Interactive Visualization:** Generates QGIS-compatible GeoTIFF risk rasters and a standalone interactive web dashboard (`freetown_flood_risk_dashboard.html`).

## Project Structure
- `freetown_flood_model.pkl`: The serialized production XGBoost model.
- `freetown_catchment_risk_summary.csv`: Ranked zonal risk report for Freetown catchments.
- `freetown_flood_risk_dashboard.html`: Interactive web visualization map.

