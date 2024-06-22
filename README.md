Tableau Sales Insights - Part 2

Feedback and Adjustments

Feedback from Higher Authorities and Sales Team
After meetings and discussions with the higher authorities and the sales team, we received the following feedback:

1. Issue with Top 5 Customers by Market**:
   - Problem: When selecting "Delhi" in the "Revenue by Market" section of the Part 1 dashboard, only the top 3 customers out of 5 are displayed. The request is to show the top 5 customers from the entire dataset.
   - Solution: Go to the "Top 5 Customers" sheet. Select each filter dropdown menu and choose "Add to Context."

2. Declining Sales**:
   - Question: What are your suggestions as an analyst to increase our profit or what decisions would you recommend to peak our business?
   - Suggestions: Increasing profit depends on various factors such as quality, promotion, advertisements, healthy communication between management and suppliers, packaging, deciding which area product to be sold, and business growth. It takes time to show profit based on team hard work.
   - KPI Indicators: Include breakdowns for sales such as brick-and-mortar, top 5 customers with the highest number of orders, and identify which zone needs hiring/firing of sales managers based on performance. Implement a dynamic red alert in the dashboard whenever the performance of certain zones falls below a threshold.

Adjustments to the Dashboard
Based on the feedback, we will create an updated dashboard. Please note the column naming adjustments:
- Profit Margin: Profit
- Profit Margin Percentage: Profit Percentage

Creating the Updated Dashboard

1. Profit:
   - Description: This measures how much profit is made by selling products.
   - Steps: Drag the sum of the "Profit Margin" to marks and then to text.

2. Profit Margin by Market:
   - Description: This shows the profit margin for each market.
   - Steps: Create a new field using the formula:
     sql
     SUM([Profit Margin]) * 100 / SUM([Normalized Amount])
   - Columns: Market
   - Rows: Calculated field for profit margin

3. Profit Trend:
   - Description: This shows the trend of profit over time.
   - Steps: Drag "CY-Date" to columns and "SUM(Normalized Amount)" to rows.

4. Per Customer Profit Margin:
   - Description: This shows the profit margin for each customer.
   - Steps: Drag "Customer Name" to columns and "Profit Percentage Margin" to rows.

5. Pie Chart for Customer Type:
   - Description: This shows the distribution of sales between brick-and-mortar customers.
   - Steps: Create a pie chart with the customer types and their respective sales amounts.

Implementing Dynamic Alerts
To add dynamic red alerts in the dashboard:
1. Create a calculated field to flag underperforming zones:
   sql
   IF [Performance] < [Threshold] THEN "Red Alert" ELSE "Normal" END
2. Use this calculated field in the dashboard to visually indicate zones that need attention.

Conclusion
We have created an updated dashboard based on the feedback from the higher authorities and the sales team. This includes fixing the issue with the top 5 customers display, addressing declining sales, and implementing KPI indicators and dynamic alerts.

Final Note
I hope you found this tutorial helpful and interesting. I have tried my best to provide you with clear and actionable insights. Thank you for your patience.

Updated database and sample output pictures are uploaded in the repository. Try it yourself and see the results.

Good luck and stay connected for more such information!
