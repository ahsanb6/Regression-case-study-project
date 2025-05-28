# Regression-case-study-project
1. Random Forest Regressor Tuning
 Apply hyperparameter tuning with grid search CV The Best parameters are:
Best Parameters: {'max_depth': None, 'min_samples_leaf': 4, 'min_samples_split': 10, 'n_estimators': 200}
Best RMSE (Cross-Validation): 0.06812784751137833
Best R² (Cross-Validation): 0.752270091865187
Test RMSE: 0.06863304614355753
Test R² Score: 0.8175878298969885


2. Decision Tree Regressor Optimization
 Tune Decesion tree with grid search the result are:
Best Parameters: {'max_depth': 5, 'max_features': 'sqrt', 'min_samples_leaf': 4, 'min_samples_split': 2}
Best RMSE (Cross-Validation): 0.07472958640985021
Best R² (Cross-Validation): 0.6992231901035337
Test RMSE: 0.07352634143667755
Test R² Score: 0.7906498993195812


3. Feature Selection-Based Modeling
 Top 5 Features:
       Feature  Importance
5         CGPA    0.748868
0    GRE Score    0.139570
1  TOEFL Score    0.035988
3          SOP    0.033350
4         LOR     0.016651


4. Handling Multicollinearity in Linear Regression
4.1 Correlation Matrix:
The correlation matrix shows strong correlations between several features:
GRE Score and TOEFL Score: 0.83 (high correlation, indicating potential multicollinearity).
GRE Score and CGPA: 0.83 (also high).
TOEFL Score and CGPA: 0.82.
University Rating and SOP: 0.74.
SOP and LOR: 0.73.
University Rating and CGPA: 0.75.
These correlations (above 0.7) suggest multicollinearity, which can inflate regression coefficient variances and make the linear regression model less reliable.

4.2 Initial VIF Scores:
The Variance Inflation Factor (VIF) scores confirm severe multicollinearity:
GRE Score: VIF = 1477.97 (extremely high).
CGPA: VIF = 1101.72 (extremely high).
TOEFL Score: VIF = 1297.29 (extremely high).
LOR: VIF = 38.07.
SOP: VIF = 36.59.
University Rating: VIF = 22.24.
Research: VIF = 2.77 (acceptable, as VIF < 5 indicates low multicollinearity).
VIF values above 5 (or 10) indicate problematic multicollinearity. The extremely high VIFs for GRE Score, CGPA, and TOEFL Score suggest these features are highly collinear with others.


Multicollinearity: The high VIFs and correlations confirm significant multicollinearity in the original dataset, particularly among GRE Score, TOEFL Score, and CGPA. This likely caused unstable regression coefficients in the original model, even though its performance was good (R² = 0.8212).
