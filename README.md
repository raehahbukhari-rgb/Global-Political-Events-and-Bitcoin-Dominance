Global Political Events and Bitcoin Market Dominance Dynamics
Overview

This project studies how global political events affect Bitcoin’s market dominance — the percentage of the total cryptocurrency market value that comes from Bitcoin. When political situations change, investors often adjust their risk behavior. The goal of this project is to explore whether political instability or uncertainty is associated with shifts toward Bitcoin, and how that changes the balance between Bitcoin and the rest of the crypto market.

Rather than attempting to predict the crypto market, this project focuses on understanding patterns and relationships using exploratory data analysis, statistical testing, and a simple machine learning baseline.

Motivation

I actively follow crypto trading and market behavior and often notice that during periods of global tension — such as wars, sanctions, or major elections — Bitcoin appears to strengthen relative to altcoins. This observation motivated me to investigate whether these movements are random or whether there is a measurable relationship between global political events and Bitcoin dominance.

If such a relationship exists, it could help explain how investors respond to uncertainty and whether Bitcoin functions as a relative “safe zone” within the crypto ecosystem during unstable periods.

Data

This project uses two main datasets:

1. Bitcoin Dominance Data (BTC.D)

Source: TradingView

Symbol: BTC.D

Description: Daily open, high, low, and close values for Bitcoin dominance

Usage: The daily closing value is used as the Bitcoin dominance percentage

File: /data/BTC_D_dataset.csv

2. Political Events Data (2020–2025)

Description: A manually compiled dataset of major global political events, including:

Elections

Wars and armed conflicts

Geopolitical shocks

Major political or financial crises

Sources: Reliable public sources such as international news outlets and Wikipedia’s year-by-year political timelines

File: /data/political_events_2020_2025.csv

After loading both datasets, they are merged using the date column to create a unified dataset named btc_dominance_with_events.csv, which is also included in the /data folder.

Data Source Note

Initially, I planned to use CoinGecko and GDELT APIs directly. However, CoinGecko’s free API does not provide a clean historical Bitcoin dominance time series, and some historical data endpoints returned errors. Because of these limitations, I switched to TradingView’s BTC.D data (exported as CSV) and a manually curated political events dataset based on reliable public sources.

Data Cleaning and Feature Engineering

Several preprocessing steps were applied before analysis:

Dates were converted to a standard datetime format and sorted chronologically

Column names were cleaned to avoid formatting issues

A binary variable (event_flag) was created to indicate whether a political event occurred on a given day

Daily changes in Bitcoin dominance (btc_change) were calculated using first differences

Rows with missing values caused by differencing were removed

These steps ensured that the dataset was clean, consistent, and suitable for both statistical analysis and modeling.

Exploratory Data Analysis (EDA)

To analyze the data from multiple perspectives, several visualizations were created, including:

Bitcoin dominance over time to observe long-term trends

Bitcoin dominance with political event days highlighted

Distributions of daily dominance changes

Boxplots comparing event days versus non-event days

Rolling averages to smooth short-term volatility

Comparisons of dominance behavior around event dates

These visualizations help illustrate the volatility of Bitcoin dominance and show that political event days are relatively rare compared to non-event days.

Statistical and Machine Learning Analysis

The analytical approach includes:

Descriptive statistics comparing event and non-event days

A two-sample t-test to test whether average dominance differs between event and non-event days

A simple linear regression model using:

Feature (X): event_flag

Target (y): daily change in Bitcoin dominance (btc_change)

A train/test split to evaluate out-of-sample performance

The regression model is intentionally simple and interpretable, serving as a baseline rather than a predictive system.

Results and Interpretation

The results suggest that political events do not consistently lead to large or predictable short-term changes in Bitcoin dominance. While some political events coincide with noticeable movements, the overall effect is weak and inconsistent. The regression model produces a very low test R² score, indicating that political events alone explain very little of the variation in daily dominance changes.

This suggests that Bitcoin dominance is influenced by many other factors such as broader market cycles, investor sentiment, and macroeconomic conditions.

Expected Results (Initial Hypothesis)

Initially, I expected that during politically unstable periods, Bitcoin dominance would increase as investors shift toward a more established digital asset. During calmer or optimistic periods, I expected dominance to decline as investors move toward altcoins seeking higher returns.

The analysis shows that while this behavior may occur in some cases, it is not strong or consistent across the full dataset.

Limitations

This project has several limitations:

Political event data may not cover all regions or events equally

The number of event days is very small compared to non-event days

Bitcoin dominance is affected by many factors beyond politics (e.g., ETFs, regulatory news, exchange activity)

The analysis focuses on short-term effects only

These limitations are acknowledged and discussed as part of the analysis.

How to Run the Project

Install the required Python packages:

pip install -r requirements.txt


Open the notebook:

/notebooks/DSA_210_project.ipynb


(using Google Colab or Jupyter)

Run all cells in order. This will:

Load the datasets from /data

Clean and merge the data

Generate visualizations

Run statistical tests and the baseline machine learning model

Save btc_dominance_with_events.csv into /data

AI Assistance Disclosure

I took assistance from AI during this project mainly for help with understanding errors, explaining certain Python methods, and improving the wording of my explanations.
