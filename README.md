# UCB-Project2
Used Car Price Analysis

Overview

This project analyzes used car listings to identify the key factors that influence vehicle prices. The dataset contains over 400,000 listings and includes features such as price, year, odometer, manufacturer, model, condition, cylinder, and vehicle type.

Objective

Identify the factors that make a car more or less expensive and build a model to predict used car prices.

Data Cleaning

1. ID, VIN, Paint_Color, Region and size columns were dropped due to high missing values or low relevance.
2. Invalid and unrealistic vehicle listings were filtered from the dataset:
 a) Vehicles with prices below $1,000 or above $100,000 were removed to reduce the impact of extreme outliers and focus the analysis on typical used car inventory.
 b) Vehicles with unrealistic mileage values were removed by limiting odometer readings to greater than 0 and less than or equal to 250,000 miles.
 c) Vehicles manufactured before 2000 or after 2026 were removed.
 d) Salvage-condition vehicles were removed to reduce noise and improve model consistency.
 e) Listings with title_status values of "salvage", "missing", or "parts only" were removed.

Remaining missing values were handled within the machine learning preprocessing pipeline using imputation techniques.

Key Findings

Used car prices are strongly influenced by:

Vehicle age
Odometer mileage
Vehicle condition
Manufacturer and model
Vehicle type and drivetrain

Newer vehicles with lower mileage generally command higher prices. Luxury brands and specialty vehicle types such as trucks, SUVs, and convertibles were associated with higher predicted prices. Four-wheel drive vehicles and vehicles with higher cylinder counts were also linked to higher prices.

Feature importance analysis from the Ridge Regression model showed that manufacturers such as Ferrari, Tesla, Porsche, Toyota, GMC, and Ram had strong positive relationships with vehicle price. Older vehicles, higher mileage, and lower condition ratings were associated with lower prices.


Models Evaluated

Four regression models were developed and compared:

Linear Regression — baseline model
Ridge Regression — regularized regression to reduce overfitting
Polynomial Ridge Regression — Ridge Regression with polynomial numeric features
Lasso Regression — regularization with automatic feature selection

 Model                        RMSE (Log Scale)        R² 
 ---------------------------  ------------------  ------------
 Linear Regression                  0.400878        0.755989 
 Ridge Regression                   0.401488        0.755246 
 Polynomial Ridge Regression        0.400916        0.755943 
 Lasso Regression                   0.811542        0 

Linear Regression achieved the best overall performance, although the difference between Linear Regression, Ridge Regression, and Polynomial Ridge Regression was extremely small.

The final models explained approximately 76% of the variation in used car prices, indicating strong predictive performance for a real-world marketplace dataset.

The RMSE results correspond to predictions generally being within about 1.5 times the actual vehicle price.

Lasso Regression performed substantially worse because removing coefficients eliminated features that still contained useful predictive information.

Insights

Data cleaning and feature engineering contributed more to model improvement than increasing model complexity.
Removing unrealistic listings and salvage vehicles significantly improved model performance.
Vehicle age and mileage remain the strongest pricing factors.
Brand reputation and vehicle type strongly influence resale value.
Luxury and specialty vehicles command higher prices in the used car market.
Simpler linear models performed nearly as well as more complex regularized models after data cleaning and preprocessing improvements.

Business Recommendations

Focus inventory on newer, lower-mileage vehicles to maximize resale value.
Prioritize high-demand brands and vehicle types such as SUVs and trucks.
Avoid or carefully price salvage and high-mileage vehicles.
Use data-driven pricing models as a pricing support tool rather than an exact pricing rule.
Additional data such as accident history, trim level, maintenance history, and number of owners could further improve pricing accuracy.

Tools

Python, Pandas, NumPy, Scikit-learn, Seaborn and Matplotlib were used for data analysis and modeling.

Conclusion

Used car prices are influenced by a combination of vehicle age, mileage, condition, manufacturer, vehicle type, and market demand. After extensive data cleaning and feature engineering, the regression models achieved strong predictive performance, explaining approximately 76% of price variation in the dataset.

The project demonstrates that improving data quality and feature engineering can have a larger impact on model performance than increasing model complexity. While the models cannot predict exact prices, they provide valuable insight into pricing trends and support better inventory and pricing decisions.

Author

Colleen Yap
