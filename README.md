# Price Forecasting Analysis

## Overview
This project performs comprehensive time series analysis and forecasting on historical monthly price data spanning from 2005 to 2025. The analysis includes data cleaning, exploratory data analysis (EDA), outlier detection, and implementation of multiple forecasting models.

## Dataset
- **Time Period**: January 2005 - September 2025
- **Total Observations**: 249 monthly data points
- **Features**: Date and average monthly price
- **Data Quality**: 
  - No missing values
  - 7 outliers detected using IQR method
  - 4 periods with >30% price change identified

## Project Structure
```
price_forecasting_project/
├── price_forecasting.ipynb    # Main Jupyter notebook with complete analysis
├── price_data.csv            # Source dataset
└── README.md                 # This file
```

## Analysis Components

### 1. Data Loading and Preprocessing
- Data loaded from CSV file
- Date column converted to datetime format
- Data sorted chronologically
- Index set to date column for time series analysis

### 2. Exploratory Data Analysis (EDA)

#### Statistical Summary
| Metric | Value |
|--------|-------|
| Count | 249 |
| Mean | 7918.89 |
| Std Dev | 2804.99 |
| Min | 3500.00 |
| 25th Percentile | 6123.00 |
| Median | 7250.00 |
| 75th Percentile | 9783.00 |
| Max | 16163.00 |

#### Key Features
- No missing values in the dataset
- No duplicate dates
- Clear upward trend over the 20-year period
- Several notable price spikes identified

### 3. Outlier Detection

#### IQR Method
- **Outliers Detected**: 7
- **Upper Bound**: 15,273
- **Notable Outliers**:
  - December 2023: 16,163
  - April-May 2024: 15,863
  - July 2025: 16,000

#### Z-Score Method
- **Outliers Detected**: 0 (using |z-score| > 3 threshold)
- Indicates that extreme values are not statistical outliers when considering normal distribution

### 4. Anomaly Detection

Identified 4 periods with significant price changes (>30%):

| Date | Price | Change % |
|------|-------|----------|
| May 2006 | 6,000 | +71.43% |
| November 2013 | 11,016 | +42.25% |
| June 2021 | 5,070 | -53.33% |
| December 2023 | 16,163 | +92.42% |

### 5. Data Visualization

The project includes:
- **Historical Price Trends**: Line plot showing the complete price history
- **Outlier Visualization**: Box plot highlighting detected outliers and distribution

## Data Quality Observations

### Strengths
✅ Complete dataset with no missing values  
✅ Regular monthly intervals  
✅ 20+ years of historical data  
✅ Clear temporal patterns

### Considerations
⚠️ Recent high volatility (2023-2025)  
⚠️ Significant price movements requiring investigation  
⚠️ Potential structural breaks in the time series

## Key Insights

1. **Long-term Trend**: Overall upward trend from 2005 to 2025
2. **Volatility**: Increased price volatility in recent years
3. **Price Range**: Prices have ranged from 3,500 to 16,163 over the period
4. **Growth Pattern**: Non-linear growth with periods of rapid increase

## Technical Requirements

### Dependencies
```python
pandas >= 2.2.2
numpy >= 1.26.4
matplotlib >= 3.8.4
seaborn >= 0.13.2
scikit-learn >= 1.4.2
scipy >= 1.13.1
```

### Installation
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
```

## Usage

1. **Clone the repository**:
```bash
git clone <repository-url>
cd price_forecasting_project
```

2. **Install dependencies**:
```bash
pip install -r requirements.txt
```

3. **Run the Jupyter notebook**:
```bash
jupyter notebook price_forecasting.ipynb
```

## Future Work

Planned enhancements include:
- [ ] Implementation of ARIMA/SARIMA models
- [ ] Prophet forecasting model
- [ ] LSTM neural network for time series prediction
- [ ] Cross-validation and model comparison
- [ ] Feature engineering (lagged variables, rolling statistics)
- [ ] Seasonality decomposition
- [ ] Forecast evaluation metrics (MAE, RMSE, MAPE)

## Data Cleaning Notes

### IQR Method Analysis
- **Q1**: 6,123
- **Q3**: 9,783
- **IQR**: 3,660
- **Lower Bound**: 633
- **Upper Bound**: 15,273

Outliers beyond the upper bound represent significant market events or data anomalies that warrant further investigation.

## Visualization Features

All visualizations use:
- High-resolution figures (15x6 inches)
- Professional color schemes
- Clear labeling and titles
- Grid lines for readability
- Seaborn styling for enhanced aesthetics

## Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is available for educational and research purposes.

## Contact

For questions or feedback, please open an issue in the repository.

---

*Last Updated: 2025*
