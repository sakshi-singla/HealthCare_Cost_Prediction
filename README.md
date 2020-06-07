
# Health Care cost prediction with Linear Regression

Group members: Sakshi Singla, Ivette Sulca

#### Description of your dataset:
The linear regression analysis presented on this report will work with a dataset related to Medical health care cost 
provided in the book of Machine Learning with R by Lantz. 
The dataset can be found at https://www.kaggle.com/ruslankl/ health-care-cost-prediction-w-linear-regression/comments.


### Summary:
- We started with a dataset containing 1338 observations of health insured person with predictor variables explaining the profile of each person and the total amount they paid for the health insurance coverage.
- Amount paid was predicted by age, sex, body mass index, number of children, smoker status and region as predictor variables.
- Upon explanatory analysis, we concluded that sex and region is not having much impact on amount paid. Therefore, removed those variables from our analysis.
- Then, we did model selection using AIC, BIC, Mallow Cp and Adj R2 criteria and concluded with 2 models:<br/>
Candidate 1: charges ~ age+bmi+children+is_smoke ->Full model<br/>
Candidate 2: charges ~ age+bmi+is_smoker ->Reduced model<br/>
- Then we performed F-test to conclude that reduced model is better.
- Now, we started with model diagnostics for both full and reduced models and found that results were quite similar for both models.<br/>
Here were outliers and leverage points, and removing those improved normality and heteroskedasticity of the model. Therefore removed those points, and used weighted least squares for correction for heteroskedasticity. Also, there was not major auto- correction and multicollinearity in both models.
- Finally selected the reduced Model:<br/>
**y= -8150.40 + 260.84 * age + 173.23 * bmi + 25693.62 * is_smoker**<br/>
Therefore cost of health insurance is depending on age, bmi and whether a person is a smoker or not.
