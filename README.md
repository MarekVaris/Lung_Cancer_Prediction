# Cancer Detection Project

## Overview

This project is focused on cancer detection using machine learning techniques. The code provides a framework for training and evaluating three different models: Logistic Regression, Support Vector Machine, and Neural Network.
The project uses data for training and testing, with the goal of predicting the presence or absence of cancer(Level 1 or 2).

## MainTrainingModel Class

The `MainTrainingModel` class is the core component of the project. It is designed to handle the training and evaluation of the machine learning models. Here's a brief overview of its functionality:

- **Initialization**: The class is initialized with a database, the name of the column to predict (`predicting_col_name`), and an optional transformation flag. It preprocesses the data, splits it into training and testing sets, and sets up a dictionary (`accuracy_compare`) to store evaluation metrics.

- **Train Model Method (`train_model`)**: This method takes a classifier as input, fits the model on the training data, makes predictions on the test data, and computes precision, recall, F1 score, and accuracy. The results are returned for further analysis.

- **Model-Specific Methods**: Three methods (`LogisticRegression`, `SupportVectorMachine`, and `NeutralNetwork`) train and evaluate specific machine learning models. The results are stored in the `accuracy_compare` dictionary.

- **ShowData Method**: This method generates a bar plot to visualize the precision, recall, F1 score, and accuracy of each model.

- **TrainAllDataModles Method**: This method orchestrates the training and evaluation of all three models.

- **ShowPredictionScore Method**: This method visualizes the true and predicted labels for two specified columns from the test data.

## Usage

To use this code, follow these steps:

1. Create an instance of the `MainTrainingModel` class, providing the required parameters.
2. Choose a model by calling the corresponding method (`LogisticRegression`, `SupportVectorMachine`, or `NeutralNetwork`).
3. Optionally, call the `ShowData` method to visualize the performance of the models.
4. Call the `ShowPredictionScore` method to visualize the true and predicted labels for specific columns.

Example:

```python
# Initialize the MainTrainingModel
model = MainTrainingModel(data_base, predicting_col_name)

# Train and evaluate the Logistic Regression model
model.LogisticRegression()

# Train and evaluate the Support Vector Machine model
model.SupportVectorMachine()

# Train and evaluate the Neural Network model
model.NeutralNetwork()

# Visualize model performance
model.ShowData()

# Visualize prediction scores for specified columns
model.ShowPredictionScore(predictions, col_name1, col_name2)
