# LJMU_Masters_Bike_Rental_Assignment

#######################
### Problem Statement
#######################

BoomBikes, a US bike-sharing provider, has seen a significant drop in revenue due to the Corona pandemic.  They're looking to create a business plan to boost revenue post-pandemic and have hired a consulting company to help.  The goal is to understand the factors influencing the demand for shared bikes in the American market.S
Specifically, BoomBikes wants to know:

* Which variables are significant in predicting the demand for shared bikes.
* How well those variables describe the bike demands

To achieve this, they've collected a large dataset on daily bike demand based on various factors, including meteorological information and user behavior.

###################
### Business Goal
###################

We are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market. 


#################
### Contents
#################

* **1. Data Exploration** <br><br>
    * 1.1 Data Dictionary
    * 1.2 Importing Libraries
    * 1.3 Understanding Data <br><br>

* **2. Exploratory Data Analysis (EDA)** <br><br>
    * 2.1 Dropping Uninformative Features
    * 2.2 Outlier Detection and Removal
    * 2.3 Add actual category names to categorical values
    * 2.4 Univariate Data Analysis
    * 2.5 Bivariate Data Analysis
    * 2.6 Pair Plot Generation
    * 2.7 Correlation Analysis <br><br>

* **3. Feature Engineering (Creating Dummy Variables for Categorical Predictors)** <br><br>

* **4. Train, Test Split** <br><br>

* **5. Feature Scaling** <br><br>

* **6. Model Building** <br><br>
    * 6.1 Split `df_train` into `X_train` and `y_train`
    * 6.2 Dimensionality Reduction: Recursive Feature Elimination (RFE)
    * 6.3 Building Model 1
    * 6.4 Building Model 2
    * 6.5 Building Model 3
    * 6.6 Building Model 4
    * 6.7 Building Model 5 <br><br>

* **7. Model Evaluation (Training Data)** <br><br>
    * 7.1 Residual Analysis on Training data
        * * Distribution of Error Terms Plot
        * * Component Plus Residual Plot (CCPR) for "temp"
        * * Validating Homoscedasticity
        * * Actual vs. Predicted Values (Training Data)
    * 7.2 Validating Multicollinearity <br><br>

* **8. Model Evaluation (Test Data)** <br><br>
    * 8.1 Actual vs Predicted (y_test vs y_pred)
    * 8.2 R-squared and Adjusted R-squared (test data) <br><br>

* **9. Conclusion**

<br>



######################
### Conclusion
######################

<br>

* **Objective:** The primary goal of this case study was to build a robust linear regression model for predicting bike rental counts using a set of environmental and temporal features.


* **Model Development and Selection:** A stepwise model building process, potentially involving feature engineering and selection, was employed to arrive at the final model (lm5). This process likely involved evaluating different combinations of predictor variables and selecting the model that provided the best balance of predictive accuracy and interpretability.  The final model included the following variables: 
    * `temp`
    * `windspeed`
    * `workingday_Yes`
    * `season_Winter`
    * `yr_2019`
    * `mnth_Nov`
    * `weekday_Mon`
    * `season_Summer`
    * `weathersit_Fair`
    * `mnth_Dec`
    * `mnth_Sep`
    * `weathersit_Bad`.

<br>

* **Model Performance (Training Data):**
    * **R-squared:** 0.827. This indicates that the model explains 82.7% of the variability in bike rental counts within the training dataset.
    * **Adjusted R-squared:** 0.822. This metric, which penalizes the inclusion of unnecessary variables, confirms the model's strong performance on the training data.

<br>

* **Model Performance (Test Data):**
    * **R-squared:** 0.8145. The model maintains a high explanatory power on the unseen test data, demonstrating its ability to generalize beyond the training set.
    * **Adjusted R-squared:** 0.8025.  The adjusted R-squared on the test data further validates the model's generalizability and indicates a good fit.

<br>

* **Key Predictors:**  The following variables were identified as statistically significant predictors:
    * `temp`: Temperature, despite a slightly elevated VIF (5.18), was retained due to its established influence on bike rentals.
    * `windspeed`: Windspeed also played a significant role in predicting rentals.
    * Temporal Factors:  Several time-related variables were significant:
        * `workingday_Yes`: Working days had a different impact on rentals compared to non-working days.
        * `yr_2019`:  The year 2019 had a statistically significant effect, likely reflecting trends or changes specific to that year.
        * Month and Season: Several months and seasons showed significant effects:  `mnth_Nov`, `weekday_Mon`, `season_Summer`, `mnth_Dec`, and `mnth_Sep`. These indicate seasonal variations in bike rental patterns.
    * Weather Conditions: Weather played a crucial role, with both fair (`weathersit_Fair`) and bad weather (`weathersit_Bad`) having significant impacts on rental counts.

<br>

* **Multicollinearity:** While `temp` exhibited a slightly elevated VIF, it was retained due to its importance and the potential for omitted variable bias if removed.


* **Model Diagnostics and Assumptions:**
    * **Normality of Residuals:**  Potential deviations from normality suggest areas for further investigation.
    * **Other Assumptions:**  Standard linear regression assumptions (linearity, homoscedasticity, independence of errors) should be thoroughly checked.

<br>

* **Conclusion and Future Directions:**
    * The linear regression model effectively predicts bike rentals with good accuracy and generalizability.
    * Future work could explore adding more granular temporal features (e.g., holidays), investigate residual diagnostics, and consider time series models to capture temporal dependencies.  The model's insights can inform operational and strategic decision-making for bike-sharing programs.

<br>

           
##################################################################
###  Author                 :  Saurabh Tayde
###  Email                  :  saurabhtayde2810@gmail.com
##################################################################
