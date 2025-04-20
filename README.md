# Used-Car-Price-Prediction
Used Car Price Prediction with Feature Engineering and Regression Models




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


✅ imagesprice-distribution.png


---

## Contact

GitHub: [github.com/MandyAC007(Min Zhang_AC@IC )
Email: mandy30811@gmail.com  
LinkedIn: https://www.linkedin.com/in/min-zhang-24763223/



# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation

- For what purpose was the dataset created? 
- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?

 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 
- How many instances of each type are there? 
- Is there any missing data?
- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?

## Collection process

- How was the data acquired? 
- If the data is a sample of a larger subset, what was the sampling strategy? 
- Over what time frame was the data collected?

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 
- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
 
## Uses

- What other tasks could the dataset be used for? 
- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 
- Are there tasks for which the dataset should not be used? If so, please provide a description.

## Distribution

- How has the dataset already been distributed? 
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  

## Maintenance

- Who maintains the dataset?







# 📄 Datasheet for Used Car Price Prediction Dataset

## Motivation

- **Purpose**: This dataset was curated and enhanced for a machine learning project aimed at predicting the selling price of used cars based on features like mileage, brand, car age, and accident history. The goal was to explore price patterns and build predictive models to assist buyers or dealers in estimating fair prices.

- **Created by**: The dataset was originally collected from a third-party source (assumed to be an online car marketplace or open dataset). Feature engineering and preprocessing were conducted independently for educational and portfolio purposes.

---

## Composition

- **Instance representation**: Each row in the dataset represents a used car listing, including details like brand, model year, mileage, fuel type, accident history, and final listed price.

- **Total instances**: 4,009 car listings after cleaning. The version used in this project includes **2,095 entries**.

- **Missing data**: Yes, there are some missing entries, particularly in columns such as `fuel_type`, `accident`, and `clean_title`. These were either filled with default values or marked as missing during preprocessing.

- **Confidential data**: No. The dataset does not include personal identifiers, private communications, or legally protected information. All data points are general vehicle attributes.

---

## Collection Process

- **Acquisition**: The dataset appears to have been scraped or downloaded from a public website or data-sharing platform containing used vehicle listings.

- **Sampling strategy**: Unknown, but the dataset likely represents a convenience sample of available listings over a fixed period.

- **Collection time frame**: Not explicitly provided, but listings seem to span vehicles from approximately 2013–2022 based on the `model_year`.

---

## Preprocessing/Cleaning/Labelling

- **Preprocessing**:
  - Converted price and mileage from string formats (e.g., "$10,300", "51,000 mi.") into clean numeric values.
  - Created new features:
    - `car_age` = 2025 - model_year
    - `price_per_km` = price / milage
  - Standardized categorical columns (e.g., brand, transmission).
  - Handled missing values by filling or flagging where appropriate.
  - Removed duplicate entries and rows with unusable data.

- **Raw data**: The raw data was preserved separately before cleaning as `used_cars.csv`.

---

## Uses

- **Other tasks**: In addition to price prediction, the dataset could be used for:
  - Vehicle depreciation analysis
  - Feature importance exploration (e.g., impact of accidents)
  - Classification of vehicles into price tiers
  - Exploratory brand/value benchmarking

- **Bias or risk considerations**:
  - Dataset may reflect biases from the source (e.g., overrepresentation of certain brands or regions).
  - Prices may not generalize to all geographies or time periods.
  - Missing or misreported accident data could skew insights.
  - Consumers should avoid using this dataset for high-stakes decisions like insurance pricing without further verification and ethical review.

- **Tasks to avoid**:
  - Inferring personal or demographic data
  - Legal or financial decisions without additional context or validation

---

## Distribution

- **Distribution**: Not distributed commercially. Used solely for learning and demonstration purposes.

- **Licensing**: Intended for academic and personal use. No explicit IP or copyright information is provided for the original data source.

---

## Maintenance

- **Maintainer**: The dataset is maintained as part of the author's GitHub repository for the Used Car Price Prediction project. Future updates may occur in the form of model improvements or feature expansion but the dataset itself is static.



# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** Describe the inputs of your model 

**Output:** Describe the output(s) of your model

**Model Architecture:** Describe the model architecture you’ve used

## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

## Limitations

Outline the limitations of your model.

## Trade-offs

Outline any trade-offs of your model, such as any circumstances where the model exhibits performance issues. 





📊 Model Card: Used Car Price Prediction
🧠 Model Description
Input:
The model takes in tabular features for each used car listing, including:

milage (numeric)

car_age (numeric)

brand (categorical)

fuel_type (categorical)

transmission, accident, clean_title, etc.

All categorical variables were encoded appropriately (e.g., one-hot or label encoding), and numeric features were either scaled or left as-is depending on the model.

Output:
The model outputs a predicted price for a used car (continuous value in currency units, e.g., USD).

Model Architecture:
Three regression models were explored:

Linear Regression (baseline)

Decision Tree Regressor

✅ Random Forest Regressor – Selected final model

The Random Forest Regressor was selected due to its strong generalization and ability to capture non-linear relationships without heavy preprocessing.

📈 Performance
Evaluation Metrics:

R² Score (Coefficient of Determination)

Root Mean Squared Error (RMSE)


Model	R² Score	RMSE (USD)
Linear Regression	0.75	~5,500
Decision Tree	0.84	~3,900
Random Forest ✅	0.89	~3,200
Test Set: The dataset used for evaluation includes 30% of the cleaned and feature-engineered entries (2,095 total), randomly split using train_test_split.

⚠️ Limitations
The model does not consider real-time market trends or regional price differences.

Pricing may be biased based on missing or misreported data (e.g., underreported accidents).

Model performance may drop significantly for rare or luxury brands due to underrepresentation.

⚖️ Trade-offs
Interpretability vs. Performance: Random Forest offers high accuracy but is less interpretable than Linear Regression.

Overfitting risk: Decision Trees and Forests may slightly overfit the training data if not tuned properly (e.g., max depth).

Missing value handling: Imputation strategies may introduce noise, especially in categorical fields like fuel_type.








#  Model Card: Used Car Price Prediction

## Model Description

**Input:**  

The model takes in tabular features for each used car listing, including:
- `milage` (numeric)
- `car_age` (numeric)
- `brand` (categorical)
- `fuel_type` (categorical)
- `transmission`, `accident`, `clean_title`, etc.

All categorical variables were encoded appropriately (e.g., one-hot or label encoding), and numeric features were either scaled or left as-is depending on the model.

---

**Output:**  
The model outputs a **predicted price** for a used car (continuous value in currency units, e.g., USD).

---

**Model Architecture:**  

Three regression models were explored:
- **Linear Regression** (baseline)
- **Decision Tree Regressor**
- ✅ **Random Forest Regressor** – Selected final model

The Random Forest Regressor was selected due to its strong generalization and ability to capture non-linear relationships without heavy preprocessing.

---

## 📈 Performance

**Evaluation Metrics:**
- **R² Score** (Coefficient of Determination)
- **Root Mean Squared Error (RMSE)**

| Model                | R² Score | RMSE (USD) |
|---------------------|----------|------------|
| Linear Regression    | 0.75     | ~5,500     |
| Decision Tree        | 0.84     | ~3,900     |
| **Random Forest** ✅ | **0.89** | **~3,200** |

**Test Set:** The dataset used for evaluation includes 30% of the cleaned and feature-engineered entries (2,095 total), randomly split using `train_test_split`.

---

## Limitations

- The model does not consider real-time market trends or regional price differences.
- Pricing may be biased based on missing or misreported data (e.g., underreported accidents).
- Model performance may drop significantly for rare or luxury brands due to underrepresentation.

---

## Trade-offs

- **Interpretability vs. Performance**: Random Forest offers high accuracy but is less interpretable than Linear Regression.
- **Overfitting risk**: Decision Trees and Forests may slightly overfit the training data if not tuned properly (e.g., max depth).
- **Missing value handling**: Imputation strategies may introduce noise, especially in categorical fields like `fuel_type`.



