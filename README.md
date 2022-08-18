<div align="center">
  <img src="https://github.com/nickkunz/smogn/blob/master/media/images/smogn_banner.png">
</div>


## Synthetic Minority Over-Sampling Technique for Regression with Gaussian Noise
[![PyPI version](https://badge.fury.io/py/smogn.svg)](https://badge.fury.io/py/smogn)
[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Build Status](https://travis-ci.com/nickkunz/smogn.svg?branch=master)](https://travis-ci.com/nickkunz/smogn)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/1bfe5a201f3b4a9787c6cf4b365736ed)](https://www.codacy.com/manual/nickkunz/smogn?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=nickkunz/smogn&amp;utm_campaign=Badge_Grade)
![GitHub last commit](https://img.shields.io/github/last-commit/nickkunz/smogn)

## Description
A Python implementation of Synthetic Minority Over-Sampling Technique for Regression with Gaussian Noise (SMOGN). Conducts the Synthetic Minority Over-Sampling Technique for Regression (SMOTER) with traditional interpolation, as well as with the introduction of Gaussian Noise (SMOTER-GN). Selects between the two over-sampling techniques by the KNN distances underlying a given observation. If the distance is close enough, SMOTER is applied. If too far away, SMOTER-GN is applied. Useful for prediction problems where regression is applicable, but the values in the interest of predicting are rare or uncommon. This can also serve as a useful alternative to log transforming a skewed response variable, especially if generating synthetic data is also of interest.
<br>

## Features
1. The only open-source Python supported version of Synthetic Minority Over-Sampling Technique for Regression.

2. Supports Pandas DataFrame inputs containing mixed data types, auto distance metric selection by data type, and optional auto removal of missing values.

3. Flexible inputs available to control the areas of interest within a continuous response variable and friendly parameters for over-sampling synthetic data.

4. Purely Pythonic, developed for consistency, maintainability, and future improvement, no foreign function calls to C or Fortran, as contained in original R implementation.

## Requirements
1. Python 3
2. NumPy
3. Pandas

## Installation
```python
## install pypi release
pip install smogn

## install developer version
pip install git+https://github.com/nickkunz/smogn.git
```

## Usage
```python
## load libraries
import smogn
import pandas

## load data
housing = pandas.read_csv(
    
    ## http://jse.amstat.org/v19n3/decock.pdf
    "https://raw.githubusercontent.com/nickkunz/smogn/master/data/housing.csv"
)

## conduct smogn
housing_smogn = smogn.smoter(
    
    data = housing, 
    y = "SalePrice"
)
```

## Examples
1. [Beginner](https://github.com/nickkunz/smogn/blob/master/examples/smogn_example_1_beg.ipynb) <br>
2. [Intermediate](https://github.com/nickkunz/smogn/blob/master/examples/smogn_example_2_int.ipynb) <br>
3. [Advanced](https://github.com/nickkunz/smogn/blob/master/examples/smogn_example_3_adv.ipynb) <br>

## Applications
1. de Santi, N. S., Rodrigues, N. V., Montero-Dorta, A. D., Abramo, L. R., Tucci, B., & Artale, M. C. (2022). Mimicking the Halo-Galaxy Connection Using Machine Learning. arXiv preprint:2201.06054. https://arxiv.org/abs/2201.06054. 

2. Gangapurwala, S., Geisert, M., Orsolino, R., Fallon, M., & Havoutis, I. (2022). RLOC: Terrain-Aware Legged Locomotion Using Reinforcement Learning and Optimal Control. arXiv preprint:2201.03094. https://arxiv.org/abs/2012.03094.

3. Wang, B., Spessa, A., Feng, P., Hou, X., Yue, C., Luo, J.-J., Ciais, P., Waters, C., Cowie, A., Nolan, R. H., Nikonovas, T., Jin, H., Walshaw, H., Wei, J., Guo, X., Liu, D. L., & Yu, Q. (2021). Extreme Fire Weather Is The Major Driver Of Severe Bushfires In Southeast Australia. Science Bulletin, 67(6), 655-664. https://doi.org/10.1016/j.scib.2021.10.001. 

4. Agrawal, A., & Petersen, M. R. (2021). Detecting Arsenic Contamination Using Satellite Imagery and Machine Learning. Toxics, 9(12), 333. https://doi.org/10.3390/toxics9120333.

## Citations
```
@software{smogn,
  author       = {Nicholas Kunz},
  title        = {{SMOGN}: Synthetic Minority Over-Sampling Technique for Regression with Gaussian Noise},
  year         = {2020},
  publisher    = {PyPI},
  version      = {v0.1.2},
  url          = {https://pypi.org/project/smogn/},
  copyright    = {GPL v3.0}
}
```
## Contributions

SMOGN is open for improvements and maintenance. Your help is valued to make the package better for everyone.

## License

© Nick Kunz, 2022. Licensed under the General Public License v3.0 (GPLv3).

## Reference

Branco, P., Torgo, L., Ribeiro, R. (2017). SMOGN: A Pre-Processing Approach for Imbalanced Regression. Proceedings of Machine Learning Research, 74:36-50. http://proceedings.mlr.press/v74/branco17a/branco17a.pdf.
