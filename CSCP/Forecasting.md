# Forecasting

## Forecasting Principles and Process

### Principles of Forecasting

#### Definitions and Purpose

* **Forecasting**: The business function of predicting sales and product use to ensure appropriate purchasing or manufacturing quantities in advance.
* **Demand Planning**: A process combining statistical techniques and professional judgment to estimate demand across the entire supply chain—from raw materials to the consumer.
* **The "Why"**: Since everything in a supply network (capacity, warehousing, transportation) depends on customer purchases, forecasting is essential to avoid financial losses (overproduction) or losing customers to competitors (stockouts).

#### Key Principles of Forecasting

The text identifies five core principles that dictate how forecasting should be conducted and how much weight should be given to the results:

##### Base Forecasts on Demand, Not Orders

* **Orders vs. Demand**: Customer orders may be skewed by returns, anticipated shortages, or stockouts.
* **True Demand**: Forecasts should reflect what customers actually want. If a stockout occurs, an estimate must be made of the sales that would have happened if the product had been available.

##### Forecasts are (Almost) Always Wrong

* **The Reality of Error**: No matter how sophisticated the model, surprises and changing minds will always create some level of error.
* **The Bullwhip Effect**: Errors are magnified as they move up the supply chain. Inaccurate forecasts lead to increasingly volatile orders for suppliers.
* **Avoid Bias**: Forecasts should be data-driven rather than "goal-driven" (e.g., arbitrarily adding 10% to last year's sales).

##### Include an Estimate of Error

* **Margin of Error**: Like political polls, forecasts must include a range of likely error based on historical variability.
* **Actionable Data**: If error levels become too large, the process must be improved. Error should also be measured in **monetary value** to prioritize fixing the most expensive mistakes.

##### Forecasts are More Accurate for Groups (Risk Pooling)

* **Aggregation**: It is easier to forecast demand for a broad category (e.g., all blue jeans) than for a specific SKU (e.g., loose-fit Levi’s in a specific size).
* **Risk Pooling**: Aggregating individual risks into a pool reduces overall uncertainty.
* **Mix Forecasts**: While aggregate forecasts are more accurate, a "mix forecast" is still needed to predict the proportion of specific options or products sold within a family.

##### Near-Term Forecasts are More Accurate

* **Time Horizons**: The further into the future a forecast extends, the more likely "chance and change" will derail it.
* **Lead Times**: Shortening lead times for items is a primary strategy for improving accuracy, as it allows for a shorter forecasting horizon.

### Forecasting Process

#### 1. Determine the Purpose

Define what the forecast will drive. Is it for manufacturing targets, purchasing, determining warehouse capacity, or service staffing levels?

#### 2. Determine Aggregation Level

Specify what is being measured (units, total sales, or SKUs) and the level of detail (e.g., individual product vs. product family).

#### 3. Determine Time Horizon

Establish the planning "buckets" (weeks, months, or quarters) and whether the focus is short-, medium-, or long-term.

#### 4. Visualize the Data

Graph historical data to identify obvious patterns. This helps you spot **trends** (long-term movement) or **seasonality** (repetitive cycles) before choosing a model.

#### 5. Choose the Forecasting Method

* Quantitative: Use **time-series** if trends are steady, or **associative** models if external drivers are changing the trends.
* Qualitative: Use expert judgment when historical data is unavailable.

#### 6. Prepare the Data

Gather inputs and "clean" them. If the data shows strong seasonality, it should be **deseasonalized** (temporarily removed) to see the underlying trend clearly.

#### 7. Test the Model

Use historical data to "forecast" the past. By comparing your model’s results to what actually happened, you can find the most accurate method before applying it to the future.

#### 8. Generate the Forecast

Apply the chosen model to future periods. If seasonality was removed in Step 6, it must be **added back in** now. Apply any final qualitative adjustments from leadership or sales.

#### 9. Perform Sales and Operations Planning (S&OP)

Collaborate with demand-side, supply-side, and financial professionals to reach a consensus. The goal is a **one-number system**—a single forecast everyone agrees to use.

#### 10. Review and Improve

Continuously monitor for error. If errors grow unacceptably large, revisit the models and process to improve future accuracy.

## Forecasting Methods

### Qualitative and Combination Methods

These methods rely on experience and judgment rather than mathematical formulas. They are essential when historical data is missing (e.g., new product launches).

* **Judgmental/Expert Judgment**: Executives and sales teams use market knowledge to generate or adjust forecasts.
* **Delphi Method**: A sophisticated survey technique where a compiler gathers anonymous expert opinions in successive rounds to reach a consensus, preventing "groupthink" or "stake in the ground" mentalities.
* **Combination Methods**: The best practice of using quantitative models as a baseline and then applying qualitative adjustments based on known events (like a competitor's promotion).

### Quantitative Methods: Time-Series Forecasting

This category assumes that past trends will continue. Key steps include **Visualizing** data to find patterns and Deseasonalizing (removing seasonal spikes to find the base trend).

* **Simple Moving Average**: An average of the last $n$ periods. It smooths out random fluctuations but lags behind new trends.
* **Weighted Moving Average**: Similar to simple moving average but applies specific weights (usually higher for recent data) to make the forecast more responsive.
* **Exponential Smoothing**: Uses three inputs: last period’s forecast, last period’s demand, and a smoothing constant ($alpha$). It is highly effective for minimizing lag in shifting trends.
* **Reseasonalizing**: The final step of multiplying the deseasonalized forecast by the seasonal index to get a "real-world" number.

### Service-Sector Forecasting

Service businesses (like restaurants) face unique challenges because demand fluctuates **hourly** rather than monthly. Projections must account for day-of-week and time-of-day variations to manage perishable inventory and staffing.

### Quantitative Methods: Associative Forecasting

Also called causal forecasting, this uses **Independent Variables** (predictors) to estimate a **Dependent Variable** (demand).

* **Correlation vs. Causation**: Correlation shows a relationship exists; causation proves one event causes the other.
* **Leading Indicators**: Predictors that change before the economy/demand (e.g., building permits, stock indices).
* **Lagging Indicators**: Factors that confirm a trend after it has happened (e.g., unemployment rate, inventory-to-sales ratios).
* **Simple Regression**: A linear mathematical formula ($y = \alpha + \beta x$) used to find the strength of a relationship between two variables.
* **Multiple Regression**: An extension using multiple predictive variables (e.g., using both "housing starts" and "marketing spend" to predict sales).

## Measures of Forecast Error

### Forecast Error and Accuracy

* **Definition**: Forecast error is the difference between actual demand and forecast demand.
* **Measurement**: Error can be measured in units or percentages, but the text emphasizes placing a monetary value on error to prioritize the most expensive mistakes.
* **Calculations**:
  * **Absolute Error**: $|\text{Actual} - \text{Forecast}|$
  * **Forecast Accuracy**: The complement of the error percentage ($100\% - \text{Error Percentage}$).

### Bias vs. Random Variation

* **Bias**: A consistent deviation in one direction (consistently over-forecasting or under-forecasting). It is calculated using the cumulative sum of errors (not absolute values).
* **Random Variation**: Occurs when cumulative actual demand equals cumulative forecast demand over time, even if individual periods vary.

### Primary Error-Tracking Methods

#### Mean Absolute Deviation (MAD)

* **Concept**: The average of the absolute values of forecast errors.
* **Inventory Application**: MAD is a primary input for calculating Safety Stock.
* **Service Levels**:
  * $1 \text{ MAD} \approx 80\%$ service level.
  * $2 \text{ MAD} \approx 95\%$ service level.
  * $3 \text{ MAD} \approx 99\%$ service level.

#### Tracking Signal

* **Formula**: Ratio of the cumulative algebraic sum of errors to the MAD.
* **Purpose**: Monitors for forecast bias.
* **Threshold**: A rule of thumb is that if the signal goes outside the range of **+4 to -4**, the forecasting method should be reviewed.

#### Standard Deviation (SD)

* **Concept**: Measures the dispersion of data from the mean.
* **Rule of Thumb**: You can approximate Standard Deviation by multiplying $\text{MAD} \times 1.25$.

#### Mean Squared Error (MSE)

* **Concept**: Squares each error before averaging, which magnifies larger errors.
* **Usage**: Useful for a more sensitive measure of error when reduction of large deviations is critical.

#### Mean Absolute Percentage Error (MAPE)

* **Concept**: The average of the absolute percentage errors.
* **Advantage**: Allows for comparison across different products or families without needing to know the specific unit volumes (e.g., a $10\%$ error is understandable regardless of whether you sell 100 units or 10,000).