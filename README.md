#BZAN 542 Group Project

## Introduction
Welcome to the comprehensive analysis of used car data using various machine learning techniques and workflows in R. This repository dives deep into the world of predictive modeling and data exploration, showcasing the power of packages such as `tidymodels`, `embed`, `stringdist`, `probably`, `bonsai`, `textrecipes`, and `finetune`. The analysis covers everything from initial data loading to model evaluation and comparison.

## Table of Contents
1. [Installation](#installation)
2. [Parallel Processing](#parallel-processing)
3. [Data Preparation and Exploration](#data-preparation-and-exploration)
4. [Data Preprocessing](#data-preprocessing)
5. [Linear Regression Model](#linear-regression-model)
6. [LightGBM Model](#lightgbm-model)
7. [LightGBM Racing](#lightgbm-racing)
8. [Final Model and Evaluation](#final-model-and-evaluation)
9. [XGBoost Model (Optional)](#xgboost-model-optional)
10. [Workflow Sets](#workflow-sets)
11. [Ensemble Model Evaluation](#ensemble-model-evaluation)
12. [Workflow Set Racing](#workflow-set-racing)
13. [GitHub Repository Structure](#github-repository-structure)

## Installation
To replicate the analysis, ensure you have the required packages installed. Run the following code to install the necessary packages once:

```R
pkgs <- 
  c("bonsai", "doParallel", "embed", "finetune", "lightgbm", "lme4",
    "plumber", "probably", "ranger", "rpart", "rpart.plot", "rules",
    "splines2", "stacks", "text2vec", "textrecipes", "tidymodels", 
    "vetiver", "remotes","textrecipes")

install.packages(pkgs)
```

## Parallel Processing
Efficient parallel processing is crucial for large datasets. Adjust the number of cores based on your system:

```R
cores <- parallelly::availableCores(logical = FALSE)
cl <- parallel::makePSOCKcluster(cores)
doParallel::registerDoParallel(cl)
```

## Data Preparation and Exploration
The journey starts with loading essential libraries and splitting the dataset into training and testing sets. The analysis delves into exploratory data visualization, covering key car features such as year, price, mileage, fuel type, assembly, and more.

## Data Preprocessing
A meticulous recipe is crafted to preprocess the data, addressing encoding, dummy variables, handling missing values, and normalization. The processed data becomes the foundation for training linear regression models.

## Linear Regression Model
A robust linear regression model is trained and rigorously evaluated using resampling techniques. Metrics such as RMSE, MAE, and R-squared are calculated and thoughtfully visualized to offer insights into the model's performance.

## LightGBM Model
The journey into machine learning intensifies with the training of a LightGBM model. Hyperparameter tuning takes center stage, and the best hyperparameters are selected based on the RMSE metric. The model's performance is vividly visualized, and predictions are meticulously compared against the actual values.

## LightGBM Racing
The pursuit of optimization continues with a racing process dedicated to LightGBM. The goal is to squeeze out every ounce of performance improvement. The best hyperparameters from the racing process are chosen to train the final LightGBM model.

## Final Model and Evaluation
With the best hyperparameters in hand, the LightGBM workflow is finalized. The model is trained on the entire dataset, and its performance is critically evaluated on the test set. The final results are presented, and the model's predictions are graphically compared to the actual values.

## XGBoost Model
For enthusiasts seeking alternative approaches, an optional XGBoost model is also presented. The training process mirrors that of LightGBM, and the model's performance is juxtaposed against the LightGBM model for a comprehensive comparison.

## Workflow Sets
A sophisticated ensemble approach is introduced, where various workflows, including regularized regression, decision tree, random forest, and XGBoost, are combined into a workflow set. Hyperparameter tuning and stacking are employed to create a powerful ensemble model.

## Ensemble Model Evaluation
The ensemble model undergoes thorough evaluation on the test set. Visualizations of various metrics offer a holistic view of its performance, showcasing the strengths of the ensemble approach.

## Workflow Set Racing
To ensure the ensemble model reaches its peak potential, a racing optimization process is undertaken. The best configurations are identified to further enhance the overall performance of the workflow set.

## GitHub Repository Structure
This GitHub repository is meticulously organized, featuring dedicated folders for data, scripts, and models. The primary R script encapsulates the entire analysis, providing a comprehensive overview. Users are encouraged to explore, modify, and contribute to this analysis, fostering collaboration and knowledge sharing.

Feel free to embark on this journey of data exploration and predictive modeling!
