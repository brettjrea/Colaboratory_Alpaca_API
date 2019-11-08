# Jupyter Notebook with Alpaca Markets integration.

## Alpaca Markets
https://alpaca.markets/

Create account with Alpaca markets.

## Google Colaboratory
https://colab.research.google.com

### Create new Jupyter Notebook on Google Colab.


Install Alpacas Python Library.
```
!pip install alpaca-trade-api
```

Insert personal API KEY ID, SECRET KEY and ENDPOINT to connect to the REST API.
```
import alpaca_trade_api as alpaca 
api = alpaca.REST('API KEY ID', 'SECRET KEY', 'ENDPOINT')
```

Once connected you can see your positions with this command.
```
api.list_positions()
```

Or return a tabulated form of data for a ticker with this command.
```
api.get_barset('MSFT', 'day', limit=10).df
```

To visualize the data install MATPLOTLIB with
```
!pip install mpl_finance
```

And run the following to return a candlestick chart.
```
from mpl_finance import candlestick_ohlc
import matplotlib.pyplot as plt
import matplotlib.dates as mdates
from matplotlib.dates import MONDAY, DateFormatter, DayLocator, WeekdayLocator

df = api.get_barset('MSFT', 'day', limit=253).df['MSFT']
quotes = zip(mdates.date2num(df.index.to_pydatetime()),
             df.open, df.high, df.low, df.close)

fig, ax = plt.subplots(figsize=(20,10))
ax.xaxis_date()
ax.autoscale_view()
alldays = DayLocator()
ax.xaxis.set_minor_locator(alldays)
candlestick_ohlc(ax, quotes, width=0.5, colorup='g', colordown='r')
```


