# yahoo_fin
Scrape stock price history from new (Spring 2017) Yahoo Finance layout

Full documentation is available on my website, here: http://theautomatic.net/yahoo_fin-documentation/.

If you're familiar with the "get_data_yahoo" method in pandas.io.data, this package's initial purpose was to serve as an updated replacement
based off Yahoo Finance's change in layout and its API (Spring 2017).  Since then, the package has been developed to scrape stock fundamentals data, ticker symbols from popular exchanges, (including S&P 500, NASDAQ, Dow Jones, and NYSE), balance sheets, income statements, cash flows, data on holders and analysts, and additional data such as beta / dividend information / 1 yr est. etc.  Additionally, it contains a module for scraping options data.

The package contains two modules: stock_info and options.

Download using pip:

```batch
pip install yahoo_fin
```

Examples:

```python
from yahoo_fin.stock_info import get_data, tickers_sp500, tickers_nasdaq, tickers_other, get_quote_table

""" pull historical data for Netflix (NFLX) """
nflx = get_data("NFLX")

""" pull data for Apple (AAPL) """
"""case sensitivity does not matter"""
aapl = get_data("aapl")

""" get list of all stocks currently traded
    on NASDAQ exchange """
nasdaq_ticker_list = tickers_nasdaq()

""" get list of all stocks currently in the S&P 500 """
sp500_ticker_list = tickers_sp500()

""" get other tickers not in NASDAQ (based off nasdaq.com)"""
other_tickers = tickers_other()

""" get information on stock from quote page """
info = get_quote_table("amzn")

```
