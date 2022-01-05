# heat_distribution
Analysis Scripts and Data used for the submission: 

Huguenin, M. F., Holmes, R. M. and England, M. H. (2022). Drivers and distribution of global ocean heat uptake over the last half century. *Nature Geoscience*

# Packages and Functions
I use the following main python packages which are publicly available online:

- cartopy (creating maps)
- numpy (numerical operations)
- xarray (loading in and working with .nc data files)

# Analysis Scripts


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
 
 Supporting Info figures:
__Fig. S1__: Total ocean heat content anomalies in ACCESS-OM2
[]()

__Fig. S2__: Experimental design of the new spin-up
[]()

__Fig. S3__: Simulated global ocean heat content in OMIP-2 and CMIP6
[]()

__Fig. S4__: Spatial distribution of OHU, transport, storage and SST trends over 1972-2017 in the wind-only and thermal-only forcing experiment
[Same script as for Fig. 2.](Fig2_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb)

__Fig. S5__: As in Fig. S4. but for the Southern Ocean-only experiment.
[FigS5_regional_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb](FigS5_regional_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb)

__Fig. S6__: Ocean heat content changes since 1972 in the basin-wide simulations
[]()

__Fig. S7__: As in Fig. S4. but for the Pacific, Indian and Atlantic Ocean-only experiments.
[Same script as for Fig. S5.](FigS5_regional_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb)

__Fig. S8__: Maximum strength of the Atlantic Meridional Overturning (AMOC) Streamfunction at 26°N between 103°W and 5°W
[FigS8_overturning_stream_function_in_both_cartesian_neutral_density_space_ACCESS-OM2-1_new.ipynb](FigS8_overturning_stream_function_in_both_cartesian_neutral_density_space_ACCESS-OM2-1_new.ipynb)

__Fig. S9__: Ocean heat content trends over 1992-2011 in the Tropics 30°S-30°N experiment
[Same script as for Fig. S5.](FigS5_regional_spatial_maps_and_zonal_integral_of_accumulated_ocean_heat_content_and_net_sfc_heating_anomalies-PI_Offset.ipynb)

__Fig. S10__: Spatial distribution of ocean heat uptake and storage trends over 1997-2017 in the simulation with full interannual forcing
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
\* `/home/561/mv7494/`
\** `/g/data/e14/mv7494`

