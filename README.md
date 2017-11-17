# Bayesian Non-Parametric Tumor Segmentation

This project implements a _Gibbs Sampler_ for performing intra-tumor clustering of vector-valued voxel representations in a joint _Hierarchical Dirichlet Process-Markov Random Field_ bayesian non-parametric model. 

The model places each voxel across a population of patients' images into one of a variable number of classes. Utilization of the __HDP__ guarantees correspondence of a class definition for all patients, allowing the algorithm to select the appropriate number of distinct voxel representations based on population information. 

The __MRF__ constraint is placed on the class assignment to reinforce the assumption that under a revealing representation (feature vector) voxels (collections of cells) tend to compose themselves into larger clusters rather than spread them selves into small, disjoint clusters.

The algorithm draws samples from conditional distributions over the full state space vector to infer the latent class assignment parameters and implicit number of unique cell classifications.

## Getting Started
Running the code for the first time is easy, just follow these steps after you have installed all of the dependencies
1. Clone the repo: 
    ```bash
    git clone https://github.com/ryanneph/bnp-tumorseg
    ```
2. Enter the project directory and run on one of the sample datasets:
    ```bash
    cd bnp-tumorseg 
    python bnp-tumorseg/main.py --dataset balloons
    ```
On every iteration, the t-index and k-index _mode_ maps are saved to `./figures/<dataset>/`, and logfiles are saved to `./logs/`. Presently, the full trace histories for t-index, k-index, and beta random variables are stored to file in `./blobs/<dataset>` at the end of the sampling stage.

## Dependencies
_coming soon_

