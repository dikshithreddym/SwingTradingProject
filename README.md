
# Swing Trading Scanner (Pro)

An advanced, fully automated swing trading scanner for US (S&P 500) and Canadian (TSX) stocks. This project combines robust data scraping, technical analysis, sector momentum, and risk management to generate high-quality swing trade ideas with visual validation.

## Key Features

- **Automated Ticker & Sector Scraping**: Scrapes the latest S&P 500 and TSX tickers and sector mappings directly from Wikipedia.
- **Comprehensive Technical Indicators**: Calculates SMA (20/50/200), RSI, MACD, ATR, Bollinger Bands, Stochastics, ADX, CCI, AVWAP, and more for each stock.
- **Market & Sector Context**: Analyzes overall market regime (SPY) and sector ETF momentum to prioritize strong stocks in strong sectors.
- **Multiple Swing Strategies**:
    - **Breakout**: High-volume breakouts above 20-day highs with trend confirmation.
    - **Pullback**: Dips to rising 20 SMA in uptrends (20>50>200) with RSI reset.
    - **Mean Reversion**: Oversold bounces below lower Bollinger Band with Stochastics confirmation.
    - **Retest**: Pullbacks to recently broken resistance (base → breakout → retest).
- **Scoring Engine**: Ranks setups (0-100) by trend quality, sector strength, relative strength, setup quality, risk/reward, and momentum.
- **Risk Management**: Calculates dynamic stop-loss and target levels for each strategy, with position sizing based on account size and risk per trade.
- **Earnings Filter**: Excludes stocks with earnings in the next 7 days to avoid unpredictable volatility.
- **Visual Charting**: Generates multi-panel technical charts (price, volume, RSI, MACD, CCI) for top candidates and manual analysis.

## How It Works

1. **Import Libraries & Set Parameters**: Loads all required Python libraries and sets up analysis parameters (lookback period, moving averages, risk settings, etc).
2. **Fetch Tickers & Sectors**: Scrapes S&P 500 and TSX tickers and sector info from Wikipedia.
3. **Download Data**: Uses yfinance to fetch daily OHLCV data for all tickers.
4. **Calculate Indicators**: Adds a full suite of technical indicators to each stock's data.
5. **Sector & Market Analysis**: Assesses sector ETF and market index trends to provide context for each trade idea.
6. **Apply Strategies**: Flags stocks meeting breakout, pullback, mean reversion, or retest criteria.
7. **Score & Filter**: Ranks all candidates, applies risk/reward and liquidity filters, and removes stocks with upcoming earnings.
8. **Visualize**: Plots detailed technical charts for the best setups and allows manual charting for any ticker.

## Usage

1. Open `scrape.ipynb` in Jupyter or VS Code.
2. Run all cells in order. The scanner will:
     - Download and process the latest data
     - Display top trade candidates by strategy and score
     - Filter out risky earnings plays
     - Generate technical charts for the best setups
3. Use the manual charting cell at the end to analyze any ticker of interest.

## Requirements

- Python 3.8+
- Packages: `yfinance`, `pandas`, `numpy`, `matplotlib`, `requests` (install via pip if needed)

## Project Structure

- `scrape.ipynb` — Main notebook with all code, logic, and visualizations
- `README.md` — Project overview and instructions

## Notes

- The scanner is designed for educational and research purposes. Always validate trade ideas with your own due diligence.
- Data sources (Wikipedia, Yahoo Finance) may occasionally change format, requiring code updates.

## Example Output

The scanner outputs:
- Ranked tables of trade candidates by strategy (Pullback, Retest, Breakout, Mean Reversion)
- Risk/reward, stop, and target levels for each setup
- Multi-panel technical charts for top candidates

---
**Author:** [Your Name]  
**Last Updated:** January 2026
