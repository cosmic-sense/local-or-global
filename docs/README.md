![](https://raw.githubusercontent.com/cosmic-sense/local-or-global/main/docs/banner.png)

Use this page to assess uncertainty of CRNS-based estimates of soil water content (SWC).
The uncertainty is estimated for two calibration scenarios: 

- **local calibration** (blue line) is the common approach for which SWC in the sensor footprint is estimated from soil sampling then
used to estimate a local value of N0.
- **general (or global) calibration** is based on the estimation of a single value of N0 from a large set of CRNS sensors across Europe.

This interactive tool should support you to decide which calibration strategy is preferable for your CRNS location. 
Find a detailed documentation of both calibration strategies and the corresponding error propagation in this [paper](https://add.ref.to.preprint).

The vertical grey lines highlight the scaled neutron intensities which correspond to
specific values of the volumetric SWC (0.1, 0.2, 0.3, and 0.4 m³/m³). Beware that
changing the bulk density will affect the relationship between
neutron intensity and soil moisture, so that operating the slider will shift
the corresponding lines. 

<iframe src="https://cosmic-sense.github.io/local-or-global/interactive.html"
    width="90%"
    height="500"
    scrolling="no"
    seamless="seamless"
    frameborder="0">
</iframe>

Cite as: ...