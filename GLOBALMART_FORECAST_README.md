# GlobalMart Sales Forecasting: E-Commerce Revenue Prediction

---
## Project Overview
This project analyzes three years of sales data from GlobalMart Retail and builds a monthly forecast for 2026 to support inventory planning, staffing decisions, and budget allocation.
The business challenge is one that most growing e-commerce companies face: revenue is accelerating year over year but without a reliable forward view, operational decisions around stock, headcount, and marketing spend end up reactive rather than planned. This project gives GlobalMart that forward view.

---
## Business Problem
What will GlobalMart's monthly sales be in 2026, and what should the business do differently across the year to prepare for it?

---
Dataset Description
The dataset contains 36 months of historical sales data from January 2023 through December 2025, including:
- Monthly revenue figures across the full three year period
- Year over year growth rates
- Seasonal performance patterns by month
- Total revenue of $131.67M across the historical period

---
## Tools Used

- Python (Pandas, NumPy, Matplotlib)
- Linear trend modeling with seasonal decomposition

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

## Analysis Structure
1. Exploratory Analysis
Examined three years of revenue data to understand the growth trajectory and identify any structural patterns worth carrying into the forecast.
2. Trend and Seasonality Decomposition
Separated the data into two components: a long term growth trend and a seasonal index showing how each month typically performs relative to the annual average. This decomposition is what makes the forecast reliable rather than just an extrapolation of recent results.
3. 2026 Forecast
Applied the trend and seasonal model to generate monthly forecasts for all 12 months of 2026, with a confidence range of plus or minus 10% per month to account for uncertainty.
4. Business Recommendations
Translated the forecast into specific operational decisions around inventory, staffing, marketing spend, and cash flow planning.

---

## Key Insights

- GlobalMart has been growing fast. Revenue went from $30.86M in 2023 to $40.69M in 2024, a 31.8% increase, and then to $60.12M in 2025, a 47.8% increase. The business is accelerating.
- The 2026 forecast puts total revenue at $77.79M, representing 29.4% growth over 2025 and an average monthly run rate of $6.48M.
- November is the peak month every year. In 2025 it hit $7.98M and the 2026 forecast puts it at $9.04M. November and December together account for roughly 25% of annual revenue.
- February is consistently the weakest month, forecast at $5.28M in 2026, creating a $3.75M swing between the lowest and highest months of the year. That gap has direct implications for cash flow and inventory management.
- Summer months from June through August consistently underperform the annual average, with seasonal indices between 0.87 and 0.92. The business slows predictably every year during this period.

---

## Recommendations
- Q4 is where GlobalMart wins or loses the year. November and December alone are forecast to generate $24.4M in 2026, which is nearly a third of annual revenue. Inventory should be built up from October and staffing should be scaled starting in mid October with peak headcount in place by November. Any supply chain delays or stockouts during this window have an outsized impact on annual performance.
- Summer is the time to invest in retention, not acquisition. With seasonal indices below 1.0 from June through August, pushing hard on customer acquisition during slow months is an inefficient use of marketing budget. The smarter move is to focus summer spend on keeping existing customers engaged so they return in Q4.
- Marketing budget allocation should reflect the seasonal reality. Approximately 40% of the annual marketing budget directed toward Q4 is justified by the revenue concentration in that period. The remaining 60% should be weighted toward the months that show the strongest conversion potential, particularly January, April, and September, which all carry seasonal indices above 1.0.
- Cash flow planning needs to account for the monthly revenue gap. A $3.75M difference between the weakest and strongest months means the business needs adequate working capital to fund inventory buildup in Q3 before the Q4 revenue arrives. This should be factored into the 2026 budget cycle.
- The forecast should be treated as a living document. Actual monthly results in 2026 should be compared against these projections and the model updated as new data comes in. If actuals deviate significantly from forecast, the seasonal indices may need to be recalibrated.

---

## Executive Conclusion
GlobalMart is on a strong growth trajectory and the 2026 forecast of $77.79M reflects that momentum continuing. But growth at this pace creates operational risk if the business is not prepared for it. The forecast makes clear that Q4 preparation is the single most important operational priority of the year, that summer requires a different playbook than the rest of the calendar, and that the gap between peak and trough months demands proactive cash flow management.

The dataset used for this project was generated using Claude AI.
---

## Author

**Victoria Abdul**  
Data Analyst | Python | Time Series Forecasting

- Email: victoria.j.abdulkadir@gmail.com
- LinkedIn: [linkedin.com/in/victoria-abdul](https://www.linkedin.com/in/victoriajabdul/)
- GitHub: [github.com/vickieabdul](https://github.com/vickieabdul)

---

## License

MIT License - Free to use for educational and portfolio purposes.

---

**⭐ Star this repository if you found this analysis helpful!**

---

*Last Updated: March 2026*
