# pm25_atmosphere_analysis_2023
Code repository for: **Examining the Effectiveness of Air Quality Monitoring for Agricultural Workers During Extreme Wildfires Events.**

Code developed for this project includes algorithms to download PM2.5 data from the AirNow Sebastopol Station, download PurpleAir Sonoma County PM2.5 , correct and aggregate PurpleAir 2-minute data into hourly averages, plot time series and diel cycles. 

[![DOI](https://zenodo.org/badge/679422894.svg)](https://zenodo.org/badge/latestdoi/679422894)


## Methodology

Data processing and analysis is broken up into several Jupyter notebooks.

| Name | description | notebook |
|---------:|:------------|:----:|
| Process AirNow | Downloads AirNow station data from Sebastopol station, writes hourly data to csv, processes daily data, convert to AQI values, writes csv files, plots for consistency check.  |  collect_and_process_AirNow_API.ipynb |
| Download PurpleAir meta | Downloads Purple Air metadata from https://api.purpleair.com to collect a list of all stations within a region bounded by latitude and longitude ranges. |  collect_PurpleAir_meta.ipynb |
| Download PurpleAir 2 min | Downloads Purple Air measurements of raw 2-minute data from the thingspeak API (now redundant). |  collect_PurpleAir_rawdata_thingspeak.ipynb |
| Process PurpleAir hourly | Create hourly data from 2-minute data, perform QA/QC and apply EPA smoke correction. |  collect_PurpleAir_process_rawdata.ipynb |
| Process PurpleAir daily | Process daily PM2.5 from hourly data and write a combined file for Sonoma County. |  collect_PurpleAir_create_daily_wfilter.ipynb |
| Create PurpleAir AQI | Process AQI values. |  reprocess_PurpleAir_AQI_GIS.ipynb |
| Plot comparisons | Timeseries of daily averages and diel cycles in different regions. | plot_PA_Airnow-90perc.ipynb |

