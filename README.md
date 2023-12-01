# BZAN_542_Group_Project

## Introduction
This R code covers a comprehensive analysis of used car data using various machine learning techniques and workflows. The main libraries used include `tidymodels`, `embed`, `stringdist`, `probably`, `bonsai`, `textrecipes`, and `finetune`. The analysis includes data preprocessing, model training, tuning, and evaluation.

## Installation
To replicate the analysis, ensure you have the required packages installed. Uncomment and run the following code to install the necessary packages:

```R
#pkgs <- 
#  c("bonsai", "doParallel", "embed", "finetune", "lightgbm", "lme4",
#    "plumber", "probably", "ranger", "rpart", "rpart.plot", "rules",
#    "splines2", "stacks", "text2vec", "textrecipes", "tidymodels", 
#    "vetiver", "remotes","textrecipes")
#
#install.packages(pkgs)
```

## Parallel Processing
The analysis utilizes parallel processing for efficiency. Adjust the number of cores based on your system:

```R
cores <- parallelly::availableCores(logical = FALSE)
cl <- parallel::makePSOCKcluster(cores)
doParallel::registerDoParallel(cl)
```

## Data Preparation and Exploration
The code begins with loading libraries and splitting the dataset into training and testing sets. Exploratory data analysis includes visualizations of car features like year, price, mileage, fuel type, assembly, and more.

## Data Preprocessing
A recipe is created to preprocess the data, including encoding, dummy variables, handling missing values, and normalization. The resulting processed data is then used to train linear regression models.

## Linear Regression Model
A linear regression model is trained and evaluated using resampling techniques. Metrics such as RMSE, MAE, and R-squared are calculated and visualized.

## LightGBM Model
A LightGBM model is trained using hyperparameter tuning. The best hyperparameters are selected based on the RMSE metric. The model's performance is visualized, and predictions are compared against the actual values.

## LightGBM Racing
A racing optimization is performed for LightGBM to further improve model performance. The best hyperparameters from the racing process are used to train the final LightGBM model.

## Final Model and Evaluation
The best hyperparameters obtained from the racing process are used to finalize the LightGBM workflow. The final model is then trained on the entire dataset, and its performance is evaluated on the test set.

## XGBoost Model (Optional)
An XGBoost model is also trained using a similar process, and its performance is compared with the LightGBM model.

## Workflow Sets
Several workflows, including regularized regression, decision tree, random forest, and XGBoost, are combined into a workflow set. Hyperparameter tuning and stacking are performed on this set to create an ensemble model.

## Ensemble Model Evaluation
The ensemble model is evaluated on the test set, and its performance is visualized using various metrics.

## Workflow Set Racing
Racing optimization is performed on the workflow set to improve its overall performance.

## GitHub Repository Structure
The GitHub repository is structured with folders for data, scripts, and models. The main R script covers the entire analysis, and additional scripts or notebooks can be added for specific tasks.

Feel free to explore, modify, and contribute to this analysis!
