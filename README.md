# Projecting global Heat Index changes under CMIP6 warming scenarios

## Scientific Question

How will the Heat Index change across the globe under future warming, and which regions will become dangerously hot as warming continues?

High temperature alone does not capture how dangerous heat really is. Humidity plays a critical role by limiting the body's ability to cool through sweating. The Heat Index, developed by the National Weather Service (NWS), combines temperature and relative humidity into a single "feels-like" temperature that reflects actual heat stress on the human body. The NWS issues warnings at two key levels: a Heat Index of 40°C (105°F), where heat cramps, exhaustion, and heatstroke become likely with prolonged exposure, and 55°C (130°F), where heatstroke is considered very likely (NWS, 2024).

This project uses globally complete downscaled CMIP6 projections to map how the frequency and spatial extent of dangerous Heat Index levels evolve from the present into the late 21st century under different emission pathways.

## Datasets

**NEX-GDDP-CMIP6** :This project uses NASA's NEX-GDDP-CMIP6, a global dataset of bias-corrected, downscaled daily climate projections derived from CMIP6 models (Thrasher et al., 2022), including daily near-surface air temperature and relative humidity for both the historical period (1950–2014) and future projections under SSP245 and SSP585 (2015–2100).

## Methods

### Heat Index Calculation

The Heat Index is computed from air temperature and relative humidity using the NOAA/NWS regression equation (Rothfusz, 1990):

```
HI = -42.379 + 2.04901523*T + 10.14333127*R - 0.22475541*T*R
     - 6.83783e-3*T² - 5.481717e-2*R² + 1.22874e-3*T²*R
     + 8.5282e-4*T*R² - 1.99e-7*T²*R²
```

where T is air temperature (°F) and R is relative humidity (%). Results are converted to °C.

### Threshold Exceedance Analysis

Annual exceedances are counted at each grid cell for Heat Index values of 40°C and 55°C, corresponding to the NWS "Danger" and "Extreme Danger" categories, respectively.

## Analysis Summary

1. **How does it look under current climate?** Map the baseline (1950–2014) frequency of Heat Index exceedances at each threshold to establish which regions already face dangerous conditions.
2. **How will the world look under different scenarios?** Map exceedance frequencies at mid-century (2040–2060) and end-of-century (2080–2100) under SSP245 and SSP585 to see how existing hotspots intensify and which new regions cross into dangerous territory.
3. **Does the emission pathway matter?** Compare SSP245 and SSP585 to quantify how much difference mitigation makes for each region.

## References

- NWS (2024). Heat Index. National Weather Service. https://www.weather.gov/safety/heat-index
- Rothfusz, L.P. (1990) The Heat Index Equation. National Weather Service Technical Attachment (SR 90-23).
- Thrasher, B., Wang, W., Michaelis, A., Melton, F., Lee, T., & Nemani, R. (2022). NASA Global Daily Downscaled Projections, CMIP6. *Scientific Data*, 9(254).
