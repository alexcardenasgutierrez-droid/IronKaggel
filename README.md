# Machine Learning Price Prediction On King County House Sales

**Project Description:** A comprehensive machine learning project using multiple regression algorithms and feature engineering to predict house sale prices in King County, Washington.

## Dataset Description
This dataset encompasses house sale prices for King County (including Seattle) spanning a one-year period from May 2014 to May 2015. 
* **Dimensions:** Contains 21 distinct columns.
* **Target Variable:** `price` (House sale price).
* **Property Features:** `bedrooms`, `bathrooms`, `sqft_living`, `sqft_lot`, `floors`, `sqft_above`, `sqft_basement`.
* **Quality Indicators:** `condition` (scale 1-5), `grade` (scale 1-11), `waterfront`, `view`.
* **Temporal Features:** `date`, `yr_built`, `yr_renovated`.
* **Location & Neighborhood:** `zipcode`, `lat`, `long`, `sqft_living15`, `sqft_lot15` (metrics of nearest 15 neighbors in 2015).

## Research Goal
The primary goal was to build a robust machine learning model to accurately predict house prices using regression algorithms. Secondary objectives included understanding which features most significantly impact house prices, exploring properties valued at $650K and above, and testing the effectiveness of various feature engineering and outlier flagging techniques.

## Steps Taken
1. **Baseline Models:** Established initial performance metrics using basic algorithms.
2. **Feature Importance Analysis:** Evaluated which variables carried the most predictive weight.
3. **Outliers Analysis:** Identified data anomalies and tested different outlier handling strategies.
4. **Feature Selection:** Filtered the dataset to retain only the most impactful variables.
5. **Feature Engineering:** Created new features (e.g., temporal features) to capture underlying trends.
6. **Model Optimization:** Tuned hyperparameters and compared test set results across different dataset versions to find the optimal balance.

## Main Findings


This project successfully improved house price prediction accuracy by ~30% compared to the initial baseline model.

* **Best Model:** Gradient Boosting Regressor (using the v1 Dataset: Cleaned + Outlier Flags).
* **Final Performance:** R² 0.942 | MAPE 11.7% | RMSE $86,770
* **Model Progression:**

| Model Stage | Key Technique | Test R² | Test RMSE |
| :--- | :--- | :--- | :--- |
| 1. Baseline | Linear Regression (Raw Data) | 0.716 | $191,531 |
| 2. Intermediate | Random Forest (Default) | 0.896 | $115,994 |
| 3. Optimized | Gradient Boosting (Tuned) | **0.942** | **$86,770** |

**Critical Insight:** Feature engineering (such as dropping specific columns or creating new temporal features) provided diminishing returns. The simplest, most robust dataset (v1: Cleaned data with Outlier Flags) paired with a powerful Gradient Boosting model yielded the best generalization. This proves that algorithm selection and hyperparameter tuning were the primary drivers of performance in this specific pipeline.



## How to Reproduce the Project
* **Prerequisites:** Python 3 and core data science libraries (`pandas`, `numpy`, `scikit-learn`, `matplotlib`, `seaborn`).
* Clone this repository and ensure the raw data is located in the `Data` folder.
* **Execution:** Run the Jupyter notebooks located in the `Notebooks` folder. *Important: Each notebook builds upon the previous one and must be executed in sequential order (1 → 6).*
* **Reproducibility:** The project uses a consistent random state (`seed=13`) across all splits and models to ensure identical results.

## Next Steps / Ideas for Improvement
* **Model Deployment:** Build an interactive web application using Streamlit or Flask where users can input house features (square footage, zip code, etc.) and receive a real-time price prediction.
* **Incorporate External Data:** Merge the existing dataset with external APIs to include local school district ratings, crime statistics, or interest/mortgage rates from 2014-2015 to see if macroeconomic or neighborhood factors improve accuracy.
* **Advanced Ensembling:** Experiment with XGBoost or LightGBM to see if computation time can be reduced while maintaining or exceeding the Gradient Boosting Regressor's accuracy.

## Repo Structure
| Folder/File | Description |
| :--- | :--- |
| **`Data/`** | Contains the raw and processed versions of the King County dataset. |
| **`Graphs/`** | Stores exported visualizations from the exploratory data analysis and model evaluation phases. |
| **`Metrics/`** | Contains exported performance metrics and model comparison tables. |
| **`Notebooks/`** | Holds the core analysis files, numbered 1 through 6, covering everything from baseline modeling to final optimization. |
| **`Presentation`** | A PowerPoint with the presentation of th project |
## Authors
Built by me (@alexcardenasgutierrez-droid) together with [@coffeedrunkpanda](https://github.com/coffeedrunkpanda/King-County-Housing-Analysis) and [@sheetansh](https://github.com/sheetansh/IronKaggle_DSML) for the Ironhack bootcamp of Data Science & Machine Learning.
