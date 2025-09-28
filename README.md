# Predicting Beats Per Minute in Songs

This repository contains the code and data for the Kaggle Playground Series (Season 4, Episode 2) competition. The primary goal of this project is to predict the Beats Per Minute (BPM) of a song based on various musical and audio features. [Competition Link](https://www.kaggle.com/competitions/playground-series-s5e9)

## Project Overview

The core of this project is a regression task where we are given a set of audio features for various songs and are asked to build a model that can accurately predict the BeatsPerMinute. The workflow includes exploratory data analysis, data preprocessing to handle skewed data, and the implementation of various regression models.
The main analysis and model development are performed in the notebook.ipynb Jupyter Notebook.

## Dataset

The data for this competition is provided in two files:

**`datasets/train.csv:`**- The training set, which includes all the audio features as well as the target variable, BeatsPerMinute.
-**`datasets/test.csv:`**- The test set, which contains the same features as the training set but without the target variable.

## Features
The dataset includes the following audio features: 
- `RhythmScore`
- `AudioLoudness`
- `VocalContent`
- `AcousticQuality`
- `InstrumentalScore`
- `LivePerformanceLikelihood`
- `MoodScore`
- `TrackDurationMs`
- `Energy`

## Methodology
The approach taken in notebook.ipynb follows a standard machine learning workflow:

### Exploratory Data Analysis (EDA):
The data is loaded and inspected for missing values and data types.
The distributions of all numerical features are visualized using histograms to identify skewness.
### Data Preprocessing:

- Log Transformation: To handle right-skewed features (VocalContent, AcousticQuality, InstrumentalScore, LivePerformanceLikelihood), a log transformation (np.log1p) is applied to make their distributions more normal.
- Train-Validation Split: The training data is split into a training set and a validation set to evaluate model performance accurately and prevent data leakage.
Feature Scaling: StandardScaler (Z-score scaling) is used to scale all features. The scaler is fitted only on the training data and then used to transform both the training and validation sets.
- Modeling:
A baseline model using Linear Regression was initially built.
The project plan includes experimenting with more advanced regression models such as SVR, LightGBM, XGBoost, and Neural Networks to capture more complex, non-linear patterns in the data.

## Repository Structure:
```
 ├── datasets
 │   ├── train.csv
 │   └── test.csv
 ├── notebook.ipynb
 ├── submission.csv
 └── README.md
```

- `datasets/:` Contains the raw training and test data.
- `notebook.ipynb:` The main Jupyter Notebook with all the analysis and modeling code.
- `submission.csv:` A sample submission file in the format required by Kaggle.
- `README.md:` This file, providing an overview of the project.


##  How to Use

### To run this project:

### Clone the repository:
```bash
 git clone [https://github.com/smusab9152/bpm_pred_songs.git](https://github.com/smusab9152/bpm_pred_songs.git)
 cd bpm_pred_songs
```
### Install dependencies:
It is recommended to use a virtual environment.

```bash
pip install pandas numpy scikit-learn matplotlib jupyter
```
### Run the Jupyter Notebook:
```bash
jupyter notebook`
```
Then, open and run the cells in notebook.ipynb.
