# Fuel-Efficiency-Prediction

Fuel-Efficiency-Prediction is a comprehensive machine learning project that predicts a car's fuel efficiency (city MPG) using multiple linear regression. The project covers data cleaning, exploratory analysis, feature engineering, model training, and evaluation, with techniques such as target encoding, one-hot encoding, feature scaling, Recursive Feature Elimination (RFE), and Principal Component Analysis (PCA).

## Table of Contents
- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Project Pipeline](#project-pipeline)
  - [Data Cleaning](#data-cleaning)
  - [Feature Engineering](#feature-engineering)
  - [Feature Scaling](#feature-scaling)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Feature Selection](#feature-selection)
  - [Handling Multicollinearity](#handling-multicollinearity)
  - [Model Training and Evaluation](#model-training-and-evaluation)
- [How to Run the Project](#how-to-run-the-project)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)
-  [Installation and Setup](#installation-and-setup)

## Project Overview
This project predicts a car's fuel efficiency based on various vehicle attributes. It demonstrates a full machine learning pipeline, including:
- **Data Cleaning**: Removing duplicates and outliers.
- **Feature Engineering**: Encoding categorical variables with target encoding and one-hot encoding.
- **Feature Scaling**: Normalizing numerical features using MinMaxScaler.
- **Feature Selection**: Identifying important predictors with RFE.
- **Multicollinearity Handling**: Reducing redundancy using PCA.
- **Model Training & Evaluation**: Building and evaluating a multiple linear regression model.

## Dataset
- **Size**: Initially 5076 records and 18 columns.
- **Features**:
  - *Numerical*: Vehicle dimensions, engine statistics, fuel efficiency (city and highway MPG), etc.
  - *Categorical*: Driveline, engine type, transmission, fuel type, make, and model year.
- After cleaning (duplicate and outlier removal), the dataset comprises 4794 records.

## Project Pipeline

### Data Cleaning
- **Duplicate Removal**: Check for and remove duplicate rows.
- **Outlier Removal**: Use the IQR (Interquartile Range) method to filter out extreme values in numerical columns.

### Feature Engineering
- **Target Encoding**: Encode categorical features like 'Identification.Make' and 'Identification.Model Year' based on the mean target value (Fuel Information.City mpg).
- **One-Hot Encoding**: Convert categorical variables such as 'Fuel Information.Fuel Type', 'Engine Information.Transmission', and 'Identification.Classification' into binary columns.

### Feature Scaling
- **Normalization**: Apply MinMaxScaler to all numerical features to standardize the range of data.

### Exploratory Data Analysis (EDA)
- **Correlation Heatmap**: Visualize the correlation matrix of features.
- **Scatter Plots**: Inspect relationships between key predictors and the target variable to confirm linearity.

### Feature Selection
- **Recursive Feature Elimination (RFE)**: Identify the top predictors using a Ridge estimator.
- **VIF Analysis**: Calculate Variance Inflation Factor (VIF) to detect multicollinearity among selected features.

### Handling Multicollinearity
- **Principal Component Analysis (PCA)**: For features with high VIF values, apply PCA to combine them into a single feature, reducing redundancy.

### Model Training and Evaluation
- **Data Splitting**: Partition the dataset into training and testing sets (80/20 split).
- **Model Building**: Train a multiple linear regression model using the selected features.
- **Evaluation**: Use the R² score and residual plots (histogram and scatter) to evaluate model performance and validate assumptions.
## How to Run the Project
- Open the Jupyter Notebook (`ML_Project.ipynb`) using your preferred environment (Jupyter Notebook, JupyterLab, or Google Colab).
- Execute the notebook cells sequentially to perform data cleaning, feature engineering, model training, and evaluation.
- Review the outputs and visualizations to understand the performance of the regression model.

## Results
- **Initial Model:** A regression model built on all features achieved an R² score of approximately 0.9783.
- **Final Model:** After feature selection and PCA, the refined model achieved an R² score of approximately 0.9732.
- **Residual Analysis:** Residual plots confirm that the errors are normally distributed around zero, supporting the linearity assumption.

## Future Work
- Experiment with alternative regression techniques (e.g., Ridge, Lasso) and ensemble methods.
- Enhance feature engineering with additional data transformation methods.
- Implement cross-validation for more robust model evaluation.

## Contributing
Contributions are welcome! Please fork the repository, make your changes, and submit a pull request. For major changes, open an issue first to discuss what you would like to change.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements
- Thanks to the open-source community for the excellent libraries and tools that made this project possible.
- Special thanks to the data providers and documentation that have helped in understanding and executing the project pipeline.


## Installation and Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/Fuel-Efficiency-Prediction.git
   cd Fuel-Efficiency-Prediction
