# UCB-Project2
Used Car Price Analysis

Overview

This project analyzes used car listings to identify the key factors that influence vehicle prices. The dataset contains over 400,000 listings and includes features such as price, year, odometer, manufacturer, model, condition, cylinder, and vehicle type.

Objective

Identify the factors that make a car more or less expensive and build a model to predict used car prices.

Data Cleaning

1. VIN and size columns were dropped due to high missing values or low relevance.
2. Invalid values
   a) price ≤ 0 and > 100,000, unrealistic mileage/year were removed. Vehicles with prices above $100,000 were removed to reduce the influence of extreme outliers and focus the analysis on typical used car inventory.
   b) Salvage-condition vehicles were removed to reduce noise.
   c) Year before 2000 and after 2026 were removed.
   d) Odometer > 300,000 removed.
   e) Missing values were filled within the modeling pipeline.

Key Findings

Vehicle price is strongly influenced by age, mileage, condition, brand, and vehicle type.
Newer vehicles and those with lower mileage consistently command higher prices.
Better condition vehicles have higher resale value.
Luxury brands and high-demand manufacturers significantly increase price.
SUVs, trucks, and specialty vehicles tend to have higher prices than smaller cars.

Some highly specific model categories introduced noise, so broader patterns such as brand and vehicle type are more useful for decision-making.

Modeling Results

Linear Regression, Ridge, and Lasso models were evaluated using cross-validation.

Ridge Regression performed best with the lowest RMSE. Predictions are within approximately two times the actual price, meaning the model captures general trends but not exact values. Ridge Regression results were very close to Linear Regression results. Lasso performed worse due to eliminating useful features.

Insights

Price is not driven by a single factor but by a combination of vehicle characteristics and market demand.
Brand reputation and vehicle type play a major role in pricing.
Removing noisy or extreme cases (e.g., salvage vehicles) improves model performance.
Adding factors like accident history, number of owners can potentially improve model analysis.

Business Recommendations

Focus on newer, low-mileage vehicles to maximize resale value.
Prioritize high-demand brands and models.
Stock more SUVs and trucks due to higher resale potential.
Avoid or carefully price salvage and high-mileage vehicles.
Use data-driven pricing as a guideline rather than an exact rule.

Tools

Python, Pandas, NumPy, Scikit-learn, Seaborn and Matplotlib were used for data analysis and modeling.

Conclusion

Used car prices are influenced by multiple factors, including age, mileage, condition, brand, and vehicle type. While the model cannot predict exact prices, it provides strong insights into pricing trends and supports better inventory and pricing decisions.

Author

Colleen Yap
