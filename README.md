# DVD Rental Duration Prediction

This project predicts how many days a customer will rent a DVD using historical rental data and regression models.  
The model helps the company improve inventory planning by estimating rental durations with a target Mean Squared Error (MSE) of **3 or less** on the test set.

## Dataset
The dataset `rental_info.csv` contains the following features:

- `rental_date`: Date and time the DVD was rented.
- `return_date`: Date and time the DVD was returned.
- `amount`: Amount paid for the rental.
- `amount_2`: Square of `amount`.
- `rental_rate`: Rental rate of the DVD.
- `rental_rate_2`: Square of `rental_rate`.
- `release_year`: Year the movie was released.
- `length`: Length of the movie in minutes.
- `length_2`: Square of `length`.
- `replacement_cost`: Cost to replace the DVD.
- `special_features`: Special features (e.g., Deleted Scenes, Behind the Scenes).
- `NC-17`, `PG`, `PG-13`, `R`: Dummy variables for movie ratings (reference category dropped).

The target variable is:
- `rental_length_days`: Number of days the DVD was rented.

## Steps Implemented

1. **Data Preprocessing**
   - Converted rental and return dates to datetime format.
   - Calculated rental duration in days.
   - Created dummy variables for `special_features`.
   - Dropped unused original columns.

2. **Feature Selection**
   - Used Lasso Regression to identify important predictors.

3. **Modeling**
   - **Linear Regression** (with selected features from Lasso)
   - **Decision Tree Regressor** (all features)
   - **Random Forest Regressor** (hyperparameter tuning using `RandomizedSearchCV`)

4. **Model Evaluation**
   - Evaluated models using Mean Squared Error (MSE).
   - Selected the model with the lowest MSE.

## Libraries Used
- pandas
- numpy
- scikit-learn

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/dvd-rental-duration-prediction.git
