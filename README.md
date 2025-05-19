Planetary Wave Resonance 
==============================================
Repository including the code needed to reproduce the results present in <a href="https://www.pnas.org/doi/***">Li et al., Increased frequency of planetary wave resonance events over the past half-century </a>, PNAS, Volume ***, Issue **, 2025.

Related Publication
-------------------
X. Li, M. E. Mann, M. F. Wehner, S. Christiansen,  Increased frequency of planetary wave resonance events over the past half-century, Proc. Natl. Acad. Sci. U.S.A. 122 (15) e2413503122, <a href="https://doi.org/10.1073/pnas.2413503122">https://doi.org/10.1073/pnas.2413503122</a> (2025).

Files description
-----------------
* `architectures.py` &rarr; Definition and building of the Deep Neural Network (DNN) used in the Transfer Learning (TL) approach
* `area_cella.csv` &rarr; Area weighting factors for each gridpoint of the grid corresponding to `CanESM5_CanOE_grid` used in this work
* `CanESM5_CanOE_grid` &rarr; Description of the grid used in this work (Grid from CanESM5-CanOE simulation)
* `transferring_env.yml` &rarr; YAML file needed to create the conda environment to reproduce the experiments and the figures
* `erf_estimates_with_aerosols_Zebedee_Nichols.csv` &rarr; Dataset of Effective Radiative Forcing values for each year
* `lib.py` &rarr; Routines called in several scripts
* `variables.py` &rarr; Definition of variables used in the scripts
* `BEST_regridded_annual_1979-2022.nc` &rarr; Berkeley Earth Surface Temperatures (BEST) observational maps resulting from the preprocessing (i.e., regridding to CanESM5-CanOE grid, computation of annual average maps, deletion of years out of 1979-2022)
* `gaussian_noise_5` &rarr; Directory containing BEST observational maps added with Gaussian noise to be used for TL on observations
* `Land_and_Ocean_global_average_annual.txt` &rarr; Average annual uncertainties associated with BEST observational data. The column headers were manually removed for ease of use

The following scripts are used to download and process CMIP6 and BEST data:
* `CMIP6_download_process.py` &rarr; Download of CMIP6 simulations from Climate Data Store and processing
* `BEST_data_processing.py` &rarr; Processing of BEST observational maps
* `BEST_data_add_gaussian_noise.py` &rarr; Generation of BEST observational maps added with Gaussian noise to be used for TL on observations

The following scripts are used to perform Training, TL on Simulations (leave-one-out cross-validation procedure) and the TL on Observations:
* `First_Training.py` &rarr; Training of each DNN on one of the 22 CMIP6 Earth System Models (ESMs) simulations under one of the three SSP scenarios (SSP2-4.5, SSP3-7.0, SSP5-8.5)
* `Transfer_learning_simulations.py` &rarr; TL of the (pre-trained) DNNs on ESMs simulations according to the leave-one-out cross-validation (LOO-CV) procedure
* `Transfer_learning_observations.py` &rarr; TL of the (pre-trained) DNNs on BEST observational data
