# Spring Predictor ML Project

## Overview
This machine learning project aims to predict early spring occurrence before April 1st using historical weather and soil data. The model analyzes various environmental factors to make predictions that can enable data-driven business decisions for increased profits.

## Business Context

### Primary Objective
- Predict early spring occurrence before April 1st using weather and soil data
- Enable data-driven business decisions for increased profitability
- Replace traditional prediction methods with a more accurate, data-driven approach

### Technical Framework
- **Problem Type**: Supervised binary classification
- **Primary Metric**: Mean Absolute Error (MAE)
- **Minimum Required Accuracy**: >65% for profitability
- **Benchmark**: Must outperform random guessing (50%)

## Data Sources

The project uses several data files:
- `early_spring.csv`: Historical early spring occurrence data
- `phil_pred.csv`: Groundhog Day predictions
- `soil.csv`: Soil temperature and moisture data
- `weather.csv`: Daily weather measurements
- `ENSO.csv`: El Niño–Southern Oscillation data

## Features

### Key Variables
- Soil temperature and moisture measurements
- Weather data (temperature, precipitation, snowfall)
- ENSO (El Niño–Southern Oscillation) indicators
- Historical spring occurrence patterns

### Data Characteristics
- Time series data from 1947 to 2024
- 687 total features
- 78 yearly samples
- Mixture of continuous and categorical variables

## Data Analysis Findings

### Temperature-Moisture Relationships
- Soil temperature ranges from -10°C to +12°C
- Moisture levels typically between 0.44 and 0.51
- Weak correlation between temperature and moisture
- Most measurements cluster around 0°C with 0.47-0.49 moisture levels

### Notable Patterns
- Strong correlations within soil temperature measures
- Strong correlations within soil moisture measures
- Weak correlations between temperature and moisture
- Temperature spikes observed around 1950, 1990, and 2015

## Data Pipeline

### Preprocessing Steps
1. Drop samples before 1950
2. Remove empty columns
3. Handle missing values using MICE (Multivariate Imputation by Chained Equations)
4. Scale numerical features
5. Encode categorical variables

### Model Pipeline Components
```python
1. Data Cleaning
   - DropSamplesOverThresholdTransformer
   - DropColumnsEmptyColumnsTransformer

2. Feature Processing
   - Numerical: MICE Imputation + StandardScaler
   - Categorical: SimpleImputer + OneHotEncoder

3. Classification
   - Multiple models tested including:
     - Support Vector Classifier
     - Random Forest Classifier
     - Gradient Boosting Classifier
     - K-Neighbors Classifier
     - AdaBoost Classifier
     - Bagging Classifier
```

## Model Performance

The project implements several classification models to predict early spring occurrence. Performance metrics include:
- Precision
- Recall
- F1-score
- Classification accuracy

(Note: Specific performance metrics to be updated after final model selection and evaluation)

## Setup and Usage

### Prerequisites
- Python 3.x
- Required packages:
  - numpy
  - scipy
  - pandas
  - matplotlib
  - seaborn
  - scikit-learn

## Future Improvements

1. Feature Engineering
   - Create more sophisticated temporal features
   - Develop compound indicators from existing measurements

2. Model Enhancement
   - Implement ensemble methods
   - Explore deep learning approaches
   - Fine-tune hyperparameters

3. Data Collection
   - Gather additional historical data
   - Include more geographical locations
   - Add other relevant environmental indicators
