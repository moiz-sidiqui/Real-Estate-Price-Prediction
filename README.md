# Real Estate Price Prediction

This Jupyter Notebook is designed to predict real estate prices in Bangalore, India. It uses a linear regression model to estimate prices based on various features such as location, square footage, number of bathrooms, and number of bedrooms (BHK).

## Table of Contents

- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Model Training](#model-training)
- [Model Evaluation](#model-evaluation)
- [Saving the Model](#saving-the-model)
- [Usage](#usage)
- [Dependencies](#dependencies)

## Dataset

The dataset used in this notebook contains information about real estate listings in Bangalore. The main features include:
- `total_sqft`: Total square footage of the property.
- `bath`: Number of bathrooms.
- `price`: Price of the property.
- `bhk`: Number of bedrooms.
- `location`: Location of the property in Bangalore.

## Data Preprocessing

Data preprocessing steps include:
- Removing duplicates and missing values.
- Converting categorical data (location) into numerical data using one-hot encoding.
- Feature scaling and selection.

## Model Training

A linear regression model is trained using the preprocessed dataset. The following steps are performed:
- Splitting the data into training and testing sets.
- Training the model on the training set.
- Evaluating the model on the testing set.

## Model Evaluation

The model's performance is evaluated using the R-squared metric. Predictions are compared to the actual prices to assess the model's accuracy.

## Saving the Model

The trained model is exported to a pickle file for future use. Additionally, the location and column information are saved to a JSON file to be used in the prediction application.

## Usage

To use the model for predicting real estate prices, load the pickle file and use the `predict_price` function provided in the notebook. Example usage:
```python
import pickle

# Load the model
with open('bangalore_home_prices_model.pickle', 'rb') as f:
    model = pickle.load(f)

# Predict price
predicted_price = model.predict([[location, total_sqft, bath, bhk]])
print(f"The predicted price is: {predicted_price}")
