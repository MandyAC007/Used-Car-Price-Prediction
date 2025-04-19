
# Used Car Price Prediction

## Non-Technical Explanation of Your Project

This project aims to predict the selling price of a used car based on its features such as mileage, age, fuel type, and accident history. By using historical data and machine learning techniques, we can estimate a fair market value for different vehicles. This type of model can help buyers, sellers, and dealerships make informed decisions and identify over- or underpriced listings.

---

## Data

The dataset was collected from online used car listings and contains 4,009 entries after cleaning, of which 2,095 were used in this project. Each row represents a vehicle and includes attributes like brand, model year, mileage, transmission type, accident history, and final listed price. Additional features like `car_age` and `price_per_km` were created during preprocessing.

Original source assumed to be from a public online marketplace or open dataset (exact origin unknown). Dataset is only used for educational purposes.

---

## Model

We experimented with several regression models, including Linear Regression and Decision Trees. Ultimately, we chose the **Random Forest Regressor** due to its strong performance and ability to handle non-linear patterns in the data. It also provides good feature importance insights and performs well with minimal tuning.

---

## Hyperparameter Optimisation

We tuned hyperparameters of the Random Forest model using grid search, including:
- `n_estimators` (number of trees)
- `max_depth` (tree depth)
- `min_samples_split`
- `min_samples_leaf`

The optimal combination was selected using cross-validation and evaluated on the validation/test set for generalizability.

---

## Results

The Random Forest model achieved an R² score of **0.89** and an RMSE of approximately **$3,200** on the test set. This suggests that the model can predict car prices with high accuracy in most cases. Important predictors included mileage, car age, fuel type, and accident status.

What we learn:
- Older cars and higher mileage tend to lower the price.
- Clean titles and no accident history increase value.
- Model works best within the data's distribution and may need retraining over time.


![Price Distribution](images/price-distribution.png)



---

## Contact

GitHub: [github.com/MandyAC007(Min Zhang_AC@IC )
Email: mandy30811@gmail.com  
LinkedIn: https://www.linkedin.com/in/min-zhang-24763223/



