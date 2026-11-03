## How Many Unique Lakes?

```python
import pathlib
import pandas as pd

dir_path  = pathlib.Path("/Users/williamchuter-davies/Documents/Projects/P-8/WFSEL/data/mn_lakes")
tsv_paths = sorted(dir_path.glob("*.tsv"))

for tsv_path in tsv_paths:
	df  = pd.read_csv(tsv_path, sep="\t")
	ser = df["unmlknum"]
	
	print(f"{tsv_path.}ser.nunique())
```