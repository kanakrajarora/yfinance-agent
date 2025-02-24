# Stock Analysis with LangGraph

This project demonstrates how to build a simple stock analysis workflow using LangGraph. It fetches historical stock data, performs technical analysis, and visualizes the results.
Name: Kanak Raj Arora
Email: kanakrajarora@gmail.com

## Overview

The application leverages LangGraph to create a structured workflow that:
1. Fetches stock price data using yfinance
2. Calculates technical indicators (moving averages and volatility)
3. Visualizes the stock trends with matplotlib

## Requirements

To run this project, you'll need the following packages:

```bash
langgraph
yfinance
matplotlib
pandas
pydantic
```

You can install them using pip:

```bash
pip install langgraph yfinance matplotlib pandas pydantic
```

## Project Structure

The project contains the following components:

- **State Management**: Using TypedDict and Pydantic for type safety
- **Node Functions**: Specialized functions that process and transform stock data
- **LangGraph Workflow**: A directed graph that orchestrates the execution flow

## Usage

To analyze a stock, simply run the script:

```bash
python code.ipynb
```

By default, the script analyzes Apple (AAPL) stock for the past month with daily intervals.

## Customization

You can easily modify the initial state in the `main()` function to analyze different stocks or time periods:

```python
state = {
    "ticker": "MSFT",  # Change to your preferred stock ticker
    "period": "3mo",   # Options: 1d, 5d, 1mo, 3mo, 6mo, 1y, 2y, 5y, 10y, ytd, max
    "interval": "1d",  # Options: 1m, 2m, 5m, 15m, 30m, 60m, 90m, 1h, 1d, 5d, 1wk, 1mo, 3mo
    "data": None
}
```

## How It Works

1. **Data Fetching**: The `fetch_stock_data` function retrieves historical stock data from Yahoo Finance.
2. **Analysis**: The `analyze_stock_data` function calculates a 10-day moving average and rolling volatility.
3. **Visualization**: The `plot_stock_data` function creates a chart showing the closing price and moving average.
4. **Workflow**: LangGraph orchestrates the flow between these components, handling data passing.

## Extending the Project

You can extend this project by:
- Adding more technical indicators
- Implementing prediction models
- Creating alerts based on specific patterns
- Expanding to analyze multiple stocks simultaneously
- Building a web interface for the results

## Troubleshooting

If you encounter the error `ValueError: Must provide state_schema or input and output`, make sure you've properly initialized the StateGraph with your state type.

If you see `AttributeError: object has no attribute 'invoke'`, check that you're using the correct method for your version of LangGraph (some versions use `run()` instead of `invoke()`).
