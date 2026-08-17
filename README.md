# Treasury Yields vs. Gold: Quantitative Research

An exploratory quantitative-finance project studying the relationship between U.S. Treasury yields and gold (XAU/USD), combining fixed-income theory, time-series analysis, and predictive modeling with scikit-learn.

## Research Question

How do changes in nominal and real U.S. Treasury yields relate to gold returns, and can information from the Treasury market provide useful information about subsequent gold movements?

The project begins with contemporaneous relationships and then moves toward the harder question of out-of-sample prediction.

## What This Project Covers

- Bond pricing and the price-yield relationship
- Macaulay duration and interest-rate sensitivity
- Convexity and nonlinear price-yield behavior
- Cleaning and aligning Treasury and gold time series
- Gold log returns and Treasury yield changes
- Pearson correlations and statistical significance
- Rolling correlations and time-varying relationships
- Nominal versus real Treasury yields
- Lagged relationships with future gold returns
- Chronological train/test splitting
- A zero-return naive benchmark
- Predictive evaluation with MSE, MAE, and R²
- A practical scikit-learn modeling workflow

## Data and Methodology

The analysis combines historical gold prices with U.S. Treasury yield series across multiple maturities, including nominal yields and real yields from Treasury Inflation-Protected Securities.

Gold prices are transformed into log returns and Treasury yields into daily changes. The datasets are aligned by date before relationships are measured.

The project first studies contemporaneous correlations and then rolling correlations to determine whether the rates-gold relationship changes through time. For prediction, the next trading day's gold return is aligned with information available on the current day.

The modeling data is split chronologically rather than randomly. This keeps later observations unseen during training and better represents the way a model would encounter financial data in practice.

A naive benchmark predicts a next-day gold return of zero. More sophisticated models can therefore be evaluated against a simple reference rather than interpreted in isolation.

## Evaluation

**MAE (Mean Absolute Error)** measures the typical absolute forecast error.

**MSE (Mean Squared Error)** penalizes large forecasting mistakes more heavily.

**R²** compares squared-error performance with a reference based on predicting the target mean. Out-of-sample R² can be negative when predictions perform worse than that reference.

## Key Lessons

One of the central lessons of the project is that **correlation is not prediction**. Treasury yields can exhibit economically meaningful contemporaneous relationships with gold without necessarily providing reliable next-day forecasting power.

The project also demonstrates why financial models should be evaluated on later, unseen observations and compared against simple benchmarks.

Beyond the empirical results, the project provided practical experience connecting bond pricing, duration, convexity, nominal yields, and real yields with Python-based quantitative research and scikit-learn.

## Limitations and Future Work

This is an exploratory research project rather than a production trading strategy. The sample period is limited, financial relationships can change across regimes, and many macroeconomic variables affecting gold are outside the current feature set.

Possible extensions include:

- Breakeven-inflation features
- Yield-curve slope and curvature
- 5-day and 20-day forecast horizons
- Ridge and Lasso regression
- PCA of yield-curve movements
- Walk-forward validation
- Market-regime analysis
- Trading signals and transaction costs

## Tools

Python, pandas, NumPy, Matplotlib, SciPy, and scikit-learn.

## Repository Structure

```text
treasury-yields-gold-quant-research/
├── treasury-yields-gold-quant-research.ipynb
└── README.md
```

## Purpose

The project was built to develop practical quantitative-research skills by combining financial theory, statistical reasoning, data analysis, and machine learning in a reproducible workflow.
