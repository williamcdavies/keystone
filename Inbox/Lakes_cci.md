---
tags:
  - WFEL
---

## Lakes_cci Project
Develops satellite-derived products for the Lakes Essential Climate Variable (ECV), as defined by GCOS-200 (GOOS-214):
- Lake Water Level (LWL): fundamental to understand the balance between water inputs and water loss.
  Lake Water Extent (LWE): a proxy for change in glacial regions (lake expansion) and drought in many arid environments, water extent relates to local climate for the cooling effect that water bodies provide.
- Lake Surface Water temperature (LSWT): correlated with regional air temperatures and a proxy for mixing regimes, driving biogeochemical cycling and seasonality.
- Lake Ice Cover (LIC): freeze-up in autumn and advancing break-up in spring are proxies for gradually changing climate patterns and seasonality.
- Lake Ice Thickness (LIT): a driver of seasonal lake biogeochemistry and early indicator of changing lake thermodynamics. This product, is being evaluated and upscaled during the current project phase.
- Lake Water-Leaving Reflectance (LWLR): a direct indicator of biogeochemical processes and habitats in the visible part of the water column (e.g. seasonal phytoplankton biomass fluctuations), and an indicator of the frequency of extreme events (peak terrestrial run-off, changing mixing conditions).

### Objectives
The overarching objective of the Lakes project is to produce and validate a consistent data set of the variables grouped under the Lakes ECV.

## WFEL
This project relies upon data sourced from the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

### Objectives
The objective of this project is to produce, for each of the variables grouped under the Lakes ECV, a dataset comprising monthly mean values spanning September 1992 – December 2023 for each candidate lake.

### Preprocessing
 Candidate lakes were identified by filtering the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file to retain only those lakes whose `country` was defined as either `Canada` or `United States`:

```RBQL
SELECT * WHERE like(a4, '%United States%') || like(a4, '%Canada%')
```

This procedure yielded a candidate set containing 667 lakes.

> [!note]
> Although the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file was published alongside the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/), its use as a metadata catalogue extends to [Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

### Processing


---
## References
[ESA Lakes Climate Change Initiative (Lakes_cci)](https://climate.esa.int/en/projects/lakes/)
[ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/)
[ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/)