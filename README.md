# HPE_TDI — Global Compound Heatwave-PM2.5 Health Burden Estimation Pipeline

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Data processing code for the compound heat-PM2.5 health burden study.**

## Code Availability

The full data processing code will be released upon publication of the associated manuscript. The repository currently contains only this README as a placeholder.

The pipeline implements:

1. **Heatwave detection** from ERA5-Land daily maximum temperature (percentile-based, ≥3 consecutive days)
2. **PM2.5 pollution day detection** from LGHAP PM2.5 reanalysis (daily PM2.5 > grid-cell p75 AND > 15 μg/m³)
3. **Compound event detection** (co-occurrence of heatwaves and PM2.5 pollution)
4. **Country mask construction** from administrative boundary shapefiles at 0.1° resolution
5. **Population exposure computation** (compound-exposure person-days, attributable fractions, 65+ elderly)
6. **Mortality burden estimation** calibrated to Zhao et al. (2021) heat EDRs and Huang et al. (2025) PM2.5 relative risks, with 7 sensitivity scenarios
7. **Future scenario projections**: CMIP6 GFDL-ESM4 climate projections (SSP1-2.6 / SSP5-8.5, 2051–2060) combined with WCDE v3.0 population ageing scenarios to estimate ageing-amplified premature mortality
7. **Temporal Decoupling Index (TDI)** analysis — same-day, lagged, and seasonal variants

## Data Sources

| Dataset | Source | Resolution |
|---------|--------|------------|
| ERA5-Land | Copernicus CDS | 0.1° × 0.1° |
| LGHAP PM2.5 | Bai et al. 2022, ESSD | 0.1° × 0.1° |
| Population | GPWv4 / WorldPop | 0.1° × 0.1° |
| GBD 2021 | IHME | Country-level |
| Country boundaries | Natural Earth | Vector |

## Contact

For questions about the code or data, please open a GitHub Issue.

## License

MIT License. Full license text will be included with the code release.
