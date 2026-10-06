# TAXI-ROUTE-REVENUE-PRICING-FLEET-PLANNER
This project focuses on forecasting the demand and fares for a14 seater taxi having 3 daily routes.
Daily passenger counts over 10 days  and fares include:
- Kampala-Ntinda = [35, 40, 42, 50, 55, 60, 48, 52, 47, 45] fare UGX 2,000
- Kampala-Entebbe = [60, 58, 65, 70, 72, 80, 75, 68, 66, 64] fare UGX 5,000
- Kampala-Mukono = [45, 47, 50, 49, 55, 62, 58, 53, 51, 50] fare UGX 3,000 
 ### IMPLEMENTATION
- Created a Route class with passenger counts , fares and descriptive statistics.
- Created Supply-demand equilibrium for the Ntinda Route with assumed values.
- Created a Forecaster base class with three subclasses ( 3 day moving average, simple exponential smoothing with a tunable alpha and linear trend).
- Evaluated the forecasters with rolling origin back testing over days 4-10.
- Forecasted day 11 revenue for the best model per route.
- Plotted actual vs forecast revenue.
- Fleet planning.
- Illustrated the findings.
### FINDINGS, LIMITATIONS AND IMPLEMENTATION
- The Kampala-Entebbe route has the highest average number of passengesrs and subsequently, the highest revenue compared to the Kampala-Ntinda and Kampala-Mukono routes. The Kampala-Ntinda route has the highest standard deviation compared to the other two routes.
- In regards to the supply–demand equilibrium  for the Ntinda route ( demand Qd = 120 − 0.02P and supply Qs = 10 + 0.03P, where P is the fare in UGX and Q is passengers per trip-hour), the equilibrium fare  is UGX 2,200, with an equilibrium quantity of 76 passengers per trip-hour. The current fare of UGX 2,000 is UGX 200 below the equilibrium fare. This suggests that the current fare is lower than the market-clearing fare so passenger demand may exceed the quantity operators are willing to supply, potentially resulting in excess demand or shortages.
- The Simple Exponential Smoothing (SES) model was the best model for each of the three routes as it made less forecasting errors compared to the other models. For example for the Kampala-Ntinda route, SES made an average forecasting error of about 5.86 passengers, compared with 7.52 for moving average and 7.87 for linear trend. Overall, the linear trend performed worst among all models.
- For day 11, one vehicle should be deployed on each route. Each vehicle has a daily capacity of 112 passengers, based on 8 one-way trips per day and 14 passengers per trip. After applying a 15% demand buffer, the estimated requirements are 51.80 passengers for Ntinda, 73.62 for Entebbe, and 57.51 for Mukono. Since all buffered demands are below the capacity of one vehicle, one vehicle is sufficient for each route. The 15% buffer provides additional capacity to accommodate unexpected increases in passenger demand.

