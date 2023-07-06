---
layout: base
permalink: /
---

![](https://raw.githubusercontent.com/cosmic-sense/local-or-global/main/docs/banner.png)

Use this page to assess uncertainty of CRNS-based estimates of soil water content (SWC).
The uncertainty is estimated for two calibration scenarios: 

- **local calibration** (blue line) is the common approach for which SWC in the sensor footprint is estimated from soil sampling then
used to estimate a local value of $N_0$.
- **general (or global) calibration** is based on the estimation of a single value of $N_0$ from a large set of CRNS sensors across Europe.

This interactive tool should support you to decide which calibration strategy is preferable for your CRNS location. 
Find a detailed documentation of both calibration strategies and the corresponding error propagation in this [paper](https://add.ref.to.preprint).

The vertical grey lines highlight the scaled neutron intensities which correspond to
specific values of the volumetric SWC (0.1, 0.2, 0.3, and 0.4 m³/m³). Beware that
changing the bulk density will affect the relationship between
neutron intensity and soil moisture, so that operating the slider will shift
the corresponding lines. 

<iframe src="https://cosmic-sense.github.io/local-or-global/interactive.html"
    width="110%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

**Cite as:** Heistermann, M., T. Francke, M. Schrön, S. E. Oswald: Technical Note: revisiting the general calibration of cosmic-ray
neutron sensors to estimate soil water content [preprint]. Hydrology and Earth System Science Discussions, https://doi.org/10.5194/hess-xx-xxxx-2023.

## Some notes and background

As pointed out above, the [above paper](https://doi.org/10.5194/hess-xx-xxxx-2023) provides 
comprehensive background to understand the above figure. Yet, some more details and thoughts are given below:

- The error propagation results that are shown here always assume an integration interval of 24 h. In other words, they are valid for daily soil moisture estimates. Depending on sensor sensitivity, the error will increase with shorter integration intervals and decrease with longer intervals. In the future, we may add an additional slider to represent the effect of different integration intervals.
- The neutron count rates on the x-axis represent count rates that are scaled to the the "calibrator" level (please see paper for details). While you can change the sensitivity of your probe relative to the calibrator (with a slider), the range of neutron counts on the x-axis will remain the same. However, the error will change as a lower sensitivity implies a higher relative (stochastic) counting error.
- To give you an idea about typical values sensitivities of the most common sensors by Hydroinnova: CRS-1000 (0.45), CRS-1000B (0.67), CRS-2000 (0.87), CRS-2000B (1.15).
- So far, we implemented the error propagation for the local calibration scenario for *one* calibration date only. In the future, we might add the option to include multiple calibration dates.
- The error for the general calibration scenario results from the propagation of errors of following components: bulk density ($\rho_b$, kg/m³), above-ground dry biomass (AGB, in kg/m²), soil organic matter (OM, g/g), lattice water content (LW, $g/g$), detector sensitivity ($f_s^{-1}$), general calibration parameter ($N_0$, cph), the neutron count rate ($N$, cph). However, user input via sliders is only required for the errors of soil bulk density, AGB, and OM. The errors of $N$ and $f_s$ is obtained via the stochastic counting errors (Poisson). For $f_s$, we assumed a 48 h collocation of the sensor with the calibrator probe. The error of $N_0$ was quantified via bootstrapping (see above paper). The variation of the error of LW considered negligible and was assumed to be 0.02 g/g for the sake of simplicity.   
- The error for the general calibration scenario results from the propagation of errors of following components: bulk density ($\rho_b$, kg/m³), above-ground dry biomass (AGB, in kg/m²), soil organic matter (OM, g/g), lattice water content (LW, $g/g$), detector sensitivity ($f_s^{-1}$), general calibration parameter ($N_0$, cph), the neutron count rate ($N$, cph). 
- The challenge in the application of the above tool is to come up with reasonable error estimates for your study site. While the error of the general calibration scenario is dominated by the errors of bulk density and above-ground biomass, the error of the local calibration scenario is governed by the error of the reference soil moisture used for calibration. For the latter, beware that this error is not only a result of the measurement accuracy and precision of your instruments. More importantly, it will be governed by the effects of spatial heterogeneity (horizontal, vertical), lack of representativeness, and by the uncertainty of the horizontal and vertical weighting functions that are used to compute the average soil moisture and bulk density per sensor footprint. For the general calibration scenario, beware that the above-ground dry biomass AGB for grassland or cropland is typically around 1 kg/m², so that the error of AGB will be much lower than 1 kg/m². Much larger error will occur in forest, depending on the method to estimate AGB.
