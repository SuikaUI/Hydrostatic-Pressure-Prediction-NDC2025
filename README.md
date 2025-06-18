# 🌊 Regression Rumble NDC 2025 - Hydrostatic Pressure Prediction

## Competition Results
**RANK 2 ACHIEVED** out of **100+ teams** on the Private Leaderboard!

**Final Score:** R² = 0.997 (Private Leaderboard)

---

## Team Members

| Name | GitHub Profile |
|------|----------------|
| **Rahardi Salim** | [@RahardiSalim](https://github.com/RahardiSalim) |


---

## Project Overview

This project presents a comprehensive and highly accurate solution for predicting hydrostatic pressure from complex oceanographic data, as part of the Neurontara Data Clash 2025 competition (Regression Rumble). The primary challenge involved inferring hydrostatic pressure from dozens of physical, chemical, and optical observations, with a critical twist: the crucial `total_light_exposure` feature was present in the test set but entirely absent from the training data, necessitating advanced imputation and feature engineering.

### Problem Statement

Oceanographers rely on hydrostatic pressure measurements to understand vital ocean phenomena such as currents, stratification, and habitat changes. Accurately inferring this pressure from other readily available sensor data, especially when specific direct measurements might be missing or limited, is crucial for comprehensive oceanographic analysis and modeling. The core challenge in this competition was to overcome the `total_light_exposure` data discrepancy between training and test sets while building a robust regression model.

### Our Solution

We developed a sophisticated hydrostatic pressure prediction system built on a multi-stage approach:

1.  **Advanced Missing Value Handling**: Employing sophisticated imputation techniques tailored to variable characteristics, including time-series imputation where appropriate.
2.  **Missing Value Flagging**: Creating explicit indicator variables to preserve and leverage patterns of missingness, which often carry predictive information.
3.  **Extensive Feature Engineering**: Generating a rich set of new features, including temporal components, cyclical encodings for periodic variables, and interaction terms to capture complex relationships within the ocean data.
4.  **Robust Ensemble Modeling**: Combining the predictive power of multiple algorithms using a **stacking ensemble with brute-force weight optimization based on Out-of-Fold (OOF) predictions**. This approach effectively integrates the strengths of high-performing gradient boosting models:
    * **CatBoost (`CatBoostRegressor`)**: Leveraged for its robust handling of categorical features and ordered boosting.
    * **XGBoost (`XGBRegressor`)**: Utilized for its speed, regularization, and performance, with careful one-hot encoding for categorical variables.
    * **LightGBM (`LGBMRegressor`)**: Chosen for its efficiency and native support for categorical features.

---

## Results & Performance

### 🏆 Competition Performance
-   **Private Leaderboard Score**: R² = 0.997
-   **Final Rank**: 2nd place out of over 100 participating teams.

### Key Insights:
-   **Ensemble Power**: The stacking ensemble with brute-force optimized weights proved highly effective, demonstrating superior generalization over individual base models. The diverse nature of CatBoost, XGBoost, and LightGBM contributed significantly to the ensemble's robustness.
-   **OOF Importance**: Utilizing Out-of-Fold predictions was crucial for building an unbiased blending layer, preventing data leakage and ensuring reliable weight optimization.
-   **Feature Engineering Impact**: Smart handling of the `total_light_exposure` discrepancy and the creation of rich contextual features were key to unlocking higher predictive accuracy.
-   **Robust Preprocessing**: The meticulous approach to missing value imputation and flagging ensured that the models received clean and informative data inputs.

---

## Project Structure

```
├── notebooks/             # Jupyter notebooks for EDA, Feature Engineering, and Model Development
├── data/                  # Raw and processed datasets (e.g., train.csv, test.csv, sample_submission.csv)
├── README.md              # Project overview and documentation
```

---

## 🏅 Achievement Highlights

-   **2nd Place** in Regression Rumble - Neurontara Data Clash 2025.
-   Achieved an **outstanding R² score of 0.997** on the private leaderboard.
-   Successfully addressed complex **missing feature challenges** through innovative data preprocessing and feature engineering.
-   Developed a **robust stacking ensemble** using brute-force weight optimization on OOF predictions.
-   Demonstrated strong analytical and modeling skills in a competitive data science environment.

---

## License

This project is licensed under the MIT License.
© 2025 Rahardi Salim.

---