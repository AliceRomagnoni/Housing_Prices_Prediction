# Housing_Prices_Prediction
### Overview:
This project implements an end-to-end machine learning workflow to predict housing prices based on features such as location, income, and proximity to the ocean.
It uses the California Housing Dataset from the book Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow (Aurélien Géron).

### Steps:
1. Data Fetching:
   The dataset is automatically downloaded and extracted using 2 functions:
   - fetch_housing_data() : downloads and extracts the dataset.
   - load_housing_data() : loads the data into a pandas DataFrame.
     
2. Data Exploration:
   After dividing the initial dataset in a training dataset and test dataset that will be used only at the end with the selected model, I proceeded to explore the data of the training set. Using functions (like .info() , .describe() , .hist() and matplotlib) we can better understand the data and the correlations between the label attribute (median_house_value) and the other attributes.

 3. Data Preparation:
    - Categorical encoding (for ocean_proximity).
    - Combined pipelines for preprocessing numeric and categorical attributes. This with creation of custom attributes as combinations of the initial attributes to better the correlation with the label

 4. Model Training:
    Multiple regression models are trained and compared:
    - LinearRegression()
    - DecisionTreeRegressor()
    - RandomForestRegressor()
      
 5. Model Evaluation:
    - RMSE, R² used to measure performance.
    - Cross-validation provides average metrics across folds.
    - Feature importance extracted for interpretability.
   
 6. Fine-Tuning:
    - Grid Search (GridSearchCV) used for hyperparameter tuning of Random Forest.
    - Best model parameters and performance recorded.
   
 7. Final Testing:
    - Final evaluation performed on test set.
    - 95% confidence interval computed for error estimation.
   
  ### Results:
  | Model | RMSE | R² Score |
|--------|------|----------|
| Linear Regression | 70,000 | 0.62 |
| Decision Tree | 0 (Overfit) | 1.00 |
| Random Forest | 50,000 | 0.82 |

- Random Forest achieved the lowest RMSE and best generalization.
- Income and location strongly influence price predictions.
- Proper feature scaling and encoding are crucial for regression accuracy.
