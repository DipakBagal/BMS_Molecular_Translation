# Disclaimer

This repository is work-in-progress. Visit soon to see the codes.



# BMS Molecular Translation

The top-5% solution to the [BMS Molecular Translation](https://www.kaggle.com/c/bms-molecular-translation) on Kaggle.

![sample](https://i.postimg.cc/sghDH7f9/Screen-2021-06-04-at-09-38-30.jpg)


## Summary

Organic chemists frequently draw out molecular work with the Skeletal formula, a structural notation used for centuries. Decades of scanned publications and medical documents contain drawings that are not annotated with the chemical formulas. Currently, time-consuming and manual work of experts is required to reliably convert chemical structure images into a readable formula format. Automated recognition of optical chemical structures, with the help of machine learning, could speed up research and development efforts.

The goal of the project is to develop a deep learning based algorithm for chemical image captioning. In other words, the project aims at translating unlabeled chemical images into the text formula strings. To do that, I work with a large dataset of more than 4 million chemical images provided by Bristol-Myers Squibb.

My solution is an ensemble of seven CNN-LSTM Encoder-Decoder models. All models are implemented in `PyTorch `. The table below summarizes the main architecture and training parameters. The solution reaches the test score of 1.31 LD and places 47th out of 874 competing teams. The detailed summary is provided in [this writeup](https://www.kaggle.com/c/bms-molecular-translation/discussion/243845).

![models](https://i.postimg.cc/cLrTp1Pc/Screen-2021-06-04-at-10-17-02.jpg)


## Project structure

The project has the following structure:
- `codes/`: `.py` scripts with training, inference and image processing functions
- `notebooks/`: `.ipynb` Colab-friendly notebooks for data augmentation, training and inference
- `input/`: input data (not included due to size constraints, can be downloaded [here](https://www.kaggle.com/c/bms-molecular-translation))
- `output/`: model configurations, weights and figures exported from the notebooks


## Reproducing solution

The solution can be reproduced in the following steps:
1. Downloading competition data and placing it in the `input/` folder.
2. Running five training notebooks `model_x.ipynb` to obtain weights of base models.
3. Running the ensembling notebook `notebook_10_ensembling.ipynb` to obtain the final predictions.

All `model_x.ipynb` notebooks have the same structure and differ in model/data parameters. Different versions are included to ensure reproducibility. To understand the training process, it is sufficient to go through the `codes/` folder and inspect one of the modeling notebooks. The ensembling code is also provided in this [Kaggle notebook](https://www.kaggle.com/kozodoi/47th-place-solution-bms-ensembling).

More details are provided in the documentation within the scripts & notebooks.