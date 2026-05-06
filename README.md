# Data Science Project: Retail Forecasting

## Executive Summary

For this project, I used retail data from Kaggle (Singh, M. (2017)) to develop a proof-of-concept forecasting solution. The aim is to help store management make proactive, data-driven decisions around inventory management, staffing, and marketing strategies. By predicting sales for the following financial year—using historical data and seasonal trends—the model supports improved operational efficiency and customer satisfaction.

The project follows the data analysis life cycle:
- Business understanding
- Data collection, cleaning, and pre-processing
- Exploratory Data Analysis (EDA)
- Model selection, training, evaluation, and validation
- Forecasting
- Visualization and reporting

This structured approach ensures clarity of purpose and outcome.

**Key Findings:**  
The SARIMA model outperformed SARIMAX, achieving lower RMSE and MAE scores and more accurate forecasts. The project demonstrates how time series modeling can enhance operational efficiency, enabling retail clients to anticipate sales trends and optimize resources.

---

## Data Infrastructure & Tools

**Data Source:**  
- Retail data organized in a Relational Database Management System (RDBMS).
- Data tables joined via primary and foreign keys (Store, Date, IsHoliday).

**Tools & Libraries Used:**  
- **JupyterLab:** Interactive coding, analysis, and documentation.
- **Python:** Rich ecosystem for data manipulation and analysis.
    - **pandas:** Data handling and analysis
    - **seaborn:** Statistical graphics
    - **NumPy:** Computation and indexing
    - **statsmodels/sklearn:** Analytics and modeling
    - **matplotlib:** Data visualizations

These tools ensure data integrity, scalability, and accelerate prototyping and reproducibility.

---

## Data Engineering

- The dataset is quantitative open-source data.
- For business deployment, GDPR compliance would be required with internal/operational data.
- Data validation and cleaning steps:
    - **Accuracy:** Correct, error-free data
    - **Completeness:** No missing data
    - **Consistency:** Uniform formatting
    - **Uniqueness:** No duplicates
    - **Timeliness:** Current and relevant

Steps taken:
- Missing values addressed with `ffill`
- Dropped unnecessary columns (e.g., Markdown)
- Checked for duplicates
- Data merged via shared columns (Store, Date, IsHoliday)
- Created a time-indexed DataFrame
- Data resampled by week for clearer trend analysis
- Train/test split for evaluation

---

## Data Visualization & Dashboards

- Data aggregated over weeks, months, quarters, and years for trend analysis.
- Visualizations highlighted consistent spikes in December sales, with no strong overall trend.
- Seasonal decomposition (Observed, Trend, Seasonal, Residual) made patterns clear.
- ACF and PACF plots used to determine SARIMA parameters (p=4, q=3).

---

## Data Analytics

- EDA revealed regular seasonal spikes in December sales.
- Augmented Dickey-Fuller test indicated the data is stationary (p-value < 0.05).

**Modeling:**
- **SARIMA:** Predicts sales based on historic data and seasonality.
    - RMSE: 3,031,406.46 | MAE: 2,682,480.98
- **SARIMAX:** Incorporates external variables (holidays).
    - RMSE: 5,277,624.39 | MAE: 3,087,215.42

SARIMA performed better on error metrics, while SARIMAX aligned more closely with holiday periods.

**Limitations and Ethical Considerations:**
- Incorporating refined external variables could further improve accuracy.
- When used with client data, ensure privacy, compliance, and clear documentation.

---

## References

Singh, M. (2017). Retail Data Analytics, Kaggle. [Kaggle Dataset](https://www.kaggle.com/datasets/manjeetsingh/retaildataset/data) (Accessed: 01 May 2026)

---
