
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
