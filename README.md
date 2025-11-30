Global Political Events and Bitcoin Market Dominance Dynamics
Overview

This project studies how global political events affect Bitcoin’s market dominance — the percentage of the total crypto market value that comes from Bitcoin.
When political situations change, investors often adjust their risk behavior. I want to see if political instability or uncertainty makes people move their money toward Bitcoin, and how that changes the balance between Bitcoin and the rest of the crypto market.

Motivation

I follow crypto trading and often notice that during wars, sanctions, or elections, Bitcoin becomes stronger compared to other coins. My idea is to check if these changes are random or if there is a clear pattern between world politics and Bitcoin’s dominance. If the connection exists, it might explain how investors react to global uncertainty and what kind of “safe zone” Bitcoin provides in such times.

Data

This project uses two main datasets:

1. Bitcoin Dominance Data (BTC.D)

Source: TradingView

Symbol: BTC.D

The dataset includes daily open, high, low, and close values.

I used the daily closing value as the Bitcoin dominance percentage.

This file is located in the /data folder as BTC_D_dataset.csv.

2. Political Events Data (2020–2025)

A manually compiled list of major global political events such as elections, wars, conflicts, financial crises, and geopolitical shocks.

These events were taken from reliable public sources including international news outlets and Wikipedia’s year-by-year political timelines.

This dataset is saved as political_events_2020_2025.csv in the /data folder.

After loading both files, I merged them using the date column to create a unified dataset called btc_dominance_with_events.csv, which is also included in the /data folder.

Note: At first I planned to use CoinGecko and GDELT directly. In practice I ran into issues such as, CoinGecko’s free API does not provide a clean BTC dominance time series, and some historical pages returned 404 errors. Because of this I switched to TradingView’s BTC.D series (exported as CSV) and a manually compiled list of political events based on reliable public sources such as major news outlets and Wikipedia’s annual political summaries.


Plan and Methods

Collect and clean crypto and political event data.

Match event dates with Bitcoin dominance records.

Create visuals showing how dominance changes before and after major events.

Use correlation and hypothesis testing to see if instability raises Bitcoin dominance.

Later, try a small regression model to estimate dominance changes based on event frequency or sentiment.
Expected Result

I expect that during politically unstable times, Bitcoin dominance will rise because investors prefer a more stable digital asset. During calmer or optimistic periods, dominance may fall as people move to altcoins seeking higher returns.

Limitations

Political event data may not cover every country equally, and Bitcoin dominance is also affected by other factors such as ETF news or major exchange actions. I will mention these points in the final report.

### How to Run the Project

1. Install the required Python packages:

   pip install -r requirements.txt

2. Open the notebook `DSA_210_project.ipynb` in the `/notebooks` folder
   (for example in Google Colab or Jupyter).

3. Run all cells in order. This will:
   - load the datasets from `/data`
   - clean and merge them
   - create the BTC dominance plots
   - run the hypothesis test
   - save `btc_dominance_with_events.csv` into `/data`
  
I took assistance from AI during this project mainly for help with understanding errors, explaining certain Python methods, and improving the wording of my explanations.


