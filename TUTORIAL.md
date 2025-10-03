# Edito_ModelLab_PISCES
Application of LSTM on PISCES BioGeoChemistry variables for prediction

This Notebook describes the steps toward creating a proof-of-concept of an ML emulator to forecast the bio-geochemical variable INTPP (net primary carbon production by phytoplankton) using an RNN architecture (Recurrent Neural Network) of the class LSTM (Long Short-Term Memory).



1. ML NN approach:
Application of Tensorflow Keras Long Short Term Memory (LSTM) cells for a Sequential model architecture on time series analysis 
2. Testing multivariate LSTM and multivariate ARIMA time series with external sub-species time series as external factors of multivariate sense in marine biogeochemistry data product.
3. 
4. The test shows a performance for LSTM with 10k parameter size for single geo-location point grid of RSME < 3%.
7. A comparison of statistical ARIMA model have been proceeded, where LSTM shows better performance and hence the ARIMA part is excluded from the notebook.
8. The analysis has been performed for 9 variables and one predictor value of lag-1 (autoregression lag 1).
9. Sampled selected points
10. Global sampling that will have a total of 360lonx290latx12monthsx60years that will lead to 3 Billion parameter pre-trained model and only applicable on a HPC (High Performance Computer) as MN5 (MareNostrum 5).
11. Sampling, with 10 selected areas,  will reduce this raw model to a 10lonx10latx12monthsx60years with only  3 Million parameters.

## Roadmap
**Preliminary**
- [x] Tested RNN, LSTM, ARIMA, Linear models on synthetic data
- [x] Tested multivariate LSTM and ARIMA on synthetic data
- [x] Tested the approach on CMIP monthly PISCES data set of different species
- [x] Tested for different norms and geo-locations 




**Optimisation of external factors**
- [x] Checked the cross-correlation for different time lags between the main series and external factors
- [x] ARIMA and LSTM have already pre-built-in functions to add multivariate computation, so that the maximum cross-correlation method is not required.
- [x] Normalisation of the variables is required to mitigate the huge value range difference between parameters. Without this step, both models fail.
- [x] Normalisation can be performed either by applying the same approach of MinMax Scaler, Normal Scaler, Log Scaler, etc. Since different variables behave differently, for each variable, a different normalisation procedure is required.
- [x] First, each variable is multiplied by a factor that leads to a similar value range of 4-30. Then log-scaler is applied for INTPP, as it shows power law variation and a constant value of 12 is added to avoid 0 values, to avoid failure of the models.



# Tutorial

**Step by Step tutorial of the notebook**

The output of the notebook has been supressed to keep the size of the notebook small. The user can download the notebook and run it in own environment or on colab.
The preliminary to run the notebook are the data set that should be available and downloaded beforehand.

**Dataset**
  
- Ocean Monthly dataset from CMIP EC-Earth3 simulation of pre-industrial control and of 1ºx1º grid resolution.
 <img src="./plots/data.png" alt="Data Set" width="400"> 

**Varialbes**

For this work we only use 9 variables for testing:

- Z(t) = INTPP : net_primary_mole_productivity_of_biomass_expressed_as_carbon_by_phytoplankton [mol m-2 s-1]

- Z(t-1) = INTPP Lag 1:

- A(t) = NO3 3D (Column integrate 200m or at const. level): mole_concentration_of_nitrate_in_sea_water [mol m-3]

- B(t) = PO4 3D (Column integrate 200m or at const. level): mole_concentration_of_dissolved_inorganic_phosphorus_in_sea_water [mol m-3]

- C(t) = Si 3D (Column integrate 200m or at const. level)

- D(t) = THETAO 3D (Column integrate 200m or at const. level): sea_water_potential_temperature [degC]

- E(t) = MLOTST: ocean_mixed_layer_thickness_defined_by_sigma_t [m]

- G(t) = DFE 3D (Column integrate 200m or at const. level): mole_concentration_of_dissolved_iron_in_sea_water [mol m-3]

- H(t) = ZMESOOS (Surface) Only from 1959..onwards: Surface Mole Concentration of Mesoozooplankton expressed as Carbon in Sea Water [mol m-3]

- I(t) = ZMICROOS (Surface) Only from 1959..onwards: Microzooplankton [mol m-3]

- L(t) = RSNTDS (Surface): Net Surface Downward Shortwave Radiation at Surface [W m-2]



## Mathematical Background

The algorithm is based on the following equation:

$$
f(x) = \sum_{i=0}^{n} a_i x^i
$$

Where $n$ represents the degree of the polynomial.




