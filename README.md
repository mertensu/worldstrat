# The WorldStrat Software Package

This is the code repository for the WorldStrat dataset, used to generate the dataset and train several super-resolution benchmarks on it.

# Quick Start
Follow the Dataset Exploration notebook, or:
- [Download and install Miniforge](https://github.com/conda-forge/miniforge/releases/tag/4.12.0-2).
- Clone the repository: `git clone https://github.com/worldstrat/worldstrat`.
- Install the environment: `mamba env create -n worldstrat --file environment.yml`.
- [Download the dataset from Kaggle.](https://www.kaggle.com/datasets/jucor1/worldstrat)
- Create an empty `dataset` folder in the repository root and unpack the dataset there.
- Run the `Dataset Exploration` notebook, or any of the other notebooks, using the `worldstrat` environment.

## What is WorldStrat?

**Nearly 10,000 km² of free high-resolution satellite imagery** of unique locations which ensure stratified representation of all types of land-use across the world: from agriculture to ice caps, from forests to multiple urbanization densities.

![A mosaic showing randomly selected high-resolution imagery from the dataset.](https://i.imgur.com/cESfjpB.png)

Those locations are also enriched with typically under-represented locations in ML datasets: sites of humanitarian interest, illegal mining sites, and settlements of persons at risk.

Each high-resolution image (1.5 m/pixel) comes with multiple temporally-matched low-resolution images from the freely accessible lower-resolution Sentinel-2 satellites (10 m/pixel). 

We accompany this dataset with a paper, datasheet for datasets and an open-source Python package to: rebuild or extend the WorldStrat dataset, train and infer baseline algorithms, and learn with abundant tutorials, all compatible with the popular EO-learn toolbox.

![A world map showing the location of the dataset imagery with their source labels (ASMSpotter, Amnesty, UNHCR, Randomly Sampled/Landcover).](https://i.imgur.com/QLpnXE5.jpeg)

# Why make this?

We hope to foster broad-spectrum applications of ML to satellite imagery, and possibly develop the same power of analysis allowed by costly private high-resolution imagery from free public low-resolution Sentinel2 imagery. We illustrate this specific point by training and releasing several highly compute-efficient baselines on the task of Multi-Frame Super-Resolution. 

# Data versions and structure:

Due to Kaggle's size limitation of ~107 GB, we've uploaded what we call the "core dataset" here, which consists of:

- 12-bit radiometry high-resolution images, downloaded through SentinelHub's API.
- 8 temporally-matched low-resolution Sentinel-2 Level-2A revisits for each high-resolution image.

We used this core dataset to train the models we used as benchmarks in our paper, and which we distribute as pre-trained models.

Other data we have, which we will release as well as a supplement:

- 12-bit radiometry high-resolution images in their raw format, downloaded directly from Airbus.
- 8-bit radiometry high-resolution images, generated by converting both 12-bit variants down to 8-bits.
- 16 temporally-matched low-resolution Sentinel-2 Level-2A revisits for each high-resolution image.
- 16 temporally-matched low-resolution Sentinel-2 Level-1C revisits for each high-resolution image.

# How can I use this?

We recommend starting with the downloading and unpacking the dataset, and using the `Dataset Exploration` notebook to explore the data.  
After that, you can also check out our source code which contains notebooks that demonstrate:

- Generating the dataset by randomly sampling the entire planet and stratifying the points using several datasets.
- Training a super-resolution model that generates high-resolution imagery using low-resolution Sentinel-2 imagery as input. 
- Running inference/generating free super-resolved high-resolution imagery using the aforementioned model.

![An image demonstrating the difference between a low-resolution image and it's super-resolved high-resolution image, generated using the pre-trained model.](https://i.imgur.com/aVL9Jy4.png)

# Licences 

- The high-resolution Airbus imagery is distributed, with authorization from Airbus, under Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0).
- The labels, Sentinel2 imagery, and trained weights are released under Creative Commons with Attribution 4.0 International (CC BY 4.0).
- This source code repository under 3-Clause BSD license.
