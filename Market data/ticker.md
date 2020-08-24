**URL** 

- `/public/ticker`

Get ticker for an instrument.



**Parameters** 

| Parameter       | Required | Type   | Enum | Description     |
| :-------------- | :------- | :----- | :--- | :-------------- |
| instrument_name | true     | string |      | Instrument name |



**Response**

| Name               | Type     | Description                                                  |
| :----------------- | :------- | :----------------------------------------------------------- |
| id                 | integer  | The id that was sent in the request                          |
| jsonrpc            | string   | The JSON-RPC version (2.0)                                   |
| usIn               | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut              | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff             | integer  | The number of microseconds that was spent handling the request                                                         |
| result             | *object* |                                                              |
| › ask_iv           | number   | (Only for option) implied volatility for best ask            |
| › best_ask_amount  | number   | It represents the requested order size of all best asks      |
| › best_ask_price   | number   | The current best ask price, `null` if there aren't any asks  |
| › best_bid_amount  | number   | It represents the requested order size of all best bids      |
| › best_bid_price   | number   | The current best bid price, `null` if there aren't any bids  |
| › bid_iv           | number   | (Only for option) implied volatility for best bid            |
| › current_funding  | number   | Current funding (perpetual only)                             |
| › delivery_price   | number   | The settlement price for the instrument. Only when `state = closed` |
| › funding_8h       | number   | Funding 8h (perpetual only)                                  |
| › greeks           | *object* |                                                              |
| ›  › delta         | number   | (Only for option) The delta value for the option             |
| ›  › gamma         | number   | (Only for option) The gamma value for the option             |
| ›  › rho           | number   | (Only for option) The rho value for the option               |
| ›  › theta         | number   | (Only for option) The theta value for the option             |
| ›  › vega          | number   | (Only for option) The vega value for the option              |
| › index_price      | number   | Current index price                                          |
| › instrument_name  | string   | Unique instrument identifier                                 |
| › interest_rate    | number   | Interest rate used in implied volatility calculations (options only) |
| › last_price       | number   | The price for the last trade                                 |
| › mark_iv          | number   | (Only for option) implied volatility for mark price          |
| › mark_price       | number   | The mark price for the instrument                            |
| › max_price        | number   | The maximum price for the future. Any buy orders you submit higher than this price, will be clamped to this maximum. |
| › min_price        | number   | The minimum price for the future. Any sell orders you submit lower than this price will be clamped to this minimum. |
| › open_interest    | number   | The total amount of outstanding contracts in the corresponding amount units. The minsize of futures and options is one contract.  |
| › settlement_price | number   | The settlement price for the instrument. Only when `state = open` |
| › state            | string   | The state of the order book. Possible values are `open` and `closed`. |
| › stats            | *object* |                                                              |
| ›  › high          | number   | highest price during 24h                                     |
| ›  › low           | number   | lowest price during 24h                                      |
| ›  › price_change  | number   | 24-hour price change expressed as a percentage, `null` if there weren't any trades |
| ›  › volume        | number   | volume during last 24h in base currency                      |
| › timestamp        | integer  | The timestamp (milliseconds since the Unix epoch)            |
| › underlying_index | number   | Name of the underlying future, or `index_price` (options only) |
| › underlying_price | number   | Underlying price for implied volatility calculations (options only) |

example:

```json
{
	"id": "13",
	"jsonrpc": "2.0",
	"usIn": 1597129255754,
	"usOut": 1597129255760,
	"usDiff": 6,
	"result": [{
		"best_ask_amount": "2",
		"best_ask_price": "11808",
		"best_bid_amount": "3",
		"best_bid_price": "11780",
		"instrument_name": "BTC-14AUG20",
		"last_price": "11794",
		"mark_price": "11792.284",
		"open_interest": "8",
		"state": "open",
		"stats": {
			"high": "12022",
			"low": "11794",
			"price_change": "-0.0186",
			"volume": "5"
		},
		"timestamp": "1597129254826",
		"underlying_price": "11756.9324"
	}]
}
```

