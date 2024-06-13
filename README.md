# pm25_atmosphere_analysis_2023
Code repository for: **Air Quality Monitoring and the Safety of Farmworkers in Wildfire Mandatory Evacuation Zones.**

Code developed for this project includes algorithms to download PM2.5 data from the AirNow Sebastopol Station, download PurpleAir Sonoma County PM2.5 , correct and aggregate PurpleAir 2-minute data into hourly averages, plot time series and diel cycles. 

To cite this codebase, please use:
  * Buchholz, R. R.: Code repository for: Examining the Effectiveness of Air Quality Monitoring for Agricultural Workers During Extreme Wildfires Events. Zenodo vx.x.x, https://doi.org/10.5281/zenodo.8253550, https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023 (2023).

Latest version: [![DOI](https://zenodo.org/badge/679422894.svg)](https://zenodo.org/badge/latestdoi/679422894)


## Methodology

Data processing and analysis is broken up into several Jupyter notebooks.

| Name | description | notebook |
|---------:|:------------|:----:|
| Process AirNow | Downloads AirNow station data from Sebastopol station, writes hourly data to csv, processes daily data, converts to AQI values, writes csv files, plots for consistency check.  |  [collect_and_process_AirNow_API.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/collect_and_process_AirNow_API.ipynb) |
| Download PurpleAir meta | Downloads Purple Air metadata from https://api.purpleair.com to collect a list of all stations within a region bounded by latitude and longitude ranges. |  [collect_PurpleAir_meta.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/collect_PurpleAir_meta.ipynb) |
| Download PurpleAir 2 min | Downloads Purple Air measurements of raw 2-minute PM2.5 data from the thingspeak API, https://api.thingspeak.com (now redundant), creates hourly averages (with 90% or more data coverage) and saves csv files. |  [collect_PurpleAir_rawdata_thingspeak.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/collect_PurpleAir_rawdata_thingspeak.ipynb) |
| Process PurpleAir hourly | Perform QA/QC and apply EPA smoke correction and also calculate PM2.5 AQI values. Write out csv with new values added. |  [process_PurpleAir_rawdata.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/process_PurpleAir_rawdata.ipynb) |
| Process PurpleAir daily | Process daily PM2.5 from hourly data and write a combined file for Sonoma County. Write a file for concentrations and a file for PM2.5 AQI. |  [process_PurpleAir_daily_wfilter.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/process_PurpleAir_daily_wfilter.ipynb) |
| Plot comparisons | Timeseries of daily averages and diel cycles in different regions. | [plot_PA_AirNow-90perc.ipynb](https://github.com/rrbuchholz/pm25_atmosphere_analysis_2023/blob/main/plot_PurpleAir_AirNow-90perc.ipynb) |

