# A Predictive Regression Analysis of Daily Citi Bike Demand in New York City

**Live Interactive Report:** [View the Final Knitted Model Analysis](https://phuongjanele.github.io/citibike-model/)

This repository contains a comprehensive data science pipeline developed to forecast daily city-wide ridership (`num_trips`) for the New York City Citi Bike network in 2014. By combining historical climate observations with structured calendar data, the predictive model isolates the primary environmental and societal levers that drive urban micro-mobility.

## Project Overview & Context

In a dense urban ecosystem like New York City, bike-share systems serve as a critical transit artery. However, managing Citibike logistics presents a chaotic operational puzzle: demand fluctuates wildly based on sudden weather deterrents, shifting seasons, and changing commuter routines. 

This project moves away from operational guesswork, utilizing statistical modeling to map human behavioral patterns against the elements. The core objective is to provide a reliable, data-driven forecasting framework that empowers transit operators to rebalance fleet inventory proactively *before* high-demand rush hours begin.

## Repository Structure

*   **`citibike_modeling.Rmd`**: The primary R Markdown pipeline containing all data preprocessing, feature engineering, model selection, cross-validation, and final evaluation loops.
*   **`trips_per_day.tsv`**: The underlying historical Citi Bike dataset containing daily aggregate trip counts and baseline tracking variables.
*   **`holiday_data.csv`**: A supplemental feature engineering dataset mapping specific dates and multi-day observation windows for major US public holidays.

## Methodology & Modeling Architecture

The model utilizes a rigorous development framework to guarantee structural stability and out-of-sample predictive power:

*   **Data Splitting Strategy:** To protect against localized overfitting, the data is partitioned into a strict **70% Training / 20% Validation / 10% Testing** split.
*   **Capturing Non-Linear Climate Comfort Zones:** Human behavior relative to temperature is non-linear; ridership drops off during freezing winters and oppressive summer heatwaves alike. The model implements a **4th-degree polynomial expansion** on maximum daily temperature to accurately capture this peak comfort threshold.
*   **Isolating Demand Deterrents:** Feature arrays account for immediate demand-killers like active precipitation, lingering snow depth on city streets, and behavioral shifts across weekends and public holidays.
*   **Optimization:** Best subset selection paired with 10-fold cross-validation was leveraged to identify the most parsimonious and predictive feature combinations.

## Performance & Key Findings

> ### Operational Diagnostic
> The final predictive regression model exhibits exceptional structural integrity and generalizability:
> *   **Test RMSE tracks within 5% of Validation RMSE**, confirming that the model has successfully captured universal behavioral trends rather than localized training noise.
> *   The model demonstrates highly reliable predictive accuracy, typically forecasting city-wide daily demand within a tight margin of **~3,200 trips**, making it fully viable for live logistical deployment.

## Getting Started & Replication

To replicate this analysis locally, ensure you have R and RStudio installed along with the `tidyverse` suite.



1. Clone this repository:
```bash
   git clone [https://github.com/phuongjanele/citibike-model.git](https://github.com/phuongjanele/citibike-model.git)
