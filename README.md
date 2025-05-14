## Introduction  
The repository contains the BUAN Experiential Project, an end-to-end retail sales analytics and forecasting study. The project goal is to transform raw transaction data into actionable insights—segmenting sales territories, evaluating promotion efficacy, and building demand-forecasting models—to help business stakeholders optimize inventory, marketing spend, and regional strategies.

## Data Collection & Preprocessing  
The workflow began with ingestion of monthly sales records, promotion logs, and store metadata. After joining these sources, missing values were cleaned, date and geographic fields were standardized, and new features were engineered (e.g., lagged promotions, holiday indicators). The final dataset spans 24 months, over 500 store-promotion combinations, and more than 200,000 individual transactions.

## Exploratory Data Analysis  
Overall sales trends and seasonal patterns were profiled. Key observations included strong year-end spikes, weekday/weekend behavior shifts, and clear correlations between promotional weeks and volume uplifts. Outliers—stores with consistently low sales—were also identified for further investigation.

## Segmentation & Clustering  
K-means clustering on normalized sales and customer-count metrics produced three distinct store segments:  
1. **High-volume flagship** (top 15% of stores by revenue)  
2. **Emerging growth** (mid-tier performance with strong month-over-month gains)  
3. **Underperforming** (bottom 20%, often in low-traffic zip codes)  
This segmentation enables tailored marketing and inventory strategies for each group.

## Promotion Impact Analysis  
Baseline vs. promotion scenarios were compared by simulating a coupon campaign (8 M coupons dropped, 10% redemption). Under promotion, average monthly sales increased by 12% but incurred incremental costs equal to the coupon payout. Profit-vs-sales trade-off analysis demonstrated that mid-tier “Emerging growth” stores achieved the highest ROI on promotional spend.

## Predictive Modeling & Forecasting  
Features encompassing past sales, promo flags, and calendar attributes were used to train multiple models (linear regression, random forest, and XGBoost). The XGBoost model achieved the lowest mean absolute percentage error (MAPE ≈ 8.5%) on hold-out data. A prediction pipeline was packaged to enable weekly forecasts at the store level.

## Dashboard & Visualization  
An interactive Tableau dashboard was developed, allowing:  
- Filtering by store segment, region, and date range  
- Side-by-side comparison of baseline vs. promotion scenarios  
- Drill-down into segment-specific KPIs (e.g., average basket size, coupon redemption rate)  
Decision-makers can explore “what-if” scenarios without code.

## Agile Methodology & Project Management  
Tasks were tracked in Jira throughout the eight-week sprint, accompanied by bi-weekly standups. The backlog included data-engineering stories, modeling tasks, and dashboard designs. Each sprint culminated in a demo to facilitate rapid feedback and continuous improvement.

## Results & Conclusions  
The combination of clustering, scenario analysis, and robust forecasting delivered:  
- A clear segmentation framework for targeted marketing  
- Quantified promotion ROI by segment  
- A reliable forecasting engine to inform inventory and staffing  
Business stakeholders can now allocate resources more efficiently and anticipate demand fluctuations with greater confidence.

## Future Work  
Potential next steps include integration of external data (e.g., competitor pricing, weather), exploration of deep-learning approaches for anomaly detection, and automation of the prediction pipeline with CI/CD. Scaling the dashboard for mobile devices and adding real-time alerts for sales anomalies could further enhance operational responsiveness.
