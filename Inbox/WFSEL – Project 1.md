---
tags:
  - WFSEL
---
## Introduction

### Scope
The objective of this project is to produce, for each day in September 1992–December 2023, a dataset comprising mean, median, variance, minimum, and maximum values for each of the Lakes Essential Climate Variables in `['chla', 'tsm', 'acdom440', 'Kd490', 'KdPAR', 'phycocyanin', 'lake_surface_water_temperature', 'lake_surface_water_extent']` wherein each record corresponds to a single lake within the candidate set.

> [!note]
> This project depends upon data sourced from the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

### The Candidate Set
The candidate set is identified by filtering the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file to retain only those records whose `country` field contains either `Canada` or `United States`:

```RBQL
SELECT * WHERE like(a4, '%United States%') || like(a4, '%Canada%')
```

The candidate set comprises 667 North American lakes.

> [!note]
> Although the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file was published alongside the [ESA Lakes Climate Change Initiative (Lakes_cci): Lake products, Version 2.1](https://catalogue.ceda.ac.uk/uuid/7fc9df8070d34cacab8092e45ef276f1/), its use extends to [Version 3.0](https://catalogue.ceda.ac.uk/uuid/a56dba09df8a42ec9fba8b8c7a5e1f69/).

## Code

### Introduction
The project repository can be found [here](https://github.com/williamcdavies/WFSEL/tree/main). The program entry point is `main.py`.

> [!note]
> `main.py` is atomic. It produces a single output from a minimum working set of inputs. For workflows that require multiple outputs, batch processing is recommended.

### `main.py`

#### Description
The purpose of `main.py` is to produce a .csv file containing mean, median, variance, maximum, and minimum values for each Lakes ECVs in`['chla', 'tsm', 'acdom440', 'Kd490', 'KdPAR', 'phycocyanin', 'lake_surface_water_temperature', 'lake_surface_water_extent']` for each lake within the candidate set given an ESA Lakes_cci v3.0 dataset, the ESA Lakes_cci v3.0 static lake mask, the ESA Lakes_cci v2.1 lake metadata, and an output destination.

#### Input
`main.py` takes four arguments:
1. `lakes_cci_merg_prod_nc_path`: The path to an [ESACCI-LAKES-L3S-LK_PRODUCTS-MERGED-YYYYMMDD-fv3.0.0.nc](https://dap.ceda.ac.uk/neodc/esacci/lakes/data/lake_products/L3S/v3.0/merged_product/) file
2. `lakes_cci_stat_mask_nc_path`: The path to the [ESA_CCI_static_lake_mask.nc](https://dap.ceda.ac.uk/neodc/esacci/lakes/data/lake_products/L3S/v3.0/ESA_CCI_static_lake_mask.nc) file
3. `csv_path`: The path to the [lakescci_v2.1_metadata](https://climate.esa.int/documents/2607/lakescci_v2.1.0_metadata.csv) file.
4. `dst_path`: The destination path. This path must point to a .csv file.

> [!note]
> `main.py` is compatible with any subset of `lakescci_v2.1.0_metadata.csv`.

> [!example]
> ```sh
> >>> python main.py ESACCI-LAKES-L3S-LK_PRODUCTS-MERGED-20230101-fv3.0.0.nc ESA_CCI_static_lake_mask.nc lakescci_v2.1.0_metadata_filtered ./ESACCI-LAKES-L3S-OUTPUT-20230101-fv3.0.0.csv
> ```

#### Output
A `668x41` .csv file with the following structure:

| id       | chla_mean | chla_median | chla_var  | chla_max  | chla_min  | $\cdots$ | lake_surface_water_extent_min |
|:-------- |:--------- |:----------- |:--------- |:--------- |:--------- |:-------- |:----------------------------- |
| 1        | `float64` | `float64`   | `float64` | `float64` | `float64` | $\cdots$ | `float64`                     |
| $\vdots$ | $\vdots$  | $\vdots$    | $\vdots$  | $\vdots$  | $\vdots$  | $\ddots$ | $\vdots$                      |
| 667      | `float64` | `float64`   | `float64` | `float64` | `float64` | $\cdots$ | `float64`                     |

#### Walkthrough
1. Check the argument count. If the argument count does not equal the expected argument count, exit the program.
```python
if len(sys.argv) != 5:
	print(f'fatal: unexpected argument count: {sys.argv}')

	return RETURN_FAILURE
```

2. Create `pathlib.Path` objects from arguments. If any of the provided paths, excluding the destination path, do not exist, exit the program.
```python
paths = [pathlib.Path(p) for p in sys.argv[1:5]]

for path in paths[0:3]:
	if not path.exists():
		print(f'fatal: no such file or directory: {path}')

		return RETURN_FAILURE

lakes_cci_merg_prod_nc_path, lakes_cci_stat_mask_nc_path, csv_path, dst_path = paths
```

3. Declare `records`. `records` will be written to the output .csv file at the conclusion of the program.
```python
records = []
```


```python
try:
	with xarray.open_dataset(lakes_cci_merg_prod_nc_path) as merg_prod_ds, xarray.open_dataset(lakes_cci_stat_mask_nc_path) as stat_mask_ds:
```

```python
# Open DataFrame specified by `csv_path`

csv = pandas.read_csv(csv_path, delimiter=';')

  

# For each row in `csv` ...

for row in tqdm.tqdm(csv.itertuples(), total=len(csv)):

# Read identity and boundary data into `lakes_cci_id`,

# `lakes_cci_lat_min_box`, `lakes_cci_lat_max_box`,

# `lakes_cci_lon_min_box`, and `lakes_cci_lon_max_box`

lakes_cci_id = row.id

lakes_cci_lat_min_box = row.lat_min_box

lakes_cci_lat_max_box = row.lat_max_box

lakes_cci_lon_min_box = row.lon_min_box

lakes_cci_lon_max_box = row.lon_max_box

  

# Clip `merg_prod_ds` to boundary extent

clipped_merg_prod_ds = merg_prod_ds.sel(lat=slice(lakes_cci_lat_min_box,

lakes_cci_lat_max_box),

lon=slice(lakes_cci_lon_min_box,

lakes_cci_lon_max_box))

# Clip `stat_mask_ds` to boundary extent

clipped_stat_mask_ds = stat_mask_ds.sel(lat=slice(lakes_cci_lat_min_box,

lakes_cci_lat_max_box),

lon=slice(lakes_cci_lon_min_box,

lakes_cci_lon_max_box))

# Build geometry mask from `clipped_stat_mask_ds`

geometry_mask = (clipped_stat_mask_ds['CCI_lakeid'].values == lakes_cci_id)

  

# Read `lakes_cci_id` into `record`

record = {'id': lakes_cci_id}

  

# For each data variable in `clipped_merg_prod_ds.data_vars` ...

# for data_var in clipped_merg_prod_ds.data_vars:

for data_var in ['chla',

'tsm',

'acdom440',

'Kd490',

'KdPAR',

'phycocyanin',

'lake_surface_water_temperature',

'lake_surface_water_extent']:

# Read data variable values into `data_var_values`

data_var_values = clipped_merg_prod_ds[data_var].values

  

# If dimensionality of `data_var_values` is not 3, continue

if data_var_values.ndim != 3:

continue

# Read masked data variable values into `data`

data = data_var_values[:, geometry_mask]

  

# Update `record` with mean, median, standard

# deviation, variance, maximum, and minimum of `data`

record.update({

f'{data_var}_mean': numpy.nanmean(data, axis=-1).item(),

f'{data_var}_median': numpy.nanmedian(data, axis=-1).item(),

f'{data_var}_var': numpy.nanstd(data, axis=-1).item(),

f'{data_var}_max': numpy.nanmax(data, axis=-1).item(),

f'{data_var}_min': numpy.nanmin(data, axis=-1).item(),

})

  

records.append(record)

  

# On exception, return with `RETURN_FAILURE`

except Exception as e:

print(f'fatal: exception: {e}')

return RETURN_FAILURE

pdf = pandas.DataFrame(records)

pdf.to_csv(dst_path, index=False)

return RETURN_SUCCESS
```

### Dependencies
`main.py`  depends upon `Python >= 3.14` and the following packages:
- [`numpy  >= 2.5.0`](https://pypi.org/project/geopandas/)
- [`pandas >= 3.0.3`](https://pypi.org/project/netCDF4/)
- [`tqdm   >= 4.68.3`](https://pypi.org/project/rasterio/)
- [`xarray >= 2026.4.0`](https://pypi.org/project/xarray/)

> [!note]
> This list specifies program dependencies for [`main.py`](https://github.com/williamcdavies/WFSEL/blob/main/main.py). For a list of repository dependencies, see [`pyproject.toml`](https://github.com/williamcdavies/WFSEL/blob/main/pyproject.toml). For a complete list of repository dependencies and sub-dependencies, see [`requirements.txt`](https://github.com/williamcdavies/WFSEL/blob/main/requirements.txt).

