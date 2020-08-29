# prescient
Code for recent paper submission of PRESCIENT (Potential eneRgy undErlying Single Cell gradIENTs) for generative modeling of single-cell time-series. 
+ Current paper version: https://www.biorxiv.org/content/10.1101/2020.08.26.269332v1

![trajectories_gif](gifs/trajectories.gif)

## Setup

+ pytorch 1.4.0
+ geomloss 0.2.3, pykeops 1.3
+ numpy, scipy, pandas, sklearn, tqdm, annoy
+ Recommended: An Nvidia GPU with CUDA support for GPU acceleration

## Organization 

`/src` contains code for training and evalating models:
+ `train.py` implements shared functions and classes, including the model and the main pre-training and training loop
+ `weinreb.py` implements training and evaluation for interpolation and fate prediction tasks on the Weinreb et al. dataset
+ `veres.py` implements training on the Veres et al. dataset
+ To implement PRESCIENT for your dataset, follow the examples in `weinreb.py` and `veres.py` 

`/scripts` contains example bash scripts for fitting models: 
+ `weinreb-interpolate.sh` trains 5 seeds of 2 layer 400 unit models on only lineage tracing data with ground truth proliferation rates for the interpolation task on the Weinreb et al. dataset
+ `weinreb-fate.sh` trains 5 seeds of 2 layer 400 unit models on all data with estimated proliferation rates for clonal fate bias prediction on the Weinreb et al. dataset
+ `veres-fate.sh` trains 5 seeds of 2 layer 400 unit models with estimated proliferation rates on the Veres et al. dataset

`/notebooks` contains preprocessing, analysis and visualization workflows:
+ `02{a-e}-weinreb2020-interpolation-*` contains workflows for the interpolation task on the Weinreb et al. dataset
+ `03{a-d}-weinreb2020-fate-*` contains workflows for fate prediction task on the Weinreb et al. dataset
+ `04{a-d}-weinreb2020-perturbations-*` contains visualizations for perturbational experiments on the Weinreb et al. dataset
+ `05{a-d}-veres2019-*` contains workflows for fate prediction on the Veres et al. dataset
+ `05{c-e}-veres2019-perturbations-*` contains visualizations for timing perturbations on the Veres et al. dataset.
+ `06{a-e}-veres2019-perturbations-* ` contains visualizations for large-scale perturbational screens and cell subset perturbations on the Veres et al. dataset.

## Pre-processed data

Pre-processed data as generated by the workflows above can be downloaded from [here]()

## Pre-trained models

Pre-trained models used for perturbation experiments can be downloaded from [here]()  

## Bugs & Suggestions

Please report any bugs, problems, suggestions or requests as a [Github issue](https://github.com/gifford-lab/prescient/issues)