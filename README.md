Planetary Wave Resonance 
==============================================
This repository contains the data and code necessary to reproduce the results presented in: <a href="https://www.pnas.org/doi/10.1073/pnas.2504482122">Li et al. (2025), Increased frequency of planetary wave resonance events over the past half-century</a>, Proceedings of the National Academy of Sciences, 122(00), e2413503122.

Related Publication
-------------------
Li, X., M. E. Mann, M. F. Wehner, and S. Christiansen (2025),  Increased frequency of planetary wave resonance events over the past half-century, Proceedings of the National Academy of Sciences 122 (00) e2413503122, <a href="https://doi.org/10.1073/pnas.2504482122">https://doi.org/10.1073/pnas.2504482122</a>.

Li, X., M. E. Mann, M. F. Wehner, S. Rahmstorf, S. Petri, S. Christiansen, and J. Carrillo (2024), Role of atmospheric resonance and land–atmosphere feedbacks as a precursor to the June 2021 Pacific Northwest Heat Dome event, Proceedings of the National Academy of Sciences, 121(4), e2315330121, <a href="https://www.pnas.org/doi/10.1073/pnas.2315330121">https://www.pnas.org/doi/10.1073/pnas.2315330121</a>.

Mann, M. E., S. Rahmstorf, K. Kornhuber, B. A. Steinman, S. K. Miller, S. Petri, and D. Coumou (2018), Projected changes in persistent extreme summer weather events: The role of quasi-resonant amplification. Science Advances, 4(10) eaat3272, <a href="https://doi.org/10.1126/sciadv.aat3272">https://doi.org/10.1126/sciadv.aat3272</a>.

Mann, M. E., S. Rahmstorf, K. Kornhuber, B. A. Steinman, S. K. Miller, and D. Coumou (2017), Influence of anthropogenic climate change on planetary wave resonance and extreme weather events. Scientific Reports, 7(1), 45242, <a href="https://doi.org/10.1038/srep45242">https://doi.org/10.1038/srep45242</a>. 

Files description
-----------------
The following data are used to reproduce Fig. 1:
* `QRA_freq_1950-2024.csv` &rarr; Annual counts of quasi-resonant amplification (QRA) of planetary wave events during boreal summer (JJA), 1950–2024.
* `GISTEMP_latband_2017_1880-2016_jja_lat-25n-75n_QRAindex.nc` &rarr; QRA fingerprint series calculated from GISTEMP surface temperature observations, 1880-2016 (Mann et al. 2017, 2018).
* `HadCRUT_latband_2017_1850-2016_jja_lat-25n-75_QRAindex.nc` &rarr; QRA fingerprint series calculated from HadCRUT4 surface temperature observations, 1850-2016 (Mann et al. 2017, 2018).
* `HadCRUT_krig_latband_2017_1850-2016_jja_lat-25n-75n_QRAindex.nc` &rarr; QRA fingerprint series calculated from Cowtan and Way surface temperature observations, 1850-2016 (Mann et al. 2017, 2018).

The following data are used to reproduce Fig. 2:
* `era5_monthly_1.5deg_v300_1950_2024_JJAmean_37.5N-57.5N_delplev-dct.nc` &rarr; Wave amplitudes calculated from monthly ERA5 data (37.5°N to 57.5°N; 1950-2024) by applying a zonal fast Fourier transformation (FFT) to JJA-averaged 300 hPa meridional wind fields. 

The following data are used to reproduce Fig. 3:
* `T_QRA_JJA_NH_ERA_2p5dg_lat-25n-75n_anom.nc` &rarr; QRA zonal fingerprint (Mann et al. 2017, 2018)
* `RC_slope_ERA5-based QRA frequency_ERA5t2m.nc` &rarr; Regression slope of ERA5-based QRA count series against ERA5 surface temperature anomalies.
* `RC_pval_ERA5-based QRA frequency_ERA5t2m.nc` &rarr; Corresponding p-values for the above regression.
* `RC_slope_ERA5-based QRA frequency_GISTEMP.nc` &rarr; Regression slope of ERA5-based QRA count series against GISTEMP anomalies.
* `RC_pval_ERA5-based QRA frequency_GISTEMP.nc` &rarr; Corresponding p-values for the above regression.
* `RC_slope_GISS-based QRA fingerprint_GISTEMP.nc` &rarr; Regression slope of GISS-based QRA fingerprints against GISTEMP anomalies.
* `RC_pval_GISS-based QRA fingerprint_GISTEMP.nc` &rarr; Corresponding p-values for the above regression.
* `WB_Land_10m.shp` &rarr; World Bank official boundary shapefile (downloaded from https://datacatalog.worldbank.org/search/dataset/0038272).

The following scripts are used to reproduce the figures in the paper:
* `Fig_1.ipynb`
* `Fig_2.ipynb`
* `Fig_3.ipynb`
