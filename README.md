# Stay local or go global?

This repository provides the code to reproduce the figures shown in the following preprint:

Heistermann, M., T. Francke, M. Schrön, S. E. Oswald: Technical Note: revisiting the general calibration of cosmic-ray
neutron sensors to estimate soil water content [preprint]. Hydrology and Earth System Science Discussions, https://doi.org/10.5194/hess-xx-xxxx-2023.

It also contains the Python and JavaScript code to produce the interactive tool
available via http://cosmic-sense.github.io/local-or-global.

## User-relevant repository content

- `data/caldata.csv`: contains the condensed CRNS calibration data that was compiled
from four recent ESSD data publications (Fersch et al. 2019, Heistermann et al. 2022, Bogena et al. 2022, Heistermann et al. 2023).
- `general-calibration.ipynb`: jupyter notebook to reproduce the analysis shown in the manuscript
- `bokehfig.ipynb`: jupyter notebook to produce the interactive Bokeh figure shown [here](http://cosmic-sense.github.io/local-or-global)
- `figs`: saved figures
- `docs`: github pages content


## Installation

The dependencies required to run the notebooks are recommended to be installed as follows:

```
$ conda create --name newenv python=3.7
$ conda activate newenv
(newenv) $ conda install -c conda-forge numpy scipy pandas matplotlib jupyter xlrd h5py netCDF4 xarray gdal deprecation xmltodict semver wradlib bokeh
```

After that, you can download the package `cosmicsense` from https://github.com/heistermann/cosmicsense and install from source via

`(newenv) $ python setup.py install`





