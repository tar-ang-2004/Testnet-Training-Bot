# Binance Futures Trading Bot

A comprehensive Python-based trading bot for Binance Futures Testnet with an interactive command-line interface. This bot provides a safe environment to test automated trading strategies without risking real funds.

## Features

### Core Trading Functions
- **Market Orders**: Execute instant buy/sell orders at current market price
- **Limit Orders**: Place orders at specific price levels
- **Stop-Limit Orders**: Set stop-loss and take-profit levels
- **OCO Orders**: One-Cancels-Other orders for advanced risk management
- **Position Management**: Track and manage open positions
- **Order Cancellation**: Cancel individual or all open orders

### Account Management
- Real-time account information and balance tracking
- Position monitoring with PnL display
- Open orders overview
- Available balance calculations
- Comprehensive account statistics

### Safety Features
- **Testnet-Only Operation**: All trading happens on Binance Testnet
- **Comprehensive Error Handling**: Robust error management for API failures
- **Input Validation**: Validates all user inputs before execution
- **Detailed Logging**: Complete audit trail of all operations
- **UTF-8 Encoding Support**: Windows-compatible logging without Unicode issues

### User Interface
- Interactive CLI menu system
- Color-coded output for better readability
- Step-by-step guidance for all operations
- Real-time status updates
- Easy-to-navigate menu structure

## Prerequisites

- Python 3.7 or higher
- Binance Testnet account
- API Key and Secret from Binance Testnet

## Installation

1. **Clone or download this repository**
   ```bash
   git clone <repository-url>
   cd paermaai
   ```

