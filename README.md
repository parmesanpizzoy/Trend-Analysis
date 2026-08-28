EGIER Bag Production Trend Analysis

Mathematical Modeling & Numerical Methods

A Python-based data analysis project that studies EGIER's monthly bag production trend and estimates when production may reach the current warehouse capacity.

Overview

This project uses historical production data from January 2018 to December 2023 (144 months).

The analysis aims to:

Explore historical production trends

Fit multiple mathematical models

Compare model performance using RMSE

Forecast when production reaches 25,000 units

Estimate when a new warehouse should begin construction using a 13-month lead time

Demonstrate numerical techniques including Horner's method, Taylor approximation, and root finding

Dataset

Property

Value

Observation period

January 2018 – December 2023

Observations

144 months

Initial production

1,863 units

Latest observed production

17,689 units

Warehouse capacity

25,000 units

Construction lead time

13 months

Methodology

1. Exploratory Analysis

The historical production series is visualized to identify the overall production trend.

2. Mathematical Modeling

Four candidate models are fitted:

Quadratic

Cubic

Exponential

Logistic

Each model is evaluated using Root Mean Square Error (RMSE).

The model with the lowest RMSE is selected for the capacity forecast.

3. Capacity Forecasting

The selected model is used to solve:

production(month) = 25,000

A bracketing root-finding method (scipy.optimize.brentq) is used to locate the first capacity crossing found beyond the observed period.

The estimated construction start is calculated as:

capacity_month - 13 months

4. Numerical Methods

The notebook also demonstrates:

Horner's method for efficient cubic polynomial evaluation

Third-order Taylor approximation

Numerical error comparison

Root finding

Results

The notebook calculates the final model selection and capacity forecast programmatically when it is run.

This is intentional: rather than hard-coding a potentially outdated forecast into the README, the result is regenerated directly from the current dataset and model-fitting procedure.

Run the notebook to see the current:

Best-fitting model

RMSE for each candidate model

Estimated capacity-reaching month

Recommended construction-start month

Numerical approximation errors

Visualizations

The notebook produces visualizations for:

Historical production trend

Comparison of fitted mathematical models

Production forecast and warehouse capacity

Numerical approximation errors

Tech Stack

Python

NumPy — numerical computation

SciPy — curve fitting and root finding

Matplotlib — data visualization

Jupyter Notebook / Google Colab

Project Structure

Trend-Analysis/
├── README.md
├── SC_2802499365_clean.ipynb
└── requirements.txt

How to Run

Option 1 — Google Colab

Open the notebook in Google Colab and run the cells from top to bottom.

Option 2 — Local Environment

Clone the repository:

git clone https://github.com/parmesanpizzoy/Trend-Analysis.git
cd Trend-Analysis

Install the dependencies:

pip install -r requirements.txt

Then open:

jupyter notebook SC_2802499365_clean.ipynb

Limitations

This project is a mathematical forecasting exercise, so the results should be interpreted as estimates rather than guaranteed future outcomes.

Important limitations include:

The forecast extends beyond the historical observation period.

Long-range extrapolation is sensitive to model assumptions.

RMSE evaluates historical fit and does not guarantee future predictive accuracy.

External factors such as demand, supply, and operational constraints are not modeled.

The warehouse construction estimate assumes a fixed 13-month lead time.

The model should therefore be re-evaluated as new production data becomes available.

Key Takeaway

This project demonstrates how data analysis + mathematical modeling + numerical methods can be combined to turn historical production data into a practical capacity-planning estimate.
