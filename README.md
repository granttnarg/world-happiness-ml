# World Happiness Data Analysis - Learning Project

## Overview

This project explores the World Happiness Report dataset to understand global happiness patterns and serves as a learning experiment in data science methodology and critical data analysis.

## Dataset

The World Happiness Report dataset contains happiness scores and rankings for countries worldwide, along with various factors that contribute to happiness calculations including:

- Economy (GDP per Capita)
- Family/Social Support
- Health (Life Expectancy)
- Freedom
- Trust (Government Corruption)
- Generosity
- Dystopia Residual

## Project Structure

### Planned Analysis Steps

- Data Collection & Investigation
- Data Cleaning pt 1 (only dealing with zero values)
- Train/Test split - Separate our Xtrain Xtest and Ytrain Ytest
- Data Visualization (look for patterns and further cleaning, outliers, fillin data possibilities)
- Data Cleaning pt 2 (filling in data values or adjusting outliers)
- Data Visualization (final check are we happy with our clean data)
- Exploratory Analysis (Correlations, trying to decide on features)
- Feature engineering - decide on best features and/or make new features if needed
- Model building
  - Set a baseline with linear regression
- Cross validate
- Iterate on Model - try some different models or adjust features to see if we can get a better outcome
- Pipeline - After our first setup we can then refactor some of our cleaning and feature engineering logic into a pipeline

## Key Learning: Data Leakage Discovery

### Initial Approach

- Attempted to predict Happiness Score using economic, social, and political factors
- Achieved suspiciously high score (0.99) with minimal error

### Investigation and Discovery

- Upon closer examination of the data documentation, discovered that all predictor variables were "contributions to the calculation of the Happiness Score"
- This created severe data leakage - essentially trying to predict a sum using its components
- The Dystopia Residual was particularly problematic as it represents the unexplained variance in the happiness calculation

### Conclusion

This dataset is designed for **explanatory analysis** (understanding what factors contribute to happiness differences) rather than **predictive modeling**.

**Key Takeaway:** Always investigate data sources and variable definitions before modeling. High performance metrics can indicate data leakage rather than model success.

## Learning Outcomes

- Understanding the difference between explanatory and predictive analysis
- Identifying data leakage in real-world datasets
- Importance of domain knowledge in data science
- Critical evaluation of model performance metrics

## Check Requirements.txt for needed libraries. Running on Python 3.13.x

- Python
- Pandas
- NumPy
- Matplotlib/Seaborn
- Scikit-learn

## Note

This project serves as a learning experiment demonstrating the importance of understanding your data before applying machine learning models. The "failed" prediction attempt provided valuable insights into data quality and appropriate use cases for different types of datasets.
