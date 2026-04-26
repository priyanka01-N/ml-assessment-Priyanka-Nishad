Part B: Business Case Analysis

## B1. Problem Formulation

### (a)

The problem can be formulated as a supervised machine learning regression problem. The target variable is items_sold. The input features include store_id, store_size, location_type, promotion_type, is_weekend, is_festival, competition_density, and date-related features. The goal is to predict the number of items sold based on these features.

### (b)

Using items_sold is more reliable than total revenue because revenue can be influenced by price variations, discounts, and inflation. Items sold directly reflect demand. This highlights the importance of selecting a target variable that closely aligns with the business objective.

### (c)

Instead of using a single global model, a better approach would be to use segmented models based on store location or type. This allows the model to capture different customer behaviors across locations.

---

## B2. Data and EDA Strategy

### (a)

The data from multiple tables can be merged using keys such as store_id and transaction_date. The final dataset should be at the store-date level, with one row representing sales for a store on a given date. Aggregations such as total items sold per day and average competition density can be performed.

### (b)

EDA would include:

- Distribution of items sold
- Sales trends over time
- Comparison of promotions
- Correlation analysis between features

These insights help in feature engineering and model selection.

### (c)

If 80% of transactions have no promotion, the dataset is imbalanced. This may bias the model. To handle this, techniques such as resampling or weighting can be used.

---

## B3. Model Evaluation and Deployment

### (a)

A time-based train-test split should be used instead of random splitting to preserve temporal patterns. Metrics like RMSE and MAE should be used to evaluate performance.

### (b)

Feature importance can help explain why different promotions work differently across stores and time periods. It helps identify which factors influence sales the most.

### (c)

The model can be deployed as a pipeline that takes new data each month, preprocesses it, and generates predictions. Monitoring should include checking model performance over time and retraining when performance drops.
