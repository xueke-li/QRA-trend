Planetary Wave Resonance 
==============================================
Repository including the code needed to reproduce the results present in <a href="https://www.pnas.org/doi/10.1073/pnas.2504482122">Li et al., Increased frequency of planetary wave resonance events over the past half-century </a>, PNAS, Volume 122, Issue 00, 2025.

Related Publication
-------------------
X. Li, M. E. Mann, M. F. Wehner, S. Christiansen,  Increased frequency of planetary wave resonance events over the past half-century, Proc. Natl. Acad. Sci. U.S.A. 122 (00) e2413503122, <a href="https://doi.org/10.1073/pnas.2504482122">https://doi.org/10.1073/pnas.2504482122</a> (2025).
M. E. Mann, S. Rahmstorf, K. Kornhuber, B. A. Steinman, S. K. Miller, S. Petri, D. Coumou, Projected changes in persistent extreme summer weather events: The role of quasi-resonant amplification. Sci. Adv. 4(10) eaat3272, <a href="https://doi.org/10.1126/sciadv.aat3272">https://doi.org/10.1126/sciadv.aat3272</a> (2018).
M. E. Mann, S. Rahmstorf, K. Kornhuber, B. A. Steinman, S. K. Miller, D. Coumou, Influence of anthropogenic climate change on planetary wave resonance and extreme weather events. Sci Rep 7(1), 45242, <a href="https://doi.org/10.1038/srep45242">https://doi.org/10.1038/srep45242</a> (2017). 


Files description
-----------------
The following data are used to reproduce Fig. 1:
* `QRA_freq_1950-2024.csv` &rarr; Counts of quasi-resonant amplification (QRA) of planetary waves during boreal summer (JJA), 1950–2024
* `GISTEMP_latband_2017_1880-2016_jja_lat-25n-75n_QRAindex.nc` &rarr; QRA fingerprint series calculated from GISTEMP surface temperature observations, 1880-2016 
* `HadCRUT_latband_2017_1850-2016_jja_lat-25n-75_QRAindex.nc` &rarr; QRA fingerprint series calculated from HadCRUT4 surface temperature observations, 1850-2016 
* `HadCRUT_krig_latband_2017_1850-2016_jja_lat-25n-75n_QRAindex.nc` &rarr; QRA fingerprint series calculated from Cowtan and Way surface temperature observations, 1850-2016

The following data are used to reproduce Fig. 2:
* `era5_monthly_1.5deg_v300_1950_2024_JJAmean_37.5N-57.5N_delplev-dct.nc` &rarr; Wave amplitudes calculated from monthly ERA5 data by applying a zonal fast Fourier transformation (FFT) to JJA averaged 300 hPa meridional wind fields (37.5°N to 57.5°N; 1950-2024)

The following data are used to reproduce Fig. 3:
* `erf_estimates_with_aerosols_Zebedee_Nichols.csv` &rarr; Dataset of Effective Radiative Forcing values for each year
* `lib.py` &rarr; Routines called in several scripts
* `variables.py` &rarr; Definition of variables used in the scripts
* `BEST_regridded_annual_1979-2022.nc` &rarr; Berkeley Earth Surface Temperatures (BEST) observational maps resulting from the preprocessing (i.e., regridding to CanESM5-CanOE grid, computation of annual average maps, deletion of years out of 1979-2022)
* `gaussian_noise_5` &rarr; Directory containing BEST observational maps added with Gaussian noise to be used for TL on observations
* `Land_and_Ocean_global_average_annual.txt` &rarr; Average annual uncertainties associated with BEST observational data. The column headers were manually removed for ease of use
* `architectures.py` &rarr; Definition and building of the Deep Neural Network (DNN) used in the Transfer Learning (TL) approach
* 
The following scripts are used to download and process CMIP6 and BEST data:
* `CMIP6_download_process.py` &rarr; Download of CMIP6 simulations from Climate Data Store and processing
* `BEST_data_processing.py` &rarr; Processing of BEST observational maps
* `BEST_data_add_gaussian_noise.py` &rarr; Generation of BEST observational maps added with Gaussian noise to be used for TL on observations

The following scripts are used to perform Training, TL on Simulations (leave-one-out cross-validation procedure) and the TL on Observations:
* `First_Training.py` &rarr; Training of each DNN on one of the 22 CMIP6 Earth System Models (ESMs) simulations under one of the three SSP scenarios (SSP2-4.5, SSP3-7.0, SSP5-8.5)
* `Transfer_learning_simulations.py` &rarr; TL of the (pre-trained) DNNs on ESMs simulations according to the leave-one-out cross-validation (LOO-CV) procedure
* `Transfer_learning_observations.py` &rarr; TL of the (pre-trained) DNNs on BEST observational data
