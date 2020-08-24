**URL** 

- `/public/get_order_book`

Retrieves the order book, along with other market values for a given instrument.



**Parameters** 

| Parameter       | Required | Type   | Enum | Description                                                  |
| :-------------- | :------- | :----- | :--- | :----------------------------------------------------------- |
| instrument_name | true     | string |      | The instrument name for which to retrieve the order book, see `getinstruments` to obtain instrument names. |



**Response**

| Name               | Type                     | Description                                                  |
| :----------------- | :----------------------- | :----------------------------------------------------------- |
| id                 | integer                  | The id that was sent in the request                          |
| jsonrpc            | string                   | The JSON-RPC version (2.0)                                   |
| usIn               | integer                  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut              | integer                  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff             | integer                  | The number of microseconds that was spent handling the request                                                         |
| result             | *object*                 |                                                              |
| › ask_iv           | number                   | (Only for option) implied volatility for best ask            |
| › asks             | array of [price, amount] | List of asks                                                 |
| › best_ask_amount  | number                   | It represents the requested order size of all best asks      |
| › best_ask_price   | number                   | The current best ask price, `null` if there aren't any asks  |
| › best_bid_amount  | number                   | It represents the requested order size of all best bids      |
| › best_bid_price   | number                   | The current best bid price, `null` if there aren't any bids  |
| › bid_iv           | number                   | (Only for option) implied volatility for best bid            |
| › bids             | array of [price, amount] | List of bids                                                 |
| › current_funding  | number                   | Current funding (perpetual only)                             |
| › delivery_price   | number                   | The settlement price for the instrument. Only when `state = closed` |
| › funding_8h       | number                   | Funding 8h (perpetual only)                                  |
| › greeks           | *object*                 |                                                              |
| ›  › delta         | number                   | (Only for option) The delta value for the option             |
| ›  › gamma         | number                   | (Only for option) The gamma value for the option             |
| ›  › rho           | number                   | (Only for option) The rho value for the option               |
| ›  › theta         | number                   | (Only for option) The theta value for the option             |
| ›  › vega          | number                   | (Only for option) The vega value for the option              |
| › index_price      | number                   | Current index price                                          |
| › instrument_name  | string                   | Unique instrument identifier                                 |
| › interest_rate    | number                   | Interest rate used in implied volatility calculations (options only) |
| › last_price       | number                   | The price for the last trade                                 |
| › mark_iv          | number                   | (Only for option) implied volatility for mark price          |
| › mark_price       | number                   | The mark price for the instrument                            |
| › max_price        | number                   | The maximum price for the future. Any buy orders you submit higher than this price, will be clamped to this maximum. |
| › min_price        | number                   | The minimum price for the future. Any sell orders you submit lower than this price will be clamped to this minimum. |
| › open_interest    | number                   | The total amount of outstanding contracts in the corresponding amount units. The minsize of futures and options is one contract.  |
| › settlement_price | number                   | The settlement price for the instrument. Only when `state = open` |
| › state            | string                   | The state of the order book. Possible values are `open` and `closed`. |
| › stats            | *object*                 |                                                              |
| ›  › high          | number                   | highest price during 24h                                     |
| ›  › low           | number                   | lowest price during 24h                                      |
| ›  › price_change  | number                   | 24-hour price change expressed as a percentage, `null` if there weren't any trades |
| ›  › volume        | number                   | volume during last 24h in base currency                      |
| › timestamp        | integer                  | The timestamp (milliseconds since the Unix epoch)            |
| › underlying_index | number                   | Name of the underlying future, or `index_price` (options only) |
| › underlying_price | number                   | Underlying price for implied volatility calculations (options only) |

example:

```json
{
	"id": "42",
	"jsonrpc": "2.0",
	"usIn": 1597129272512,
	"usOut": 1597129272521,
	"usDiff": 9,
	"result": {
		"asks": [
			["1043.00", "40", "119.760", "0.910"],
			["1048.00", "40", "122.820", "0.824"],
			["1061.00", "40", "129.520", "0.811"]
		],
		"bids": [
			["862.00", "15", "48.050", "0.824"],
			["859.00", "15", "1.000", "0.910"],
			["856.00", "40", "40.170", "0.824"],
			["855.00", "55", "52.490", "0.811"],
			["853.00", "40", "1.000", "0.910"],
			["806.00", "500", "1.000", "0.811"],
			["796.00", "500", "1.000", "0.824"],
			["793.00", "500", "1.000", "0.910"],
			["224.00", "10", "1.000", "0.813"],
			["221.00", "10", "1.000", "0.823"],
			["220.00", "10", "1.000", "0.910"],
			["200.00", "100", "1.000", "0.813"],
			["197.00", "100", "1.000", "0.823"],
			["196.00", "100", "1.000", "0.910"],
			["121.00", "5", "1.000", "0.813"],
			["119.00", "10", "1.000", "0.823"]
		],
		"timestamp": "1597129272520",
		"instrument_name": "BTC-14AUG20-11000-C"
	}
}
```

