# 🚲 Bike Sharing Demand Analysis (Seoul)

This repository demonstrates a complete exploratory data analysis (EDA) and machine learning pipeline for predicting hourly bike sharing demand in Seoul, South Korea. The project is performed in Python and organized as a Jupyter notebook: [`Bike.ipynb`](Bike.ipynb).

---

## 📂 Dataset Description

The dataset (`SeoulBikeData.csv`) records hourly bike rental counts along with weather, seasonal, temporal, and holiday information for Seoul over a period of one year.

**Columns:**
| Name                        | Description                                      | Type    |
|-----------------------------|--------------------------------------------------|---------|
| Date                        | Date (dd-mm-yyyy)                                | object  |
| Rented Bike Count           | Target variable: Number of bikes rented          | int     |
| Hour                        | Hour of the day (0–23)                           | int     |
| Temperature(°C)             | Temperature in Celsius                           | float   |
| Humidity(%)                 | Relative humidity (%)                            | int     |
| Wind speed (m/s)            | Wind speed (m/s)                                 | float   |
| Visibility (10m)            | Visibility (10m units)                           | int     |
| Dew point temperature(°C)   | Dew point temperature                            | float   |
| Solar Radiation (MJ/m2)     | Solar radiation                                  | float   |
| Rainfall(mm)                | Rainfall (mm)                                    | float   |
| Snowfall (cm)               | Snowfall (cm)                                    | float   |
| Seasons                     | Spring, Summer, Autumn, Winter                   | object  |
| Holiday                     | Holiday/No Holiday                               | object  |
| Functioning Day             | Yes/No (if bike sharing system was working)      | object  |

---

## 📝 Project Structure

- **Data Inspection:** Load, preview, and check the structure and completeness of the data.
- **Data Cleaning:** Handle missing values, duplicates, and outliers.
- **Feature Analysis:** Separate, inspect, and visualize categorical and numerical variables.
- **Exploratory Data Analysis (EDA):** Visualize distributions, trends, and relationships.
- **Feature Engineering:** (If applicable) Create or transform features for better model performance.
- **Model Building:** Train and evaluate several regression algorithms.
- **Model Evaluation:** Compare and interpret model performances.

---

## 1. Data Inspection & Cleaning

- **Shape & Columns:** 8760 rows × 14 columns (covers every hour for 365 days).
- **Duplicates:** Checked for and found zero duplicate rows.
- **Missing Values:** No missing values in any column.
- **Data Types:** Columns classified into numerical and categorical variables.
- **Outliers:** Identified but not explicitly removed at this stage.

---

## 2. Categorical & Numerical Variables

- **Categorical Variables:** `Date`, `Seasons`, `Holiday`, `Functioning Day`
    - Example: `Seasons` (Spring, Summer, Autumn, Winter), `Holiday` (Holiday, No Holiday)
- **Numerical Variables:** `Rented Bike Count`, `Hour`, `Temperature(°C)`, `Humidity(%)`, `Wind speed (m/s)`, `Visibility (10m)`, `Dew point temperature(°C)`, `Solar Radiation (MJ/m2)`, `Rainfall(mm)`, `Snowfall (cm)`

Frequency counts and unique categories for all categorical variables are displayed in the notebook.

---

## 3. Exploratory Data Analysis (EDA)

- **Descriptive Statistics:** Used `.describe()` for central tendencies and spread.
- **Distribution Plots:** Histograms and boxplots for numerical features; countplots for categorical ones.
- **Correlation Analysis:** Heatmaps to identify which features are most associated with bike rental demand.
- **Temporal Trends:** Line plots to show bike counts by hour, day, season, and holiday.
- **Weather Relationships:** Scatterplots and jointplots between bike count and weather features (e.g., temperature, humidity).

---

## 4. Feature Engineering

- **Encoding:** Transformed categorical variables (e.g., seasons, holiday) into numerical or dummy variables suitable for modeling.
- **Scaling:** Applied MinMaxScaler to standardize features for algorithms sensitive to scale.
- **Train/Test Split:** Data is split into training and test sets (e.g., 80/20 split) for fair model evaluation.

---

## 5. Model Building

Multiple regression models are trained and compared:
- **Linear Regression**
- **Lasso Regression (L1 Regularization)**
- **Ridge Regression (L2 Regularization)**
- **ElasticNet Regression**
- **Decision Tree Regressor**
- **Random Forest Regressor**
- **XGBoost Regressor**

**Model Selection:** Hyperparameter tuning is performed using GridSearchCV for tree-based and regularized models.

---

## 6. Model Evaluation

- **Metrics Used:** R² Score, Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE)
- **Visual Comparison:** Bar plots of model performance metrics.
- **Feature Importance:** Tree-based model feature importances are visualized for interpretability.

---

## 7. Key Findings & Insights

- **Temporal Importance:** Hour of the day and season have strong effects on rental demand.
- **Weather Effects:** Temperature and humidity are important predictors.
- **Holiday/Functioning Day:** Rentals drop on holidays and non-functioning days.
- **Best Models:** (See notebook for details; typically ensemble models like Random Forest / XGBoost outperform linear models.)

---

## 8. How to Run

**Requirements:**
- Python 3.x
- Jupyter Notebook

**Install Dependencies:**
```bash
pip install numpy pandas matplotlib seaborn scikit-learn xgboost statsmodels tabulate
```

**Run Analysis:**
1. Clone the repository:
    ```bash
    git clone https://github.com/Aamod007/Bike-Sharing.git
    cd Bike-Sharing
    ```
2. Make sure `SeoulBikeData.csv` is in the project directory.
3. Launch Jupyter and open `Bike.ipynb`:
    ```bash
    jupyter notebook
    ```
4. Run all cells to reproduce the analysis and results.

---

## 📊 Visualizations

The notebook includes:
- Distribution and boxplots for all features
- Correlation heatmaps
- Time series bike count plots (hourly, daily, by season)
- Feature importance plots

---

## 📌 Author

- [Aamod007](https://github.com/Aamod007)

## 📄 License

Licensed under the MIT License.

---

**For all details, code, and in-depth analysis, see the [`Bike.ipynb`](Bike.ipynb) notebook.**
