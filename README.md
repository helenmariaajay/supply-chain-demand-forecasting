# Supply Chain Demand Forecasting & Inventory Analysis

## Project Overview
Built a machine learning model to forecast retail demand and analyze supply chain patterns using Walmart sales data.

---

## Objectives
- Analyze seasonal demand trends
- Study holiday impact on sales
- Build a demand forecasting model
- Improve inventory planning insights

---

## Dataset
- Walmart Retail Dataset (~421K rows)
- Features: Store, Dept, Date, Weekly Sales, Holiday

---

## Tech Stack
- Python (Pandas, Scikit-learn)
- Matplotlib
- Jupyter Notebook

---

## Key Insights
- Sales peak mid-year (seasonality present)
- Holiday periods show higher demand
- Demand patterns vary across stores/departments
- Used time-based train-test split to avoid data leakage and ensure realistic forecasting

---
## Visualizations

### Monthly Sales Trend
![Sales Trend](sales_trend.png)

### Holiday vs Non-Holiday Sales
![Holiday Analysis](holiday_analysis.png)

---

## Model
- Random Forest Regressor
- Feature Engineering: Month, Year, Lag feature

---

## Results
- MAE: ~1715
- R² Score: ~0.97

---
## SQL Analysis

### Top Performing Stores
```sql
SELECT Store, SUM(Weekly_Sales) AS total_sales
FROM sales
GROUP BY Store
ORDER BY total_sales DESC
LIMIT 5;
```
### Monthly Sales Trend
```sql
SELECT 
    strftime('%m', date) AS month,
    SUM(weekly_sales) AS total_sales
FROM sales
GROUP BY month
ORDER BY month;
```
### Holiday vs Non-Holiday Sales
```sql
SELECT 
    isholiday,
    AVG(weekly_sales) AS avg_sales
FROM sales
GROUP BY isholiday;
```
---

## SQL Insights
- Store 20 has the highest total sales
- Sales peak in July, indicating strong seasonality
- Holiday periods show higher average sales, indicating demand spikes

---
## Business Impact
- Helps predict demand accurately
- Reduces stockouts during peak periods
- Supports inventory optimization

---

## Files
- `analysis.ipynb` → full code
- `model.pkl` → trained model
- `model.pkl` → saved trained model for reuse without retraining

---
## How to Run

1. Open `analysis.ipynb` in Google Colab or Jupyter Notebook  
2. Install required libraries:
   pip install pandas numpy scikit-learn matplotlib  
3. Run all cells to reproduce results  

---

## Author
Helen Maria Ajay
