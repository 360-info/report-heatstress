# `/data`

## `/data/zhao-etal-2024`

Raw and processed data from [Zhao et al. (2024)](https://doi.org/10.1371/journal.pmed.1004364).

`heatwave-days.csv`: decadal statistics of heatwave exposure, in days. Columns include:

- `location_type`: `country` or `region`
- `continent`: continent in question
- `region`: region within the continent
- `iso2`: country's ISO 3166-1 alpha-2 code
- `country`: country name
- `avr`: average annual number of heatwave days over 1980–2019
- `1980-1989` through `2010-2019`: average annual number of days for each decade
- `Change_per_decade`: the change in the average annual number of days each decade over 1980–2019
- `percen`: the percentage change in the average annual number of days each decade over 1980–2019

`heatwave-mortality-stats-country`: statistics around to heatwave-related mortality in long format. Columns include:

- `measure`: `Excess deaths`, `Excess deaths per 10M residents`
- `population`: `WHO standard population` or `Country-specific age standardisation`
- `location_type`: `country` or `region`
- `id`: an ID based on `measure` and `population`
- `continent`: continent the country is on
- `region`: region the country is in
- `iso2`: country's ISO 3166-1 alpha-2 code
- `country`: country name
- `statistic`: `Overall`, `Average`, `Pct change per decade` or a decadal range
- `central`, `lower`, `upper`: central, lower or upper estimates for the figure. Lower and upper are at a 95% confidence interval.

### `/data/zhao-etal-2024/raw`

Supplementary tables from [Zhao et al. (2024)](https://doi.org/10.1371/journal.pmed.1004364), which are processed and tidied by the analysis.

## `heatstress-asiapac-mosthours-2014to2023.csv`, `heatstress-asiapac-mostdays-avgannual-2014to2023.csv`

Processed statistics from the above tidied data, specific to Asia-Pacific, ordered from most to least.

## `/cds`

### `/cds/heatstress-hours-[couuntries|states].scv`

Data on the heat stress experienced by countries and Indian states over 2014 to 2023, from the [ERA5-HEAT](https://cds.climate.copernicus.eu/cdsapp#!/dataset/derived-utci-historical) dataset. Columns include:

- `year`: the year
- `lower`, `upper`: the lower and upper limits of the heat stress category, based on the the UTCI index. Thresholds are based on those defined by Copernicus.
- `hs_category`: a string label of the category representing a severity of heat stress, based on the UTCI index. Thresholds are based on those defined by Copernicus.
- `iso`: for countries, the ISO 3166-1 alpha-3 code; for Indian states, an identifier
- `country` or `state`: the name of the country or the Indian state
- `hours`: the number of hours that the country or state averaged this level of heat stress for a given year

### `/cds/hs-datawrapper-sea.csv`

Widened form of the above data for the south-east Asia region. Columns include:

- `year`: the year
- `country`: the country name
- `Strong (32-38)`, `Very strong (38-46)`, `Extreme (> 46)`: hours within this UTCI heat stress band
