
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
