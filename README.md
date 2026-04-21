# GIS-Based Site Selection for Green Infrastructure in Greater Manchester

A GIS-based site selection project that identifies priority areas for green infrastructure (GI) interventions in Greater Manchester using Multi-Criteria Evaluation (MCE) and Weighted Linear Combination (WLC).

## Project Overview

In the past years, GI has received growing attention not only for its potential to improve public health and urban climate adaptation but also to alleviate social inequality. This project takes Greater Manchester as the research area and uses GIS-based MCE and WLC methods to systematically identify and evaluate potential green infrastructure intervention sites.

On this basis, the study further designs two types of scenario plans with different planning objectives. One focuses on urban thermal environment regulation and ecological benefits through rooftop greening. The other is the site selection for the largest community garden, oriented towards humanistic and social benefits, aiming to address green space accessibility and social needs at the community level. Through these intervention plans, the study attempts to alleviate social-environmental inequality caused by the uneven distribution of urban green space. 
## Study Area

Greater Manchester, United Kingdom. The project focuses on identifying areas with higher potential need for GI intervention across the city-region.

## Method

The project uses Multi-Criteria Evaluation / Weighted Linear Combination (MCE/WLC) to integrate multiple indicators into a composite suitability surface for planning decision-support. The workflow also includes Local Moran’s I analysis to test whether the resulting suitability pattern shows meaningful spatial clustering rather than random distribution. 

### Key indicators

A total of six factors were selected for weighting and used to calculate the overall suitability:

- Population density
- Index of Multiple Deprivation (IMD)
- Normalised Difference Vegetation Index (NDVI)
- ANGSt-based green space accessibility deficit
- Distance to public green space
- Green space patch connectivity (effective mesh size, Meff)

### Why these factors were used

**Social needs and equity**  
IMD and population density were used to represent who most needs and may benefit from green infrastructure interventions. In this study, IMD was selected as the primary weighting factor for the social dimension with a weight of 0.3, while population density was used as a secondary factor with a weight of 0.1.

**Spatial accessibility and coverage**  
ANGSt and distance to public green space were used to reflect green space accessibility. ANGSt was treated as the core factor in the accessibility dimension with a weight of 0.2, while distance to public green space was used as an auxiliary factor with a weight of 0.1.

**Ecological quality**  
NDVI was used as the primary indicator of vegetation condition and ecological service capacity with a weight of 0.2. Meff was used as a supplementary indicator of green space fragmentation and structural quality with a weight of 0.1.

**Additional scenario-specific factor**  
For the rooftop greening scenario, Land Surface Temperature (LST) was additionally considered to better reflect the potential of GI for urban heat island mitigation. LST data were derived from Landsat 9 imagery for Greater Manchester from June to August.
## Data Sources

The spatial datasets used in this project were obtained from a combination of UK open data sources and satellite-derived products. Administrative boundary and socio-economic data, including LSOA and IMD, were sourced from the Office for National Statistics (ONS). Public green space and natural site information were derived from Ordnance Survey Open Greenspace and Natural England datasets. In addition, near-infrared and red band imagery were derived from Copernicus Sentinel-2, while land surface temperature data were exported from Google Earth Engine.

## Key Results

The comprehensive suitability map was generated through a weighted combination of six indicators. Higher suitability values were mainly concentrated in the peripheral areas of Greater Manchester, particularly in the southern, northeastern and northwestern parts of the region, while lower suitability values were more commonly observed in the urban core. This pattern suggests that areas with larger socio-environmental deficits and lower access to green space have stronger potential need for GI interventions.

Based on the composite suitability surface, the top 10% of high-suitability areas were identified as priority zones for potential intervention. These areas showed clustered spatial distribution rather than random dispersion, especially in peripheral communities in the southern and eastern parts of Greater Manchester.

Local Moran’s I analysis further showed high spatial consistency between the top-ranked suitability areas and high-high clustering zones, which partially validates the statistical robustness of the identified priority areas.

## Scenario-Based Outputs

### 1. Rooftop garden site selection

This scenario overlays comprehensive high-suitability target areas with building outline data at the LSOA scale. The weight of the land surface temperature factor was recalibrated in the WLC process to better reflect the potential benefits that rooftop greening can bring to mitigating thermal environments. This allowed a series of specific building units to be identified as potentially suitable for rooftop GI interventions.

### 2. Largest community garden site selection

The site selection of community gardens is based on the results of the comprehensive GI suitability analysis and is screened in combination with spatial feasibility and social needs. It first extracts spatial units from the available area for ground greening, then introduces IMD and ANGSt to preferentially identify areas with high social needs and insufficient green space supply. Finally, it screens candidate plots in conjunction with land use type and plot scale, selecting medium-sized plots as demonstration sites for community gardens.

## Limitations

This project has several limitations. First, weight allocation relies to some extent on the researcher’s subjective judgment. In particular, ANGSt and distance to public green space are theoretically distinct but still have some conceptual overlap, which may affect the final suitability outcomes.

Second, the datasets used are not fully temporally consistent. For example, Local Nature Reserve and Open Greenspace data are from October 2025, while IMD data are from 2019 and population data rely on the ONS 2011 Census. This temporal mismatch may affect the accuracy and real-world applicability of the results.

Third, the original Landsat LST data had a spatial resolution of 30 m and were resampled to 10 m to match other raster layers such as NDVI. Although this improves consistency across layers, it may reduce the authenticity of local temperature variation.

## Planning Implications

Ground-truthing is necessary when applying this kind of GIS-based planning analysis in practice. In addition, future work could consider the dilution effect of large private and institutional green spaces on public green space demand, as well as topographic impedance, since simple Euclidean distance does not fully represent real accessibility in hilly landscapes. Future planning could also consider per capita green space exposure analysis for specific demographic groups.

## Repository Structure

```text
project/
├── data/                # input data or sample/derived data if allowed
├── maps/                # final maps used in the project
├── figures/             # workflow charts, result figures, screenshots
├── docs/                # original report or supplementary write-up
├── scripts/             # ArcGIS / GEE / processing scripts if available
└── README.md
```

## Suggested Figures to Include

You can place your main outputs in the `figures/` folder and embed them in the README, for example:

- Workflow of weighted overlay and Local Moran’s I analysis
- Spatial distribution of key indicators
- Comprehensive suitability map
- Top 10% high-suitability areas
- Local Moran’s I cluster map
- Rooftop garden candidate sites
- Largest community garden candidate site

## Acknowledgements

Contains Ordnance Survey data © Crown copyright and database right (2024). Other datasets were obtained from UK Government Open Data, Copernicus Sentinel-2, and Google Earth Engine.

## References
Dennis, M. et al. (2020) ‘Relationships between health outcomes in older populations and urban green infrastructure size, quality and proximity’, BMC Public Health, 20(1), p. 626. Available at: https://doi.org/10.1186/s12889-020-08762-x.

Dennis, M., Armitage, R.P. and James, P. (2016) ‘Appraisal of social-ecological innovation as an adaptive response by stakeholders to local conditions: Mapping stakeholder involvement in horticulture orientated green space management’, Urban Forestry & Urban Greening, 18, pp. 86–94. Available at: https://doi.org/10.1016/j.ufug.2016.05.010.

Drobne, S. and Lisec, A. (no date) ‘Multi-attribute Decision Analysis in GIS: Weighted Linear Combination and Ordered Weighted Averaging’.
