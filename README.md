[Slides](https://github.com/lee-jin81/metis_project_4_classification/blob/main/Slides_classification.pdf) <br>
[Final writeup](https://github.com/lee-jin81/metis_project_4_classification/blob/main/Writeup_classification.pdf) <br>
[Code](https://github.com/lee-jin81/metis_project_4_classification/blob/main/project_4_microbes_v_FINAL.ipynb) <br>
[MVP](https://github.com/lee-jin81/metis_project_4_classification/blob/main/mvp_classification.md)

# Abstract 
In this project, I am classifying microorganisms from a dataset containing features of microscope images. The target is 1 if it is ‘Ulothrix’ and 0 for ‘Other’. Machine learning classification models were used in this project and the best model was selected through validation. The dataset was split into a training and testing set for proper evaluations. Models were scored using cross-validation. Testing set that was unseen was used to evaluate the best model at the end of the model selection. F1 score was used to select the best model and to optimize the model’s parameters since both true positives and true negatives are of importance to the goal of the project. Random forests was the best model with an accuracy of 90% on the train set. The model suffered from some overfitting, and the test accuracy was 80% with better prediction on the 0 class (Other).

# Introduction
Microscope image analysis is a laborious and tedious job requiring skilled and trained personnel to perform the job. The analysis is prone to human error. The lab personnel need to spend hours a day to identify hundreds of cell images and researchers may be susceptible to decision fatigue and bias. Some microscope software has built in functions to measure the features of the images in an automated way, but the scientist still has to identify what the image is. Automating the classification of cell images by predicting the type such as fungi or algae, can help speed up identification of microorganisms while reducing human errors and bias. 
I’m proposing to build a machine learning model that can be used to classify the type of a microorganism based on features extracted from microscope image analysis. As a proof of concept, my model will predict whether features of an algae are Ulothrix or not. The automated classification feature can be used alongside the microscope software to speed up overall image analyses while reducing bias and error. 

# Data
Source: Kaggle Microbes dataset: https://www.kaggle.com/datasets/sayansh001/microbes-dataset

A row of data represents the features of a microscope image of a particular microorganism.
The 15 columns of interest are: solidity, eccentricity, equivdiameter, extrema, filled area, extent, orientation, euler number, bounding box, convex hull, major axis length, minor axis length, perimeter, centroid, and area. These are numerical features extracted from microscope images of organisms. 

**Target**
I will predict whether the algae is Ulothrix or not.

# Tools
* Exploratory data analysis: Pandas
* Visualizations: matplotlib and seaborn
* Classification model: sklearn

# Algorithms 
Feature engineering
•	Target labels were converted to numerical values of 1 and 0
•	Duplicated entries across all columns were removed

### Models
K-nearest neighbors, Logistic regression, Random forests, and Gradient boosted machine. 

### Model evaluation and selection 
The entire training set split into 80% train and 20% test. The validation method used was cross validation with StratifiedKFold. To account for class imbalance, minority class was oversampled.

### Best model
Random Forests 5 fold cross-validation scores
* Accuracy 0.897
* Precision: 0.879
* Recall 0.923
* F1: 0.900



