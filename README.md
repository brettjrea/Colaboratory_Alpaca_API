# Colaboratory_Alpaca_API
## Jupyter Notebook With Alpaca Integration.

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

Or return a Tabulated form of the data with this command.
```
api.get_barset('MSFT', 'day', limit=10).df
```
