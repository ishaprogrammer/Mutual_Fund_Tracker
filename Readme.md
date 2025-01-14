# Mutual Fund Allocation Tracker with Trend Prediction

This project allows users to track changes in mutual fund allocations over a specified period. The tracker can display changes in quantities and market values of mutual funds, visualize trends, and predict future trends using machine learning. The tool also offers insights into top-performing funds, helping users make informed decisions about their investments.

## Features

- **Track Fund Changes**: View changes in mutual fund quantities and market values over a user-specified date range.
- **Trend Prediction**: Machine learning-based forecasting to predict whether a fund's allocation will increase or decrease in the future.
- **Fund Summary**: Aggregated fund information, including top 3 funds with the highest increase in quantity or market value.
- **Trend Visualization**: Line plots to show changes in quantity and market value for the selected funds over time.
- **Flexible User Inputs**: The user can specify which funds to track, the date range, and whether they want to see predictions and trend plots.

## Installation

You can use this tool directly in a Jupyter Notebook or Google Colab environment.

### Prerequisites

- Python 3.x
- Pandas
- Matplotlib
- scikit-learn
- Google Colab (if using)

Install the necessary libraries using the following commands:

```bash
pip install pandas
pip install matplotlib
pip install scikit-learn
```

### Setup

1. Clone this repository or upload the necessary `.xlsx` files to Google Drive if using Google Colab.
2. Mount your Google Drive to access the data files.

```python
from google.colab import drive
drive.mount('/content/drive')
```

3. Load your Excel data (`ZN250 - Monthly Portfolio November 2024.xlsx` and `ZN250 - Monthly Portfolio September 2024.xlsx`).

4. Run the Python script to start tracking fund changes and making predictions.

## Usage

Once you have the data loaded, the program will ask you to input the following:

- **Fund Names**: A list of mutual funds you want to track (comma-separated).
- **Date Range**: The number of months you'd like to look back (e.g., 3 months).
- **Trend Prediction**: Whether you want to see future trend predictions for the selected funds (yes/no).
- **Trend Plot**: Whether you'd like to see a plot of the fund's trends (yes/no).

The program will then show:
- The changes in quantity and market value for the selected funds.
- Machine learning-based trend prediction for whether the fund is expected to increase or decrease.
- A plot showing the trends over time, if requested.

### Example

```bash
Enter the fund names (comma-separated, e.g., 'Zerodha Midcap Fund, HDFC Large Cap'): ICICI Bank Limited
Enter the number of months to look back (e.g., '5' for last 5 months): 3
Do you want to see the future trend predictions for these funds? (yes/no): yes
Do you want to see the trend plot for ICICI Bank Limited? (yes/no): yes
```

Output Example:
```bash
Changes for ICICI Bank Limited (from 2024-10 to 2025-01):
Quantity Change: 20.5
Market Value Change: 12.3
Prediction for ICICI Bank Limited: The fund is predicted to increase in the future.
Trend Summary: Over the last 3 months, the fund has shown an increase in quantity.

Trend plot for ICICI Bank Limited:
(Shows the line plot for the fund's quantity changes over the selected date range.)
```

## Machine Learning Model

The trend prediction uses a simple linear regression model, which forecasts whether a fund's quantity will increase or decrease based on the past few months of data. It uses the `Quantity_change` as the target variable and `MonthNumber` (ordinal representation of months) as the independent feature.

## File Structure

- `nov_df`: DataFrame for November 2024 portfolio data.
- `sept_df`: DataFrame for September 2024 portfolio data.
- `track_mutual_fund_changes_with_prediction`: Function to process the data and show results based on user input.

## Future Enhancements

- **Advanced Forecasting Models**: Use time series models like ARIMA or LSTM for more accurate predictions.
- **Additional Fund Analysis**: Incorporate more advanced metrics for fund performance (e.g., risk, return).
- **User Interface**: Build a more user-friendly GUI or web interface.

## License

This project is open-source and available under the MIT License.

---
