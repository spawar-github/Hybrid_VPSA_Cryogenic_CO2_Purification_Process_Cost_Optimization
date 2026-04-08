# Hybrid VPSA + Cryogenic CO2 Purification/Liquefaction Process for Post-combustion CO2 Capture
This MATLAB Runtime-based Windows app optimizes the CO2 avoided cost of a Hybrid VPSA + Cryogenic CO2 Purification Process for Postcombustion CO2 Capture. More details about the integrated techno-economic framework behind the program can be found here. https://doi.org/10.26434/chemrxiv.15000073/v1

IMPORTANT (readme):
=========
(*) Please refer to the table below for the range of the CO2-N2 isotherms and feed CO2 molefractions for which the PVSA surrogate models are trained for.

(*) This Windows program does not need MATLAB licenses to run. We have included  "MATLAB Runtime" (available for free) in the installer along with the program. If you don't already have MATLAB Runtime installed, the program will automatically do that for you. 

(*) The installer is an .exe file; if Windows Defender blocks it, just right-click the file and go to properties, and at the bottom, enable the check box to unblock security. 

The user interface of the app looks as follows:
==========================================================================
<img width="1151" height="991" alt="image" src="https://github.com/user-attachments/assets/d7192351-d616-4b96-bd4c-982c9461fc88" />

Dual-Site Langmuir (DSL) adsorption isotherm model
==========================================================================
The adsorption equilibria for an adsorbent, representing the solid-phase loading in equilibrium with the fluid-phase composition for this adsorbent, are described using a competitive-form dual-site Langmuir (DSL) model (for each component $i$).

$$
q_{i}^{*}=\frac{q_{\mathrm{sb}, i} b_{i} c_{i}}{1+\sum_{i} b_{i} c_{i}}+\frac{q_{\mathrm{sd}, i} d_{i} c_{i}}{1+\sum_{i} d_{i} c_{i}}
$$

where $q_{i}^{*}$ is the solid phase loading of species $i$, in equilibrium with the fluid phase concentration $c_i$, $q_{\mathrm{sb}, i}$ and $q_{\mathrm{sd}, i}$ are the saturation loadings for the two sites and $b_{i}$ and $d_{i}$ are the adsorption equilibrium constants with van’t Hoff temperature dependence as follows:

$$
\begin{aligned}
b_{i} &= b_{0} e^{\left(-\frac{\Delta U_{\mathrm{b}, i}}{R T}\right)} \\
d_{i} &= d_{0} e^{\left(-\frac{\Delta U_{\mathrm{d}, i}}{R T}\right)}
\end{aligned}
$$

$\Delta U_{\mathrm{b}, i}$ and $\Delta U_{\mathrm{d}, i}$ are the internal energies of the two sites, $R$ is the universal gas constant, and $T$ is the temperature. The extended dual-site Langmuir isotherm model explicitly accounts for competition between $\mathrm{CO_2}$ and $\mathrm{N}_{2}$. 

In this study, the DSL isotherm's equal-energy-site (EES) form is used. In this DSL formulation, the saturation capacity of each site is equal for both components, and the enthalpy of adsorption for $\mathrm{N}_{2}$ is equal for both sites. This form is supported by experimental evidence for the case of Zeolite 13X. 


Bounds of the variables used in the surrogate models
================================================================================
<img width="789" height="749" alt="SURROGATE TRAINING RANGE" src="https://github.com/user-attachments/assets/dd78224b-dd76-451f-ac40-d79623bcd06a" />
