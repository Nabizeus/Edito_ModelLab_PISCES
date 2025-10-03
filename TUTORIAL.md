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




