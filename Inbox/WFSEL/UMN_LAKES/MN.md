## FAQ
1. 
	1. Q. What is a `.tsv` file?
	2. A. A `.tsv` is a tab-separated value file.
2. 
	1. Q. What does `unmlknum` stand for?
	2. A. `unmlknum` stands for UNM Lake Number.

## How Many Unique Lakes?

### Per File?

```python
import pathlib
import pandas as pd

dir_path = pathlib.Path("/Users/williamchuter-davies/Documents/Projects/P-8/WFSEL/data/mn_lakes")
tsv_paths = sorted(dir_path.glob("*.tsv"))

for tsv_path in tsv_paths:
	df = pd.read_csv(tsv_path, sep="\t")
	ser = df["unmlknum"]
	
	print(f"{tsv_path.stem}: {ser.nunique()}")
```

```
S2MSI1C_MN_2017_2m0iA4: 11730
S2MSI1C_MN_2017_2m0iCL: 11664
S2MSI1C_MN_2017_2m0iSD: 11722
S2MSI1C_MN_2018_2m0iA4: 11824
S2MSI1C_MN_2018_2m0iCL: 11773
S2MSI1C_MN_2018_2m0iSD: 11813
S2MSI1C_MN_2019_2m0iA4: 11846
S2MSI1C_MN_2019_2m0iCL: 11820
S2MSI1C_MN_2019_2m0iSD: 11841
S2MSI1C_MN_2020_2m0iA4: 11799
S2MSI1C_MN_2020_2m0iCL: 11773
S2MSI1C_MN_2020_2m0iSD: 11791
S2MSI1C_MN_2021_2m0iA4: 11754
S2MSI1C_MN_2021_2m0iCL: 11729
S2MSI1C_MN_2021_2m0iSD: 11748
S2MSI1C_MN_2022_2m0iA4: 11786
S2MSI1C_MN_2022_2m0iCL: 11749
S2MSI1C_MN_2022_2m0iSD: 11775
S2MSI1C_MN_2023_2m0iA4: 11723
S2MSI1C_MN_2023_2m0iCL: 11678
S2MSI1C_MN_2023_2m0iSD: 11714
S2MSI1C_MN_2024_2m0iA4: 11794
S2MSI1C_MN_2024_2m0iCL: 11767
S2MSI1C_MN_2024_2m0iSD: 11789
S2MSI1C_MN_2025_2m0iA4: 11749
S2MSI1C_MN_2025_2m0iCL: 11723
S2MSI1C_MN_2025_2m0iSD: 11743
```

### All Files?

```python
import pathlib
import pandas as pd
from functools import reduce

dir_path = pathlib.Path("/Users/williamchuter-davies/Documents/Projects/P-8/WFSEL/data/mn_lakes")
tsv_paths = sorted(dir_path.glob("*.tsv"))

l = []

for tsv_path in tsv_paths:
	df = pd.read_csv(tsv_path, sep="\t")
	ser = df["unmlknum"]
	
	l.append(ser)

s = reduce(lambda a, b: a[a.isin(b)], l)

print(f"Shared: {s.nunique()}")
```

```
Shared: 11369
```

## Inspecting Lake Data?
UMN_41008400_v1.0:
![[UMN_41008400_v1.0.png]]

> [!warning]
> Problem: 
> Observations are clustered near the start of each year because pandas is interpreting the date string `YYYYMMDD` as an integer.

> [!success]
> Solution: Convert date string `YYYYMMDD` to datetime.

UMN_41008400_v1.1:
![[UMN_41008400_v1.1.png]]

Observation clustering is improved. However, UMN observation dates are not as frequent as ESA observation dates. Therefore, it is not possible to fit the UMN observation data into the ESA observation data pipeline. Some components, however, may be usable. 

Pros: An identical strategy can be used to compute the smoke season of a given lake.
Cons: There are not enough observations during the smoke season of a given lake to discover a trend.

> [!warning] 
> Problem: No units were provided for Secchi Depth, Chlorophyl-a, nor A440 CDOM.

> [!success] 
> Solution: Leave units blank until this can be resolved.

> [!warning] 
> Problem: Observation dates are sparse. Therefore, a complete trend line for an individual lake cannot be observed.

> [!help] 
> Solution: Signal processing. i.e., measuring state before an after some signal event (smoke coverage) and performing a comparison.

### Loading ShapeFiles into PostgreSQL

```sh
ogr2ogr -f "PostgreSQL" PG:"dbname=spatial" data/umn_lakes/product/MNWQ2010_new_ecoregion_wgs/MNWQ2010_new_ecoregion_wgs.shp -nln public.umn_lakes -lco SPATIAL_INDEX=GIST -nlt MULTIPOLYGON
```

### Querying PostgreSQL for Metadata
Objective: To produce a count of distinct start days for UMN Lakes; To link HydroLAKES to UMN Lakes.

