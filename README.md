# De-Bias
Project De-Bias: Investigating Biased Data and Classifier Mitigation Strategies 


[![Continuous Integration](https://github.com/Trusted-AI/AIF360/actions/workflows/ci.yml/badge.svg)](https://github.com/Trusted-AI/AIF360/actions/workflows/ci.yml)
[![Documentation](https://readthedocs.org/projects/aif360/badge/?version=latest)](https://aif360.readthedocs.io/en/latest/?badge=latest)
[![PyPI version](https://badge.fury.io/py/aif360.svg)](https://badge.fury.io/py/aif360)
[![CRAN\_Status\_Badge](https://www.r-pkg.org/badges/version/aif360)](https://cran.r-project.org/package=aif360)

The project used AI Fairness 360 toolkit from IBM to demosntrates real world examples of 

This package includes
1) a comprehensive set of metrics for datasets and models to test for biases,
2) explanations for these metrics, and
3) algorithms to mitigate bias in datasets and models.
   It is designed to translate algorithmic research from the lab into the actual practice of domains as wide-ranging
   as finance, human capital management, healthcare, and education. We invite you to use it and improve it.

The [Project](https://github.com/sahilpasricja/De-Bias.git) aims to bring up methods
to make AI more trustable by offering debias capabilities to it along with 
attempting to reasoning behind ots decision making.
. The [tutorials
and other notebooks](./demo) offer a deeper, data scientist-oriented
introduction. The complete API is also available.

We have developed the package with extensibility in mind. This library is still
in development. We encourage the contribution of your metrics, explainers, and
debiasing algorithms.

## Setup

### R

``` r
install.packages("aif360")
```

For more details regarding the R setup, please refer to instructions [here](aif360/aif360-r/README.md).

### Python

Supported Python Configurations:

| OS      | Python version |
| ------- | -------------- |
| macOS   | 3.8 – 3.11     |
| Ubuntu  | 3.8 – 3.11     |
| Windows | 3.8 – 3.11     |

### (Optional) Create a virtual environment

AIF360 requires specific versions of many Python packages which may conflict
with other projects on your system. A virtual environment manager is strongly
recommended to ensure dependencies may be installed safely. If you have trouble
installing AIF360, try this first.

#### Conda

Conda is recommended for all configurations though Virtualenv is generally
interchangeable for our purposes. [Miniconda](https://conda.io/miniconda.html)
is sufficient (see [the difference between Anaconda and
Miniconda](https://conda.io/docs/user-guide/install/download.html#anaconda-or-miniconda)
if you are curious) if you do not already have conda installed.

Then, to create a new Python 3.11 environment, run:

```bash
conda create --name de-bias python=3.11
conda activate de-bias
```

The shell should now look like `(de-bias) $`. To deactivate the environment, run:

```bash
(de-bias)$ conda deactivate
```

The prompt will return to `$ `.

### Install with `pip`

To install the latest stable version from PyPI, run:

```bash
pip install aif360
```

Note: Some algorithms require additional dependencies (although the metrics will
all work out-of-the-box). To install with certain algorithm dependencies
included, run, e.g.:

```bash
pip install 'aif360[LFR,OptimPreproc]'
```

or, for complete functionality, run:

```bash
pip install 'aif360[all]'
```

The options for available extras are: `OptimPreproc, LFR, AdversarialDebiasing,
DisparateImpactRemover, LIME, ART, Reductions, FairAdapt, inFairness,
LawSchoolGPA, notebooks, tests, docs, all`

If you encounter any errors, try the [Troubleshooting](#troubleshooting) steps.


### Troubleshooting

If you encounter any errors during the installation process, look for your
issue here and try the solutions.

#### TensorFlow

See the [Install TensorFlow with pip](https://www.tensorflow.org/install/pip)
page for detailed instructions.

Note: we require `'tensorflow >= 1.13.1'`.

Once tensorflow is installed, try re-running:

```bash
pip install 'aif360[AdversarialDebiasing]'
```

TensorFlow is only required for use with the
`aif360.algorithms.inprocessing.AdversarialDebiasing` class.

#### CVXPY

On MacOS, you may first have to install the Xcode Command Line Tools if you
never have previously:

```sh
xcode-select --install
```


On Windows, you may need to download the [Microsoft C++ Build Tools for Visual
Studio 2019](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16).
See the [CVXPY Install](https://www.cvxpy.org/install/index.html#mac-os-x-windows-and-linux)
page for up-to-date instructions.

Then, try reinstalling via:

```bash
pip install 'aif360[OptimPreproc]'
```


#### Important Links 
Databases
3) https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

Models
1) https://github.com/sahilpasricja/shap
2) https://github.com/amazon-science/fraud-dataset-benchmark/tree/main
3) https://www.kaggle.com/code/gpreda/credit-card-fraud-detection-predictive-models
