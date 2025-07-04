# Stock Prediction App

A comprehensive web application for stock market analysis and prediction using machine learning. This application provides real-time market data, stock predictions using Random Forest regression, and explainable AI insights powered by SHAP (SHapley Additive exPlanations).

## 🚀 Features

- **Real-time Market Data**: Track top gainers, losers, most active stocks, and trending tickers
- **Stock Price Prediction**: ML-powered predictions using Random Forest regression
- **Explainable AI**: SHAP-based explanations for model predictions
- **Technical Indicators**: RSI, MACD, and Moving Averages analysis
- **Multi-Market Support**: US and Indian stock markets
- **Interactive Dashboard**: Modern web interface with responsive design
- **Portfolio Management**: Track and manage your stock portfolio
- **Watchlist**: Monitor your favorite stocks
- **Market News**: Stay updated with latest market trends
- **Stock of the Day**: AI-recommended stock picks

## 🛠️ Technology Stack

### Backend
- **Python 3.7+**
- **Flask**: Web framework
- **yfinance**: Yahoo Finance API for stock data
- **scikit-learn**: Machine learning models
- **Prophet**: Time series forecasting
- **SHAP**: Model explainability
- **pandas**: Data manipulation
- **numpy**: Numerical computing

### Frontend
- **HTML5**: Structure and markup
- **CSS3**: Styling and responsive design
- **JavaScript (ES6+)**: Interactive functionality
- **Chart.js**: Data visualization
- **Bootstrap**: UI components (if used)

## 📋 Prerequisites

- Python 3.7 or higher
- pip (Python package installer)
- Modern web browser (Chrome, Firefox, Safari, Edge)

## 🔧 Installation

### 1. Clone the Repository
```bash
git clone https://github.com/JEEVITHRAM72/Stock-Price-Prediction-AI.git
cd stock-prediction-app
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

## 🚀 Running the Application

### 1. Start the Flask Server
```bash
python app.py
```

### 2. Access the Application
Open your web browser and navigate to:
```
http://localhost:5000
```

## 📁 Project Structure

```
stock-prediction-app/
│
├── app.py                 # Main Flask application
├── README.md             # Project documentation
│
├── templates/            # HTML templates
│   ├── index.html        # Main dashboard
│
├── static/               # Static files
│   ├── css/
│   │   └── style.css     # Main stylesheet
│   ├── js/
│   │   ├── main.js       # Main JavaScript
│
```

## 🔌 API Endpoints

### Market Data
- `GET /market-data` - Fetch real-time market data
- `GET /stock-of-the-day` - Get AI-recommended stock

### Stock Prediction
- `POST /predict` - Generate stock price predictions
  ```json
  {
    "symbol": "AAPL"
  }
  ```

### Pages
- `GET /` - Main dashboard
- `GET /market-news` - Market news page
- `GET /watchlist` - Watchlist page
- `GET /portfolio` - Portfolio page

## 📊 Supported Stock Symbols

### US Stocks
- AAPL, MSFT, GOOG, AMZN, TSLA, META, NVDA, AMD, INTC

### Indian Stocks (NSE)
- RELIANCE.NS, TCS.NS, HDFCBANK.NS, INFY.NS, ICICIBANK.NS
- HINDUNILVR.NS, BHARTIARTL.NS, ITC.NS, KOTAKBANK.NS, LT.NS

*Note: For Indian stocks, you can use either format (e.g., "RELIANCE" or "RELIANCE.NS")*

## 🧠 Machine Learning Features

### Technical Indicators
- **SMA (Simple Moving Average)**: 20-day and 50-day periods
- **RSI (Relative Strength Index)**: Momentum oscillator
- **MACD (Moving Average Convergence Divergence)**: Trend-following indicator

### Model Features
- **Random Forest Regression**: Primary prediction model
- **Feature Engineering**: Technical indicators and price data
- **SHAP Explanations**: Understand model decisions
- **Real-time Predictions**: Latest market data integration

## 🎯 Usage Examples

### Making a Prediction
```javascript
// Frontend JavaScript example
fetch('/predict', {
    method: 'POST',
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify({
        symbol: 'AAPL'
    }),
})
.then(response => response.json())
.then(data => {
    console.log('Prediction:', data.predicted_price);
    console.log('Current Price:', data.current_price);
    console.log('Buy Price:', data.buy_price);
    console.log('Sell Price:', data.sell_price);
});
```

### Response Format
```json
{
    "symbol": "AAPL",
    "current_price": 150.25,
    "predicted_price": 152.30,
    "buy_price": 149.25,
    "sell_price": 155.35,
    "price_change": 2.05,
    "price_change_percent": 1.36,
    "explanation": {
        "feature_importance": {...},
        "detailed_explanations": [...]
    },
    "historical_data": [...],
    "dates": [...],
    "last_updated": "2024-01-15 10:30:00"
}
```

## 🔍 Troubleshooting

### Common Issues

1. **Module Not Found Error**
   ```bash
   pip install -r requirements.txt
   ```

2. **Port Already in Use**
   ```bash
   # Change port in app.py
   app.run(host='0.0.0.0', port=5001, debug=True)
   ```

3. **Stock Symbol Not Found**
   - Verify the stock symbol is correct
   - For Indian stocks, try adding ".NS" suffix
   - Check if the stock is actively traded

4. **SHAP Installation Issues**
   ```bash
   pip install shap --no-cache-dir
   ```

### Debug Mode
Enable detailed logging by setting debug mode:
```python
import logging
logging.basicConfig(level=logging.DEBUG)
```

## 📈 Performance Optimization

- **Data Caching**: Implement Redis for market data caching
- **Database Integration**: Use PostgreSQL/MySQL for historical data
- **Async Processing**: Use Celery for background tasks
- **CDN**: Serve static files via CDN for better performance

## 🔒 Security Considerations

- **API Rate Limiting**: Implement rate limiting for API endpoints
- **Input Validation**: Validate all user inputs
- **CORS Configuration**: Configure CORS for production
- **Environment Variables**: Use environment variables for sensitive data

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Yahoo Finance** for providing stock market data
- **SHAP** library for explainable AI capabilities
- **scikit-learn** for machine learning algorithms
- **Flask** community for the excellent web framework

## 🔄 Version History

- **v1.0.0** - Initial release with basic prediction functionality
- **v1.1.0** - Added SHAP explanations and Indian stock support
- **v1.2.0** - Enhanced UI and portfolio management features

---

Disclaimer: This application is for educational and informational purposes only. It should not be considered as financial advice. Always consult with a qualified financial advisor before making investment decisions.
