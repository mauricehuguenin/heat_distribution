# heat_distribution
Analysis Scripts and Data used for the submission: 

Huguenin, M. F., Holmes, R. M. and England, M. H. (2022). Drivers and distribution of global ocean heat uptake over the last half century. *Nature Geoscience*

# Packages and Functions
I use the following main python packages which are publicly available online:

- cartopy (creating maps)
- numpy (numerical operations)
- xarray (loading in and working with .nc data files)

# Analysis Scripts

- [extract_patterns_cesm_with_differences.m](extract_patterns_cesm_with_differences.m) and [extract_patterns_cmip5_with_differences.m](extract_patterns_cmip5_with_differences.m) are the MATLAB files I used to pull out all the circulation type maps shown in the Supporting Information Fig. S9-S20 including the differences in the maps for the past and future time periods
- [leap_day_cesm.py](leap_day_cesm.py) and [leap_day_cmip5.py](leap_day_cmip5.py) are the scripts I used to insert leap days every 4th year for those models that do not have leap days. I basically inserted a day with a 'NAN' circulation type randomly within that year which as a leap day. This was necessary in order to align the dates and the cost output files
- [merging_cmip5.py](merging_cmip5.py) and [preprocessing_cesm.py](preprocessing_cesm.py) are basically the same scripts but for the two model data sets and show the preprocessing of the raw output files in order for use in cost733class. See also the documentation in the Supporting Information, Section 2
- [preprocessing_cesm_maps_data.py](preprocessing_cesm_maps_data.py) and [preprocessing_cmip5_maps_data.py](preprocessing_cmip5_maps_data.py) are the scripts used to prepare the raw model data sets for the circulation type maps in MATLAB (i.e. extracting Central European region, only selecting specific variables, only selecting 1980-2099 time period, ...)

# List of Figures
__Fig. 1__: Recent global ocean heat content anomalies in observations and hindcast model simulations

[Fig1_comparing_IAF_OHC_from_new_simulation_with_OBS.ipynb](Fig1_comparing_IAF_OHC_from_new_simulation_with_OBS.ipynb)

__Fig. 2__: Spatial distribution of ocean heat uptake, transport, storage and SST trends over 1972--2017 in the simulation with full interannual forcing

[Fig2_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb](Fig2_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb)

__Fig. 3__: Simulated global and regional OHC changes due to thermal/wind trends and due to atmospheric trends over individual regions

[Fig3_time_series_and_histograms_perturbation_simulations.ipynb](Fig3_time_series_and_histograms_perturbation_simulations.ipynb)

__Fig. 4__: Southern Hemisphere ocean heat uptake, temperature and net longwave and sensible heat flux trends over 1972--2017

[Fig4_zonal_mean_integrals.ipynb](Fig4_zonal_mean_integrals.ipynb)

__Fig. 5__: Schematic summarising anomalous global ocean heat uptake and transport over the last half century in different hindcast simulations

[Fig5_schematic_OHC_map_and_side_panels.ipynb](Fig5_schematic_OHC_map_and_side_panels.ipynb) and [Fig5_schematic_OHC.ppt](Fig5_schematic_OHC.ppt)
 
- Script for Figs. S3-7 includes the analysis of past time series and trends for the four main circulation types
[]()

# Model output data on the NCI supercomputer gadi
```
| Description of simulation     | Model files*               | Input files                        | Storage files**                                  |
| ----------------------------- | -------------------------- | ---------------------------------- | ------------------------------------------------ |
| Pre-industrial offset spin-up | 1deg_jra55_iaf_PI_Offset   | e14/EXP_PI_Offset_JRA55-do-1-3     | 1deg_jra55_rdf_spinup_PI_Offset                  |
| ""  "" continued with scaling | 1deg_jra55_iaf_PI_Offset   | e14/EXP_PI_Offset_JRA55-do-1-3     | 1deg_jra55_rdf_spinup_PI_Offset_for_Control      |
| ""  "" continued as control   | 1deg_jra55_iaf_Control     | /g/data/qv56                       | 1deg_jra55_iaf_branch2000_Control_PI_Offset      |
| Full interannual forcing      | 1deg_jra55_iaf_branch2000  | /g/data/qv56                       | 1deg_jra55_iaf_branch2000_PI_Offset              |
| ----------------------------- | -------------------------- | ---------------------------------- | ------------------------------------------------ |
| Southern Ocean-only forcing   | 1deg_jra55_iaf_Southern    | e14/EXP_Southern_JRA55-do-1-3      | 1deg_jra55_iaf_branch2000_Southern_PI_Offset     |
| North of 44°S forcing         | 1deg_jra55_iaf_Northern    | e14/EXP_Northern_JRA55-do-1-3      | 1deg_jra55_iaf_branch2000_Northern_PI_Offset     |
| Tropics-only forcing          | 1deg_jra55_iaf_Tropics30SN | ik11/EXP_Tropics_30SN_JRA55-do-1-3 | 1deg_jra55_iaf_branch2000_Tropics30SN_PI_Offset  |
| ----------------------------- | -------------------------- | ---------------------------------- | ------------------------------------------------ |
| Pacific Ocean-only forcing    | 1deg_jra55_iaf_Pacific     | ik11/EXP_Pacific_JRA55-do-1-3      | 1deg_jra55_iaf_branch2000_Pacific_PI_Offset      |
| Indian Ocean-only forcing     | 1deg_jra55_iaf_Indian      | ik11/EXP_Indian_JRA55-do-1-3       | 1deg_jra55_iaf_branch2000_Indian_PI_Offset       |
| Atlantic Ocean-only forcing   | 1deg_jra55_iaf_Atlantic    | ik11/EXP_Atlantic_JRA55-do-1-3     | 1deg_jra55_iaf_branch2000_Atlantic_PI_Offset     |
| ----------------------------- | -------------------------- | ---------------------------------- | ------------------------------------------------ |
```

- * `/home/561/mv7494/`
- ** `/g/data/e14/mv7494`


[Location of model runs](location_model_runs.png)
