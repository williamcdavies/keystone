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

Problem: Observations are clustered near the start of each year because pandas is interpreting the date string `YYYYMMDD` as an integer.
Solution: Convert date string `YYYYMMDD` to datetime.

UMN_41008400_v1.1:
![[UMN_41008400_v1.1.png]]

Observation clustering is improved. However, UMN observation dates are not as frequent as ESA observation dates. It may not be possible to observe smoke coverage impact for a single lake. Therefore, analysis has to be done for every lake under some aggregation rule. It may be possible derive a statistic by counting the number of distinct start days between two observation dates within the same year. Restrictions: 
1. The first observation date must occur before the onset of the smoke season, or at least there must be some recovery period before to the observation date.
2. The second observation date must occur after the onset of the smoke season, or at least after some smoke coverage period  before the the observation date.

Pros: An identical strategy can be used to compute the smoke season of a given lake.
Cons: There are not enough observations during the smoke season of a given lake to discover a trend.

Problem: No units were provided for Secchi Depth, Chlorophyl-a, nor A440 CDOM.
Solution: Leave units blank until this can be resolved.



