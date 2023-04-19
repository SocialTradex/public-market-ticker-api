## Table of Contents
- [General Information](#general-information)
- [Spot Ticker Endpoints](#spot-ticker-endpoints)
- [Derivatives Ticker Endpoints](#derivatives-ticker-endpoints) 

# Public Ticker API Documentation

## General Information
- Base endpoint for ticker api : ``https://api.socialtradex.com/public-api/``
- All date and timestamp items are given in milliseconds based on UTC timezone
- All endpoints return either a **JSON object** or **Array**

## Spot Ticker Endpoints

### Endpoints
- #### Summary
> Endpoint: ``GET:{apiBase}/spot/summary``
> 
> Example Response:
> ```
> [
>   {
>     "trading_pairs": "BTC_USDT",
>     "base_currency": "BTC",
>     "quote_currency": "USDT",
>     "last_price": 22344.07,
>     "lowest_ask": 22344.11,
>     "highest_bid": 22344.03,
>     "base_volume": 199556.17229,
>     "quote_volume": 4458982517.06026,
>     "price_change_percent_24h": -0.157,
>     "highest_price_24h": 22498.99,
>     "lowest_price_24h": 22147
>   },{...}
> ]
> ```

- #### List Assets
> Endpoint: ``GET:{apiBase}/spot/assets``
>
> Example Response:
> ```
> {
>    "BTC": {
>       "name": "Bitcoin",
>       "unified_cryptoasset_id": 352,
>       "can_withdraw": true,
>       "can_deposit": true,
>       "min_withdraw": 0.0000086,
>       "max_withdraw": 10000000000,
>       "maker_fee": 0.01,
>       "taker_fee": 0.01
>    },{...}
> }
> ```

- #### Spot Ticker
> Endpoint: ``GET:{apiBase}/spot/ticker``
>
> Example Response:
> ```
> {
>    "BTC_USDT": {
>      "base_id": 352,
>      "quote_id": 520,
>      "last_price": 22351.6,
>      "base_volume": 212205.33511,
>      "quote_volume": 4742659671.535437,
>      "isFrozen": 0
>    }
> }
> ```


- #### Orderbook Depth
> Endpoint: ``GET:{apiBase}/spot/orderbook/{symbol}``
> 
> Symbol Example: ``BTC_USDT``
>
> Example Response:
> ```
> {
>    "timestamp": 1677917419851,
>    "asks": [
>      [
>        "22352.48000000",
>        "0.00145000"
>      ]
>    ],
>    "bids": [
>      [
>        "22352.26000000",
>        "0.01446000"
>      ]
>    ]
>    }
> }
> ```

- #### Recent Trades
> Endpoint: ``GET:{apiBase}/spot/trades/{symbol}``
>
> Symbol Example: ``BTC_USDT``
>
> Example Response:
> ```
> [
>   {
>     "trade_id": 2000017251,
>     "price": 22351.43,
>     "base_volume": 0.00045,
>     "quote_volume": 10.0581435,
>     "timestamp": 1677917338795,
>     "type": "buy" // ["buy","sell"]
>   },{...}
> ]
> ```

---

## Derivatives Ticker Endpoints
### Endpoints

- #### List of derivative contracts
> Endpoint: ``GET:{apiBase}/derivatives/contracts``
>
> Example Response:
> ```
> [
>   {
>     "ticker_id": "BTCUSDT_PERPETUAL",
>     "base_currency": "BTC",
>     "quote_currency": "USDT",
>     "last_price": 22333.7,
>     "base_volume": 307229.99,
>     "quote_volume": 6858986772.47,
>     "bid": 22333.7,
>     "ask": 22333.8,
>     "high": 22495.2,
>     "low": 22120.1,
>     "product_type": "Perpetual",
>     "open_interest": 0,
>     "open_interest_usd": 0,
>     "index_price": 22345.2586017,
>     "funding_rate": 0.00003422,
>     "next_funding_rate_timestamp": 1677945600000,
>     "maker_fee": 0.0002,
>     "taker_fee": 0.0004
>   },{...}
> ]
> ```

- #### Derivatives Orderbook
> Endpoint: ``GET:{apiBase}/derivatives/orderbook/{contractTickerId}``
>
> Ticker ID Example: ``BTCUSDT_PERPETUAL``
>
> Example Response:
> ```
> {
>   "ticker_id": "BTCUSDT_PERPETUAL",
>   "timestamp": 1677932366645,
>   "bids":[
>     [
>       "22344.90",
>       "39.161"
>     ],[...]
>   ],
>   "asks":[
>     [
>       "22345.00",
>       "14.851"
>     ],[...]
>   ]
> }
> ```
