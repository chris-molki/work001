# repo_0

[![Python 3.9](https://img.shields.io/badge/python-3.11-blue.svg)](https://www.python.org/downloads/release/python-3111/)
[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![Documentation](https://img.shields.io/badge/docs-master-blue.svg)](https://chris-molki.github.io/gpetas)
![GitHub](https://img.shields.io/github/license/chris-molki/gpetas)

The main motivation of this package is to make
`repo_0` usable for a broader community.
The code follows this [papers, references, literature](https://link.springer.com/article/10.1007/s11222-022-10085-3).

[**Basic Usage**](#basics) | [**Install guide**](#installation) | [**Citing**](#citation) | [**Documentation**](https://chris-molki.github.io/gpetas/)

# Basics

## A model for something or some process
The model is as follows:

```math
\lambda(t,\boldsymbol{x}|H_t,\boldsymbol{\theta}_\mu,\boldsymbol{\theta}_\varphi) = \mu(\boldsymbol{x}|\boldsymbol{\theta}_\mu) + \sum_{i: t_i < t}\varphi(t-t_i,\boldsymbol{x}-\boldsymbol{x}_i|H_t,\boldsymbol{\theta}_\varphi).
```

## Bayesian non-parametric background intensity via Gaussian process modelling

```math
\lambda(t,\boldsymbol{x}|H_t,\boldsymbol{\theta}_\mu,\boldsymbol{\theta}_\varphi) = \frac{\bar{\lambda} }{1+e^{-f(\boldsymbol x)}}+ \sum_{i: t_i < t}\varphi(t-t_i,\boldsymbol x-\boldsymbol x_i|H_t,\boldsymbol \theta_\varphi).
```
* $f\sim GP()$

## Bayesian inference via data augmentation and Gibbs sampling

Posterior distribution has no simple closed form. We use Markov chain Monte Carlo (MCMC) methods for generating samples from 
the joint posterior distribution. More specifically we employ MH within Gibbs sampling.

# Installation 

`repo_0` requires `python>=3.9`.
For a proper installation create a virtual environment first and activate it. Just do the following.

## Create virtual environment
```
conda create --name repo_0_env python=3.9
conda activate repo_0_env
```
This creates a virtual environment with python==3.9 installed, and activates it.
In order to return to the base environment afterwards, use: *conda deactivate*.

## Package installation
Clone the repository into a directory and change into the folder and do the following.
```
git clone https://github.com/chris-molki/repo_0.git
cd repo_0
pip install -r requirements.txt
pip install -r requirements_docs.txt
pip install -e .
```

`repo_0` has been installed in developer/editable mode.

***Hint:*** In case there is a problem with pip installation 
of a subpackage/library just try,
```
conda install -c conda-forge --file requirements.txt
```

### For online data downloads install pyXXX
First make clear that *repo_0_env* is activated,
otherwise activate it via *conda activate repo_0_env*.
If *repo_0_env* is activate, install pyXXX as follows,
```
conda install --channel conda-forge pyXXX
```

## Build documentation locally

Change into the folder *docs*
and generate a local documentation in html.
```
cd docs
make html
```
For opening the documentation just open *index.html* file
```
open ./build/html/index.html 
```

## Uninstall ```repo_0```

Uninstall or remove ```repo_0``` and 
virtual *environment repo_0_env* easily 
as follows.
Just change to the parent directory 
and remove folder *repo_0* recursively
```
cd ..
rm -rf repo_0
```
Return to bases environment by deactivating virtual environment *repo_0_env*
```
conda deactivate
```
Subsequently remove virtual environment *repo_0_env* using the following 
command,
```
conda env remove -n repo_0_env
```
or just delete the directory of *repo_0_env*.

# Short installation guide
Create a virual environment first.
Clone the repository into a directory and go into the folder. Just do the following
```bash
pip install git+https://github.com/chris-molki/repo_0.git
```
Make sure the requirements (requirements.txt) are full-filled.

For code development do
```bash
git clone https://github.com/chris-molki/repo_0.git
cd repo_0/
pip install -r requirements.txt
pip install -e .
```

# Citation

To cite this repository:

```
@software{repo_0_2024,
	author = {CM},
	title = {{repo_0}: A Python package for modeling xyz.},
	url = {https://github.com/chris-molki/repo_0},
	version = {0.0.1},
	year = {2024},
}
```
The development of the repository is based on the following
publication,

```
@article{Somebody2022,
	title={Some important model and its implementation},
	author={Somebody, Author2 and Author3},
	journal={Statistics and Computing},
	volume={xx},
	number={x},
	pages={x--xx},
	year={2022},
	publisher={xxx}
}
```
