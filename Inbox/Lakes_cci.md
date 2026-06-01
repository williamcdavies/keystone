---
tags:
  - WFEL
---

## Lakes_cci

### Introduction

#### Scope
> The overarching objective of the Lakes_cci project is to produce and validate a consistent data set of the variables grouped under the Lakes ECV. This includes aiming for the longest period of combined satellite observations by operating processing chains for suitable satellite imagery, ultimately featuring in a sustainable production system. This PUG details the contents, format, and standards applied to the files that make up the dataset. It also introduces some software tools that can help new users explore the data contained in the CRDP.
>
> The specific objectives for the Lakes_cci project are:
• To assess the requirements of the climate research community and thereby ensure consistency in the (further) development of the Lakes ECV processing system.
• To develop, test and select the best algorithms and standards to produce high quality Lake products for climate applications across sensors.
• To provide a specification of the operational production system, aligned with related activities in the Copernicus programme (e.g. Global Land Service, C3S). Algorithms are developed or improved to meet user requirements.
• To validate the Lake ECV products through independent climate research groups and use cases.
• To generate new interest in the EO climate datasets produced for inland water bodies within the community of limnologists, operating at local to global spatial scales and likely to use varying subsets of the Lakes ECV products.

#### Dataset
> The Lakes_cci develops products for the following six ECV Products:
• Lake Water Level (LWL): to understand the balance between water inputs and water loss.
• Lake Water Extent (LWE): a proxy for change in glacial regions (lake expansion) and drought in many arid environments, relating to local climate for the cooling effect that water bodies provide.
• Lake Surface Water temperature (LSWT): correlated with regional air temperatures and a proxy for mixing regimes, driving biogeochemical cycling and seasonality.
• Lake Ice Cover (LIC): freeze-up in autumn and advancing break-up in spring are proxies for gradually changing climate patterns and seasonality.
• Lake Ice Thickness (LIT): a proxy indicator of changes in air temperature and on-ice snow mass (depth and density) during the ice growth period.
• Lake Water-Leaving Reflectance (LWLR): a direct indicator of biogeochemical processes and habitats in the visible part of the water column (e.g. seasonal phytoplankton biomass fluctuations) and an indicator of the frequency of extreme events (peak terrestrial run-off, changing mixing conditions).

### Lakes ECV Dataset

#### Definition
> The Climate Research Data Package (CRDP) intended to fulfil the Lakes ECV observation challenge is a merged (‘L3S’) product composed of the thematic products described in the previous sections:
• Lake water level (LWL)
• Lake water extent (LWE)
• Lake Ice Cover (LIC)
• Lake Surface Water Temperature (LSWT)
• Lake Water Leaving Reflectance (LWLR)
• Lake Storage Change (LSC)

#### Main Characteristics
> Data generated in the Lakes_cci project are derived from multiple sensors and satellites (for details see the Product Specification Document (PSD)) and, consequently, different temporal and spatial resolutions. One of the objectives in Lakes_cci project is the harmonisation of the different products as a single dataset with the following characteristics:
• Daily aggregation interval (products are specified as 12:00:00 UTC).
• Grid format with spatial resolution of 1/120 degrees (near 1 km at the equator).
• Variables not produced in grid format (LWL and LWE) are duplicated in the grid for the area given under the nominal spatial delineation of that lake.
• Common 1/120 degree grid (latitude and longitude)
• Common regions of interest. The full set of lake definitions is made available as a set of polygons and on the global grid equivalent to the CRDP. The definitions are based on the maximum water extent V4.0 maps from ESA Land Cover. The grid representation of the lake definitions also contains the distance to the nearest land for each lake pixel.
• Extent: -180 to 180 degrees longitude, -90 to 90 degrees latitude, where positive signs point north and east. The pixel coordinate is the centre of the pixel.

## WFEL

### Introduction

#### Scope
The objective of this project is to produce, for each of the variables grouped under the Lakes ECV, a dataset comprising monthly mean values spanning September 1992 – December 2023, wherein each record corresponds to a single lake within the candidate set.

> [!note]
> This project relies upon data sourced from the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

#### Candidate Set Selection
 Candidate lakes are identified by filtering the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file to retain only those records whose `country` field contains either `Canada` or `United States`:

```RBQL
SELECT * WHERE like(a4, '%United States%') || like(a4, '%Canada%')
```

The resulting candidate set comprises 667 lakes.

> [!note]
> Although the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file was published alongside the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/), its use extends to [Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

### Processing

---
## References
[ESA Lakes Climate Change Initiative (Lakes_cci)](https://climate.esa.int/en/projects/lakes/)
[ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/)
[ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/)
[Lakes_cci Product User Guide (PUG)](https://climate.esa.int/media/documents/Lakes_cci_PUG-v3.00_ST.pdf)