2. **Install required dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Get Binance Testnet API Credentials**
   - Visit [Binance Testnet](https://testnet.binancefuture.com/)
   - Create an account
   - Generate API Key and Secret Key
   - Save your credentials securely

## Configuration

### Setting Up API Credentials

Open the Jupyter notebook `binance_trading_bot.ipynb` and locate the API Credentials Setup cell:

```python
# Set your API credentials here
API_KEY = "your_testnet_api_key_here"
API_SECRET = "your_testnet_api_secret_here"
```

**Important**: Never commit your actual API keys to version control. Consider using environment variables for production deployments.

## Usage

### Running the Bot

1. **Open the Jupyter Notebook**
   ```bash
   jupyter notebook binance_trading_bot.ipynb
   ```

2. **Execute cells in order**:
   - Cell 1: Import required libraries
   - Cell 2: Load API credentials
   - Cell 3: Set up logging
   - Cell 4: Initialize the BinanceTradingBot class
   - Cell 5: Add bot methods
   - Cell 6-9: Add order and position management methods
   - Cell 10: Initialize CLI interface
   - Cell 11: Run bot methods
   - Cell 12: Start the CLI

3. **Start the Interactive CLI**
   - Run the "START THE TRADING BOT CLI" cell
   - Follow the on-screen menu prompts

### CLI Menu Options

```
MAIN MENU:
1.  Account Information       - View balance and account details
2.  Symbol Information        - Get price and trading info for any symbol
3.  Place Market Order        - Execute instant buy/sell orders
4.  Place Limit Order         - Set orders at specific prices
5.  Place Stop-Limit Order    - Configure stop-loss orders
6.  Place OCO Order           - Advanced order with multiple conditions
7.  View Positions            - See all open positions
8.  View Open Orders          - List all pending orders
9.  Cancel Order              - Cancel a specific order
10. Cancel All Orders         - Cancel all open orders
11. Close Position            - Close positions partially or fully
12. Account Balance           - Quick balance check
0.  Exit                      - Close the CLI
```

### Example Usage Scenarios

#### Viewing Account Information
```
Select option: 1
Getting account information...
Account Info Retrieved:
Total Wallet Balance: 10000.00 USDT
Available Balance: 10000.00 USDT
```

#### Placing a Market Order
```
Select option: 3
Enter symbol (e.g., BTCUSDT): BTCUSDT
Enter side (BUY/SELL): BUY
Enter quantity: 0.001
Placing market order: BUY 0.001 BTCUSDT
Market order placed successfully: 12345678
```

#### Viewing Positions
```
Select option: 7
Retrieved 2 active positions
Symbol: BTCUSDT | Position: 0.001 | Entry Price: $65000.00 | PnL: +$50.00
Symbol: ETHUSDT | Position: 0.01 | Entry Price: $3200.00 | PnL: -$5.00
```

## Project Structure

```
paermaai/
├── binance_trading_bot.ipynb   # Main Jupyter notebook with bot implementation
├── requirements.txt             # Python dependencies
├── README.md                    # This file
└── logs/                        # Trading logs directory
    └── trading_bot_*.log        # Daily log files
```

## Technical Architecture

### Class Structure

- **BinanceTradingBot**: Core bot class handling all Binance API interactions
  - Account management methods
  - Order placement and management
  - Position tracking
  - Error handling and logging

- **TradingBotCLI**: Command-line interface class
  - Menu system
  - User input handling
  - Output formatting
  - Interactive workflows

### API Integration

- Uses official `python-binance` library (v1.0.19)
- Connects to Binance Futures Testnet
- Implements proper error handling for API failures
- Respects rate limiting

### Logging System

- UTF-8 encoded file logging
- Separate log files per session
- Console output with color coding
- Detailed operation tracking
- Error and exception logging

## Dependencies

- **python-binance** (1.0.19): Official Binance API wrapper
- **requests** (2.31.0): HTTP library for API calls
- **python-decouple** (3.8): Configuration management
- **colorama** (0.4.6): Cross-platform colored terminal output

## Safety & Best Practices

### Important Reminders

1. **TESTNET ONLY**: This bot is configured for Binance Testnet. No real money is involved.

2. **Start Small**: When adapting for live trading, always start with minimal amounts.

3. **Risk Management**: 
   - Always set stop-loss orders
   - Never risk more than you can afford to lose
   - Diversify your positions
   - Monitor positions regularly

4. **API Security**:
   - Never share your API keys
   - Use API keys with minimal required permissions
   - Regularly rotate your API keys
   - Enable IP whitelist restrictions

5. **Monitor Regularly**: Check your positions and orders frequently

6. **Test Thoroughly**: Test all functions on testnet before considering live trading

## Troubleshooting

### Common Issues

**Issue**: `UnicodeEncodeError` when logging
- **Solution**: The logging system has been updated with UTF-8 encoding. Ensure you're running the latest version.

**Issue**: API connection errors
- **Solution**: Verify your API credentials are correct and you're connected to the internet.

**Issue**: `Bot not initialized` error
- **Solution**: Run the API credentials cell and bot initialization cell before starting the CLI.

**Issue**: Order placement fails
- **Solution**: Check that you have sufficient balance and the symbol format is correct (e.g., 'BTCUSDT').

### Debug Mode

To enable detailed logging, check the log files in the `logs/` directory:
```bash
cat logs/trading_bot_YYYYMMDD_HHMMSS.log
```

## Future Enhancements

### Planned Features
- TWAP (Time-Weighted Average Price) orders
- Grid trading strategy
- Advanced risk management tools
- Position size calculators
- Daily profit/loss reports
- Webhook notifications
- Multi-symbol trading
- Strategy backtesting

### Contributing
Feel free to fork this project and submit pull requests for improvements or bug fixes.

## Disclaimer

**IMPORTANT LEGAL DISCLAIMER**

This software is provided for educational and testing purposes only. 

- This bot is configured for Binance TESTNET only - no real money is involved
- The authors are not responsible for any financial losses incurred from using this software
- Cryptocurrency trading carries significant risk
- Past performance does not guarantee future results
- Always do your own research before trading
- Never invest more than you can afford to lose
- This is not financial advice

By using this software, you acknowledge that you understand these risks and accept full responsibility for your trading decisions.

## License

This project is open source and available for educational purposes.

## Support

For issues, questions, or contributions:
- Open an issue in the repository
- Check existing documentation
- Review the code comments in the notebook

## Acknowledgments

- Built with the official Binance API
- Uses python-binance library by Sam McHardy
- Inspired by the cryptocurrency trading community