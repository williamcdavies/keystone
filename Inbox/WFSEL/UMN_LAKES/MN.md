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

### Shared?

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
> Problem: Observations are clustered near the start of each year because pandas is interpreting the date string `YYYYMMDD` as an integer.

> [!success]
> Solution: Convert date string `YYYYMMDD` to datetime.

UMN_41008400_v1.1:
![[UMN_41008400_v1.1.png]]

Observation clustering is improved. However, UMN observation dates are not as frequent as ESA observation dates. Therefore, it is not possible to fit the UMN observation data into the ESA observation data pipeline. Some components, however, may be usable. 

Pros: An identical strategy can be used to compute the smoke season of a given lake.
Cons: There are not enough observations during the smoke season of a given lake to discover a trend.

> [!warning] Problem: No units were provided for Secchi Depth, Chlorophyl-a, nor A440 CDOM.

> [!success] Solution: Leave units blank until this can be resolved.

> [!warning] Problem: Observation dates are sparse. Therefore, a complete trend line for an individual lake cannot be observed.

> [!success] Solution: Signal processing. i.e., measuring state before an after some signal event (smoke coverage) and performing a comparison.

### Loading ShapeFiles into PostgreSQL

```sh
ogr2ogr -f "PostgreSQL" PG:"dbname=spatial" data/umn_lakes/product/MNWQ2010_new_ecoregion_wgs/MNWQ2010_new_ecoregion_wgs.shp -nln public.umn_lakes -lco SPATIAL_INDEX=GIST -nlt MULTIPOLYGON
```

Objective: To produce a count of distinct start days for the UMN Lakes; To link HydroLAKES to the UMN Lakes

The queries to produce these tables have already been written. They can be duplicated and fitted to the umn_lakes table.
> [!bug]
> Tables are blank or null. Since both tables are blank, an SRID or projection issue may have occurred.
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

Inspection of source ShapeFiles and PSQL Polygons result in identical map projection. Therefore, the bug is likely as a result of incorrect query modification.

> [!bug]
> `public.umn_lakes.wkb_geometry` is projected into `32615` whereas `public.hms_smokes.geom` and `public.hylak_polys.geom` are projected into `4326`.
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