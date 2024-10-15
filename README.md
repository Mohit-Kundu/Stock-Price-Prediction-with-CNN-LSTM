# CNN-LSTM Stock Price Prediction

## Overview
This project is part of a larger **Automated Stock Forecasting Pipeline** built with **AWS** and **Apache Airflow**. The goal is to predict stock prices using a hybrid **CNN-LSTM model**, leveraging historical stock data. The model forecasts the next "Close" price based on features such as Open, High, Low, Close, Volume, and Adjusted Close.

The entire pipeline automates the process of scraping, storing, processing, and visualizing stock data, streamlining the decision-making process for stock trading or analysis.

## Project Pipeline Overview

1. **Data Collection**:
   - **Scraped Stock Data**: Historical stock data is scraped using the **Yahoo Finance API** via **Apache Airflow** DAGs.
   - **Storage**: The scraped data is stored in **AWS S3 buckets** for easy access and long-term storage.

2. **ETL Pipeline**:
   - Built an ETL (Extract, Transform, Load) pipeline using **AWS Glue** to process and prepare the stock data for analysis.

3. **Model Training**:
   - The **CNN-LSTM model** is trained on **Amazon SageMaker**, leveraging historical stock data to forecast future stock prices.
   - Achieved **93% forecasting accuracy**, demonstrating the effectiveness of the model.

4. **Visualization**:
   - **AWS QuickSight** is used to create visualizations of the stock predictions, helping streamline decision-making for stakeholders.

## Feature Selection

The following features are used to train the model:
- `Open`
- `High`
- `Low`
- `Close`
- `Volume`
- `Adjusted Close`

## Data Preprocessing
- **Standardization**: The data is scaled using `StandardScaler` to ensure all features have a uniform scale.
- **Sequence Preparation**: The data is split into sequences of 10 time steps, with the model predicting the `Close` price for the next time step.

## CNN-LSTM Model

The model architecture combines the strengths of:
- **Convolutional Neural Networks (CNN)**: To capture short-term patterns within the sequences.
- **Long Short-Term Memory (LSTM)**: To capture long-term dependencies in time-series data.

### Model Training and Evaluation
- The data is split into an 80% training set and a 20% test set.
- The model is evaluated based on its ability to predict future stock prices, achieving **93% accuracy** in forecasting.

## How to Run the Project

### Prerequisites
Make sure to install the following libraries:

```bash
pip install pandas numpy yfinance scikit-learn tensorflow matplotlib
