# Forex_Api_Python

**Last Updated**: 2024-11-06 (Version 3)

This Forex API library offers a robust solution for integrating forex market data into your applications. With real-time currency rates, historical information, and technical analysis tools, it caters to a wide range of financial data needs.

### Features

- Over 2,000 currency pairs supported
- Live updates every 10 seconds
- Comprehensive historical records spanning 25 years
- Built-in tools for technical indicators and moving averages
- Global economic calendar with detailed event tracking

## System Requirements

- Python version 3.13.0 or higher
- An active API key from [ForexRatesAPI](https://forexratesapi.com/documentation/)

## Installation Steps

Download the repository and install the required dependencies using `pip`:

```bash
git clone https://github.com/forexratesapi619/Forex_Api_Python.git
cd Forex_Api_Python
pip install -r requirements.txt
```

## How to Get Started

### API Key Setup
1. Register on the [ForexRatesAPI](https://forexratesapi.com/register/) portal to obtain your API key.
2. Provide the API key while initializing the `ForexRate` class in your Python code.

```python
from forex_rate import ForexRate

# Configure the API client
forex_api = ForexRate(api_key='YOUR_API_KEY')

# Fetch live currency rates
latest_price = forex_api.get_latest_price("GBP/CHF")
print("Latest price for GBP/CHF:", latest_price)
```

## API Output Structure
All responses are returned in JSON format. Below is a sample response for a currency rate query:

```json
{
  "status": true,
  "code": 200,
  "msg": "Request Successful",
  "data": [
    {
      "id": "41",
      "open": "1.11997",
      "high": "1.12864",
      "low": "1.12201",
      "close": "1.12425",
      "ask": "1.12447",
      "bid": "1.12403",
      "spread": "4.4",
      "change": "+0.00428",
      "percent_change": "+0.38%",
      "timestamp": "1730874177",
      "symbol": "GBP/CHF",
      "datetime": "2024-11-06 06:22:57"
    }
  ],
  "meta": {
    "server_time": "2024-11-06 06:23:41 UTC",
    "credits_used": 1
  }
}
```

## Key Functionalities

1. **Retrieve Supported Symbols**
   
   Obtain a list of available forex and crypto trading pairs:
   
   ```python
   symbols = forex_api.get_symbols_list()
   ```

2. **Fetch Latest Rates**
   
   Get the current exchange rates for specific pairs:
   
   ```python
   latest_price = forex_api.get_latest_price(["EUR/USD", "USD/JPY"])
   ```

3. **Currency Conversion**
   
   Perform conversions between currencies:
   
   ```python
   result = forex_api.get_converter(200, 'EUR', 'USD')
   print(result)
   ```

4. **Currency Information**
   
   Access detailed information about a currency:
   
   ```python
   profile = forex_api.get_profile('EUR')
   ```

5. **Base Currency Quotes**
   
   Retrieve all rates relative to a base currency:
   
   ```python
   base_prices = forex_api.get_base_prices('USD')
   ```

6. **Historical Data**
   
   Access past rates for selected currencies over a specified timeframe:
   
   ```python
   history = forex_api.get_history({
       'symbol': 'EUR/USD',
       'period': '1d',
       'from': '2024-10-01',
       'to': '2024-10-31'
   })
   ```

7. **Technical Analysis Tools**
   
   Leverage built-in tools for moving averages, pivot points, and more:
   
   ```python
   ma = forex_api.get_moving_averages('EUR/USD', '1d')
   ```

8. **Economic Calendar**
   
   Stay updated with upcoming economic events:
   
   ```python
   events = forex_api.get_economy_calendar(from_date='2024-11-01', to_date='2024-11-05')
   ```

9. **Search Functionality**
   
   Locate forex symbols based on keywords:
   
   ```python
   search_results = forex_api.get_search_query('BTC')
   ```

## Additional Resources

For real-time streaming and advanced features, check out the WebSocket API options available with this library.

## Support

Need help? Reach out via [live chat](https://forexratesapi.com/contact/) or refer to the documentation provided on the official site.

## License

This project is distributed under the MIT License. See the LICENSE file for further details.

