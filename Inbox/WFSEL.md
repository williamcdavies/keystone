Plot 10 lakes with 5 non-smoke years and 1 smoke year.

Only include lakes from P=7 to P=42. Reduce x-axis to span 121 (1 May) to 273 (30 Sept.)

| esacci_lakes_id | 2011     | $\cdots$ | 2023     |
|:--------------- |:-------- |:-------- |:-------- |
| $i_1$           | $d_{11}$ | $\cdots$ | $d_{1n}$ |
| $\vdots$        | $\vdots$ | $\ddots$ | $\vdots$ |
| $i_m$           | $d_{m1}$ | $\cdots$ | $d_{mn}$ |

Aggregate by
- Trophic state
- Start of smoke season
- Depth of lake

Early: Smoke starts in `[May, Jun, Jul, Aug.15]`
Late: Smoke starts in `[Aug.15, Sep, Oct, Nov]`

Shallow: < 10m
Deep: > 10m


## Products

## Lakes
- Lake Tahoe
- Crater Lake
- Lake Champlain
- Pyramid Lake
- Flathead Lake
- Lake Oroville
- Salt Lake
- All Great Lakes
- Lake Winnipeg

do the following
- divide between shallow and deep lakes
- lakes < 10 m (shallow): > 50m (deep)
	- for simple purpose:
		- weekly values of temperature. plot the difference between the smoke and non-smoke year. repeat for all lakes lower than a certain depth. plot when the smoke season starts in each of the lake
		- define the beginning of the smoke season as the first week >= 4 of smoke. non-smoke <= 7. smoke >= 42.


Notes
- Shallow lakes, on average, are warmer than deep lakes at the start of the smoke season by ~$12.004 - 9.917 = 2.087$ degrees Celsius. 
- Shallow lakes, on average, reach their peak seasonal temperature sooner than deep lakes by ~$8 - 6 = 2$ weeks.
- Shallow lakes, 