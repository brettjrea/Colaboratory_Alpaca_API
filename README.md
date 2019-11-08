# Colaboratory_Alpaca_API
## Jupyter Notebook With Alpaca Integration.

```
!pip install alpaca-trade-api
```

```
import alpaca_trade_api as alpaca 
api = alpaca.REST('API KEY ID', 'SECRET KEY', 'ENDPOINT')
```

```
api.list_positions()
```

```
api.get_barset('MSFT', 'day', limit=10).df
```
