# GIS-Based Site Selection for Green Infrastructure in Greater Manchester

A geospatial decision-support project that identifies priority areas for green infrastructure interventions across Greater Manchester using multi-criteria evaluation (MCE) and weighted linear combination (WLC).

## Project Overview

This project was developed to identify areas with the greatest potential need and suitability for green infrastructure interventions in Greater Manchester.
The analysis integrates socio-economic, accessibility, vegetation, and landscape connectivity indicators into a composite suitability surface, and translates the results into scenario-based planning outputs.

## Study Area

Greater Manchester, United Kingdom.

## Tools and Software

- ArcGIS Pro
- Google Earth Engine
- ArcGIS Spatial Analyst
- ArcGIS Spatial Statistics tools

## Data Sources

This project integrates multiple spatial datasets, including:
- Lower Super Output Areas (LSOA)
- Index of Multiple Deprivation (IMD)
- Population density data
- Ordnance Survey Open Greenspace
- Natural England Local Nature Reserves
- Sentinel-2 imagery for NDVI
- Landsat-derived land surface temperature from Google Earth Engine
- Building footprint data
  
## Methodology

The workflow consisted of five main stages:

1. **Data preparation**
   Collected and processed socio-economic, green space, vegetation, and accessibility datasets for Greater Manchester.

2. **Indicator generation**
   Created standardised indicators for:
   - population density
   - deprivation (IMD)
   - NDVI-based vegetation deficit
   - ANGSt-based accessibility deficit
   - distance to public green space
   - effective mesh size (Meff)

3. **Suitability modelling**
   Applied Multi-Criteria Evaluation (MCE) and Weighted Linear Combination (WLC) to generate a composite green infrastructure suitability surface.

4. **Spatial validation**
   Used Local Moran’s I (LISA) to test whether high-suitability zones showed significant spatial clustering.

5. **Scenario-based site selection**
   Converted regional suitability results into intervention scenarios, including:
   - rooftop green infrastructure
   - ground-based/community garden interventions

## Indicator Weights

The final suitability surface was derived using the following weights:

- IMD: 0.3
- ANGSt deficit: 0.2
- NDVI deficit: 0.2
- Population density: 0.1
- Distance to public green space: 0.1
- Effective mesh size (Meff): 0.1


## Key Outputs

### 1. Composite Suitability Map
A city-regional suitability surface showing priority areas for green infrastructure intervention.

### 2. Top 10% Priority Areas
Identification of the highest-ranked target zones for intervention.

### 3. Spatial Statistical Validation
Local Moran’s I analysis showing spatial clustering of high-suitability and low-suitability areas.

### 4. Scenario Maps
Two scenario-based outputs were produced:
- rooftop greening target areas
- community garden / ground-based intervention sites

## Key Findings

- Higher suitability values were concentrated mainly in peripheral parts of Greater Manchester, particularly in the south, northeast, and northwest.
- Lower suitability values were more common in the urban core.
- The top 10% priority zones showed clear spatial clustering rather than random distribution.
- Scenario-based outputs demonstrated how regional suitability analysis can support planning decisions at building and plot scales.

## Repository Structure

```text
├── README.md
├── images/
│   ├── suitability_map.png
│   ├── top10_map.png
│   ├── lisa_map.png
│   ├── rooftop_scenario.png
│   └── community_garden_scenario.png
├── docs/
│   └── project_summary.pdf
├── scripts/
│   └── [optional analysis scripts or notes]
└── outputs/
    └── [optional exported maps / figures]
```

## Limitations

- Weight assignment in the suitability model involved a degree of subjective judgement.
- Some datasets were drawn from different years, which may affect temporal consistency.
- Accessibility measures were based mainly on Euclidean assumptions rather than full network or terrain-aware accessibility.
- Some outputs would benefit from further ground-truthing before real-world implementation.

## Relevance

This project demonstrates skills relevant to GIS, urban analytics, sustainability consulting, and geospatial decision-support roles, including:

- multi-source spatial data integration
- suitability modelling
- spatial statistics
- scenario-based planning
- map-based communication for decision-making

## Acknowledgements
Contains Ordnance Survey data © Crown copyright and database right (2024).
Other datasets were obtained from UK Government Open Data, Copernicus Sentinel-2, and Google Earth Engine.

## Author
Ziyao Zhao
MSc GIS, The University of Manchester