The queries to produce these tables have already been written. They can be duplicated and fitted to `public.umn_lakes`.
> [!bug]
> Bug: Tables are blank or null. An SRID or projection issue may have occurred.
> 
| unmlknum | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 |
|:-------- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |
| 01000100 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
| 01000200 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
| 01000300 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
| 01000400 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
| 01000500 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
| 01000600 | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    | 0    |
>
| umn_lakes_id | hylak_id | lake_name | country | continent | poly_src | lake_type | grand_id | lake_area_m2 | shore_len_m | shore_dev | vol_total_m3 | vol_res_m3 | vol_src | depth_avg_m | dis_avg_m3_per_s | res_time_days | elevation_m | slope_deg | wshd_area_m2 | pour_long_deg | pour_lat_deg |
|:------------ |:-------- |:--------- |:------- |:--------- |:-------- |:--------- |:-------- |:------------ |:----------- |:--------- |:------------ |:---------- |:------- |:----------- |:---------------- |:------------- |:----------- |:--------- |:------------ |:------------- |:------------ |
| 01000100     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000200     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000300     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000400     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000500     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000600     |          |           |         |           |          |           |          |              |             |           |              |            |         |             |                  |               |             |           |              |               |              |

UMN_Shapes_Source:
![[UMN_Shapes_Source.png]]

UMN_Shapes_PSQL
![[UMN_Shapes_PSQL.png]]

Source ShapeFile and PSQL output provide identical map projections. The bug was likely introduced during query duplication and modification.

> [!bug]
> Bug: `public.umn_lakes.wkb_geometry` is projected into `32615` whereas `public.hms_smokes.geom` and `public.hylak_polys.geom` are projected into `4326`.
> 
```
SELECT Find_SRID('public', 'hms_smokes', 'geom');
SELECT Find_SRID('public', 'hylak_polys', 'geom');
 find_srid 
-----------
      4326
(1 row)

 find_srid 
-----------
      4326
(1 row)

spatial=# SELECT Find_SRID('public', 'umn_lakes', 'wkb_geometry');
 find_srid 
-----------
     32615
(1 row)
```

> [!success]
> Solution: transform SRID to `4326` at transaction time.
>
| umn_lakes_id | 2011 | 2012 | 2013 | 2014 | 2015 | 2016 | 2017 | 2018 | 2019 | 2020 | 2021 | 2022 | 2023 |
|:------------ |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |:---- |
| 01000100     | 4    | 23   | 14   | 16   | 23   | 5    | 16   | 25   | 17   | 14   | 57   | 21   | 85   |
| 01000200     | 5    | 22   | 14   | 16   | 24   | 5    | 18   | 26   | 17   | 14   | 57   | 21   | 84   |
| 01000300     | 5    | 22   | 13   | 17   | 24   | 6    | 19   | 27   | 17   | 14   | 58   | 19   | 84   |
| 01000400     | 5    | 22   | 13   | 17   | 24   | 6    | 19   | 27   | 17   | 14   | 58   | 19   | 85   |
| 01000500     | 6    | 21   | 13   | 16   | 24   | 7    | 18   | 27   | 17   | 14   | 57   | 19   | 84   |
| 01000600     | 6    | 19   | 13   | 16   | 24   | 7    | 18   | 26   | 17   | 13   | 57   | 19   | 84   |
>
| umn_lakes_id | hylak_id | lake_name | country                  | continent     | poly_src | lake_type | grand_id | lake_area_m2 | shore_len_m        | shore_dev | vol_total_m3 | vol_res_m3 | vol_src | depth_avg_m | dis_avg_m3_per_s | res_time_days | elevation_m | slope_deg | wshd_area_m2 | pour_long_deg | pour_lat_deg |
|:------------ |:-------- |:--------- |:------------------------ |:------------- |:-------- |:--------- |:-------- |:------------ |:------------------ |:--------- |:------------ |:---------- |:------- |:----------- |:---------------- |:------------- |:----------- |:--------- |:------------ |:------------- |:------------ |
| 01000100     | 107727   |           | United States of America | North America | SWBD     | 1         | 0        | 1340000      | 7070               | 1.72      | 6510000      | 0          | 3       | 4.8         | 0.368            | 204.8         | 329         | 2.86      | 40400000     | -93.064641    | 46.193753    |
| 01000200     |          |           |                          |               |          |           |          |              |                    |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000300     |          |           |                          |               |          |           |          |              |                    |           |              |            |         |             |                  |               |             |           |              |               |              |
| 01000400     | 1026013  |           | United States of America | North America | SWBD     | 1         | 0        | 150000       | 2029.9999999999998 | 1.48      | 260000       | 0          | 3       | 1.8         | 0.066            | 46.4          | 392         | 0.66      | 6200000      | -93.142158    | 46.548936    |
| 01000500     | 1025420  |           | United States of America | North America | SWBD     | 1         | 0        | 300000       | 2660               | 1.37      | 810000       | 0          | 3       | 2.7         | 0.101            | 92.4          | 385         | 1.28      | 9400000      | -93.141939    | 46.595509    |
| 01000600     |          |           |                          |               |          |           |          |              |                    |           |              |            |         |             |                  |               |             |           |              |               |              |

5444 of the 12194 (44.64%) of lakes could not be linked to HydroLAKES. Therefore, HydroLAKES metadata cannot considered for a significant percentage of the study group.

## Simple Comparison
> [!warning]
> Problem: 2024 and 2025 data needs to be extracted from NOAA, transformed, and loaded into PostgreSQL.
