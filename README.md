# Time series trend analysis of Chillai Kalan over the Kashmir Valley

**A meteorological study of cold waves, temperature variability, snowfall, and precipitation using ERA5-Land reanalysis data.**

## Overview

Chillai Kalan is the harshest phase of winter in Kashmir, traditionally observed from 21 December to 29 January. This project investigates the variability and long-term trends of cold conditions during Chillai Kalan over the Kashmir Valley, with a focus on temperature extremes, cold-wave occurrence, snowfall, and precipitation.

The analysis uses ERA5-Land reanalysis data to examine winter conditions from 1981 to 2024, with the aim of understanding how cold spells and related meteorological variables have varied over time and across selected locations.

## Research Objectives

1. Analyses the long-term variability of minimum temperature during Chillai Kalan.
2. Identify number of cold-wave occurrences and examine their temporal trends.
3. Compare cold conditions across selected locations in the Kashmir Valley.
4. Investigate temperature extremes using percentile-based indices.
5. Apply statistical methods (Mankendall trend test) to evaluate the significance and magnitude of observed trends.

## Study Area

The study focuses on the Kashmir Valley, located in the northwestern Himalayas, India.

- **Coordinates:** 32.0°N–35.8°N and 73.0°E–76.8°E.
- **Time period:** 1981–2024.
- **Interested Season:** Chillai Kalan, from 21 December to 29 January.

The Locations:
- Srinagar
- Gulmarg
- Pahalgam
- Baramulla
- Kupwara
- Qazigund

## Data Source

The meteorological data used in this project are obtained from the **ERA5-Land reanalysis dataset**, provided by the Copernicus Climate Change Service (C3S).

Data portal: [Copernicus Climate Data Store](https://cds.climate.copernicus.eu/)

The variables analysed include:

- **2 m temperature (`t2m`):** Used to derive daily minimum and maximum temperatures.
- **Snowfall (`sf`):** Used to investigate snowfall variability.
- **Snow depth (`sde`):** Used to examine variations in snow depth.
- **Total precipitation (`tp`):** Used to investigate precipitation variability.

The data are processed using Python, primarily with `xarray`, `NumPy`, `pandas`, and related scientific-computing libraries.

## Methodology

### 1. Data Processing

ERA5-Land data are processed to extract the Chillai Kalan period for each winter season. The period is constructed by combining 21–31 December with 1–29 January of the following calendar year.

Daily minimum and maximum temperatures are derived from the available temperature data. Temperature values are converted from kelvin to degrees Celsius where appropriate.

### 2. Cold-Wave Analysis

Cold-wave conditions are examined using temperature-based criteria. Cold-wave days and cold-spell duration are analysed to investigate the frequency and persistence of severe cold conditions.

The analysis also examines consecutive cold days, following the adopted cold-wave definition.

### 3. Climate Indices

The project calculates temperature indices to characterise cold and warm extremes, including:

- **TN10p:** Percentage of days when daily minimum temperature falls below the baseline 10th percentile.
- **TN90p:** Percentage of days when daily minimum temperature exceeds the baseline 90th percentile.
- **CSDI:** Cold Spell Duration Index.
- **CWD:** Cold-wave days, based on the adopted cold-wave definition.
- **DTR:** Diurnal Temperature Range, calculated as daily maximum temperature minus daily minimum temperature.

The percentile-based indices use the 1991–2020 reference period, consistent with the selected climatological baseline.

### 4. Anomaly Analysis

Temperature anomalies are calculated relative to the climatological reference period. Snowfall, snow depth, and precipitation are also analysed to investigate variations during Chillai Kalan.

### 5. Trend Analysis

Long-term trends are evaluated using:

- **Mann–Kendall test:** A non-parametric test for identifying monotonic trends.
- **Sen's slope estimator:** Used to estimate the magnitude and direction of a trend.
- **Kendall's tau:** Used to quantify the direction and strength of the monotonic association.

The statistical results are used to distinguish increasing, decreasing, and statistically insignificant trends.

## Tools and Technologies

The project uses the following scientific-computing tools:

- Python
- Jupyter Notebook
- NumPy
- pandas
- xarray
- SciPy
- Matplotlib
- NetCDF/GRIB data-processing libraries

## Results

Trend analysis revealed that most indices exhibit interannual variability but do not
show statistically significant long-term trends. In contrast, the Diurnal Temperature
Range (DTR) displayed a statistically significant increasing trend at all six stations,
indicating an increasing difference between daytime maximum and nighttime minimum
temperatures during the Chillai Kalan period. On the top of this, Pahalgam was the only
station to exhibit a statistically significant decreasing trend in seasonal mean minimum
temperature (TNm), while the remaining stations did not show significant long-term
changes in mean minimum temperature.
Overall, the finding suggests that although the frequency/persistence of cold waves
have remained relatively stable over the past four and a half decades, winter temperature
characteristics displays vivid spatial heterogeneity across the Kashmir Valley. The DTR
rise at all 6 hill stations may be an indication of alteration in the regional surface energy
budget and deserves further study utilizing other meteorological parameters like vegetation,
clouds, and radiation.

## Reproducibility

To reproduce the analysis:

1. Clone or download this repository.
2. Install the required Python packages.
3. Obtain the ERA5-Land data from the Copernicus Climate Data Store (for the given latitude and longitude range mentioned above and for dec and jan months for all study period years)
4. Place the downloaded data in the appropriate local directories.
5. Update file paths in the notebooks and run.

Raw meteorological data are not included in this repository because of their size (Also downloading the data was the most painfull thing in the entire project, so everyone should get the experience). Users should consult the original data source and document the relevant retrieval settings.

## Acknowledgements

The author acknowledges the Copernicus Climate Change Service for providing ERA5-Land reanalysis data and the open-source Python scientific-computing community for the tools used in this analysis. Also, my favourite PhD student Imamah Ali for being such an incredible support during this project (which is still ongoing).

## Author

**Kumkum Prabha Mishra**  
Integrated MSc in Physics and Astronomy  
National Institute of Technology Rourkela, India

## License

The code and original analysis materials may be reused subject to the license selected for this repository. ERA5-Land data remain subject to their original data-access and attribution terms.
