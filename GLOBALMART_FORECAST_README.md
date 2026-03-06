# Sales Forecasting: E-Commerce Revenue Prediction
## Time Series Analysis for GlobalMart Retail

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Status](https://img.shields.io/badge/Status-Complete-success)]()
[![Data](https://img.shields.io/badge/Data-36%20Months-orange)]()

---

## Project Overview

Developed a time series forecasting model to predict 2026 monthly sales for GlobalMart Retail, an international e-commerce platform. This analysis enables data-driven business decisions for inventory planning, staffing allocation, and budget forecasting.

**Business Question:**  
*What will our monthly sales be in 2026 so we can optimize inventory, staffing, and marketing spend?*

**Key Results:**  
- **$77.8M projected revenue for 2026**  
- **29.4% year-over-year growth forecast**  
- **Peak season identified:** November ($9.0M) and December ($8.4M)  
- **Actionable recommendations** for Q4 inventory planning ($24.4M estimated need)

---

## Business Impact

### Strategic Value
This forecasting model provides GlobalMart with:
- **Inventory Optimization:** Plan stock levels 6-12 months in advance
- **Staffing Strategy:** Hire seasonal workers for peak periods (Q4)
- **Cash Flow Planning:** Prepare for 29% revenue increase
- **Marketing Budget:** Allocate 40% of budget to high-performing Q4 months

### Financial Impact
- **2026 Projected Revenue:** $77.8M
- **Expected Growth:** +29.4% vs 2025
- **Revenue Range:** $5.3M (low month) to $9.0M (peak month)
- **Q4 Revenue:** ~$24.4M (31% of annual sales)

---

## Methodology

### Forecasting Approach
Used **Trend + Seasonality Decomposition** method:

1. **Trend Analysis:** Linear regression to identify growth pattern
   - Monthly growth rate: $113,972/month
   - Base revenue: $1.66M
   
2. **Seasonal Pattern Recognition:** Calculate monthly multipliers
   - November: 1.31x (31% above average) - Black Friday
   - December: 1.20x (20% above average) - Holiday shopping
   - July: 0.87x (13% below average) - Summer slowdown

3. **Forecast Formula:**  
   ```
   Forecasted Sales = Trend Value × Seasonal Multiplier
   ```

### Why This Method Works
- **Simplicity:** Easy to understand and explain to stakeholders
- **Transparency:** Clear breakdown of trend vs seasonality
- **Accuracy:** Captures both growth and seasonal patterns
- **Business-Friendly:** Non-technical teams can interpret results

---

## Project Structure

```
GlobalMart Sales Forecasting/
│
generate data/
├── generate_sales_data.py         # Data generation (2023-2025)
|
data/
├── globalmart_sales_data.csv       # Historical sales data
analysis/
├── forecast_sales.py               # Forecasting analysis
│
visualization/
├── chart1_sales_forecast.png       # Historical + 2026 forecast
├── chart2_2025_monthly.png         # 2026 monthly breakdown
├── chart3_yearly_revenue.png       # Annual revenue trend
├── globalmart_2026_forecast.csv    # 2026 predictions
│
└── README.md                       # Project documentation
```

---

## Running the Analysis

### Prerequisites
```bash
pip install pandas numpy matplotlib
```

### Step 1: Generate Historical Data (2023-2025)
```bash
python generate_sales_data.py
```
**Output:** `globalmart_sales_data.csv` (36 months of sales data)

### Step 2: Run Forecasting Analysis
```bash
python forecast_sales.py
```
**Output:** 
- 2026 monthly forecasts
- 3 visualization charts
- `globalmart_2026_forecast.csv`

---

## Key Findings

### Historical Performance (2023-2025)

| Year | Total Revenue | Average Monthly Sales | Growth Rate |
|------|---------------|----------------------|-------------|
| 2023 | $30.9M | $2.6M | Baseline |
| 2024 | $40.7M | $3.4M | +31.8% |
| 2025 | $60.1M | $5.0M | +47.8% |

### 2026 Forecast

| Month | Forecasted Sales | Range (±10%) |
|-------|-----------------|--------------|
| January | $6.3M | $5.6M - $6.9M |
| February | $5.3M | $4.8M - $5.8M |
| July | $5.6M | $5.1M - $6.2M |
| November | $9.0M | $8.1M - $9.9M |
| December | $8.4M | $7.6M - $9.3M |

### Seasonal Insights

**High Season (Q4):**
- November & December account for ~22% of annual revenue
- Black Friday and holiday shopping drive peak sales
- Requires maximum inventory and staffing

**Low Season (Summer):**
- July & August show 10-13% below average sales
- Opportunity to reduce inventory costs
- Focus on customer retention over acquisition

---

## Business Recommendations

### 1. Inventory Management
**Action:** Increase Q4 inventory by 50% compared to Q2/Q3
- Estimated Q4 inventory need: $24.4M in sales → ~$12M in inventory
- Stock up by October to avoid supply chain delays
- Reduce summer inventory (July-August) by 20%

### 2. Staffing Strategy
**Action:** Hire seasonal workers for November-December
- Peak period: November-December (35% more sales than average)
- Recommended: +15-20 temporary staff members
- Can reduce staffing in July-August (slower months)

### 3. Marketing Budget Allocation
**Action:** Allocate 40% of annual marketing budget to Q4
- Focus on October (pre-holiday awareness)
- November (Black Friday campaigns)
- December (last-minute holiday shoppers)
- Summer: Shift budget to retention programs

### 4. Cash Flow Planning
**Action:** Secure working capital for Q4 inventory
- Prepare for 29% revenue increase ($17.7M more than 2025)
- Revenue fluctuates $3.8M between lowest and highest month
- Ensure sufficient cash reserves for inventory purchases

---

## Visualizations

### Chart 1: Sales Forecast (2023-2026)
Shows historical sales (2023-2025) and forecasted sales (2026) with confidence intervals.

**Key Insights:**
- Clear upward trend across all years
- Seasonal spikes in Q4 visible annually
- 2026 forecast follows established patterns

### Chart 2: 2026 Monthly Breakdown
Bar chart showing forecasted sales for each month in 2026.

**Key Insights:**
- November peak: $9.0M
- February low: $5.3M
- Q4 dominance clearly visible

### Chart 3: Yearly Revenue Comparison
Annual revenue comparison (2023-2026) showing consistent growth.

**Key Insights:**
- 95% revenue growth from 2023 to 2026 (3 years)
- Compound annual growth rate (CAGR): ~26%

---

## Technical Details

### Data Generation
- **Period:** 36 months (January 2023 - December 2025)
- **Components:** Base trend + seasonal patterns + random noise
- **Seasonality:** Monthly patterns (Black Friday, Christmas, summer slowdown)
- **Noise:** ±10% random variation (simulates real-world fluctuations)

### Forecasting Model
**Method:** Trend + Seasonality Decomposition

```python
# Calculate trend
slope, intercept = np.polyfit(month_index, sales, 1)

# Calculate seasonal indices
seasonal_factor = actual_sales / trend_value

# Generate forecast
forecast = (slope × month_index + intercept) × seasonal_factor
```

**Confidence Intervals:** ±10% range around forecast

### Model Validation
- **Training Period:** 36 months (2023-2025)
- **Forecast Horizon:** 12 months (2026)
- **Accuracy Metrics:** Visual inspection, pattern consistency
- **Assumptions:** Historical patterns continue, no major market disruptions

---

## Skills Demonstrated

### Technical Skills
- **Time Series Analysis:** Trend decomposition and seasonal pattern recognition
- **Python Programming:** pandas, numpy, matplotlib
- **Data Visualization:** Multi-chart dashboards with clear business insights
- **Statistical Forecasting:** Linear regression, seasonal indexing

### Business Skills
- **Strategic Planning:** Inventory, staffing, and budget recommendations
- **Financial Analysis:** Revenue projections and growth calculations
- **Stakeholder Communication:** Translating data into actionable insights
- **Decision Support:** Data-driven recommendations for C-suite

---

## Future Enhancements

Potential improvements for this analysis:

1. **Regional Forecasting:** Break down by geographic market (NA, Europe, Asia)
2. **Product Category Analysis:** Forecast by product line
3. **External Factors:** Incorporate marketing spend, economic indicators
4. **Advanced Models:** Test ARIMA, Prophet, or LSTM neural networks
5. **Real-Time Monitoring:** Compare actual 2026 sales to forecast monthly
6. **Automated Alerts:** Notify if actual sales deviate >15% from forecast

---

## What This Project Teaches

### Forecasting Fundamentals
- **Trend:** Long-term growth or decline pattern
- **Seasonality:** Repeating patterns (monthly, quarterly, yearly)
- **Noise:** Random fluctuations in data
- **Decomposition:** Separating signal from noise

### Business Applications
- E-commerce revenue planning
- Retail inventory optimization
- Workforce management
- Marketing budget allocation
- Cash flow forecasting

### Real-World Relevance
This methodology applies to:
- **Retail:** Store sales, foot traffic
- **E-commerce:** Online revenue, conversion rates
- **SaaS:** Subscription revenue, churn prediction
- **Supply Chain:** Demand forecasting, procurement planning
- **Finance:** Budget planning, revenue projections

---

## About This Project

This project was completed as part of my data analytics portfolio to demonstrate:
- Time series forecasting skills
- Business impact analysis
- Python data analysis capabilities
- Strategic thinking and planning
- Clear communication of complex insights

The dataset is simulated but follows realistic e-commerce patterns based on industry benchmarks and seasonal shopping behavior.

---

## Author

**Victoria Abdul**  
Data Analyst | Python | Time Series Forecasting

- Email: your.email@example.com
- LinkedIn: [linkedin.com/in/victoria-abdul](https://linkedin.com/in/victoria-abdul)
- GitHub: [github.com/vickieabdul](https://github.com/vickieabdul)

---

## License

MIT License - Free to use for educational and portfolio purposes.

---

**⭐ Star this repository if you found this analysis helpful!**

---

*Last Updated: March 2026*
