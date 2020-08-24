**URL** 

- `/private/get_position`

Retrieve user position.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter       | Required | Type   | Enum | Description     |
| :-------------- | :------- | :----- | ---- | --------------- |
| instrument_name | true     | string |      | Instrument name |



**Response**

| **Name**                      | **Type** | **Description**                                              |
| :---------------------------- | :------- | ------------------------------------------------------------ |
| id                            | string   | The id that was sent in the request                          |
| jsonrpc                       | string   | The JSON-RPC version (2.0)                                   |
| usIn                          | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                         | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                        | integer  | The number of microseconds that was spent handling the request                                                         |
| result                        | object   |                                                              |
| › average_price               | string   | Average price of trades that built this position             |
| › average_price_usd           | string   | Only for options, average price in USDT                       |
| › delta                       | string   | Delta parameter                                              |
| › direction                   | string   | Direction: `buy`, `sell` or `zero`                           |
| › estimated_liquidation_price | string   | Floating profit or loss                                      |
| › floating_profit_loss_usd    | string   | Only for options, floating profit or loss in USDT             |
| › gamma                       | string   | Only for options, Gamma parameter                            |
| › index_price                 | string   | Current index price                                          |
| › initial_margin              | string   | Initial margin                                               |
| › instrument_name             | string   | Unique instrument identifier                                 |
| › kind                        | string   | Instrument kind, `"future"` or `"option"`                    |
| › leverage                    | integer  | Current available leverage for future position               |
| › maintenance_margin          | string   | Maintenance margin                                           |
| › mark_price                  | string   | Current mark price for position's instrument                 |
| › open_orders_margin          | string   | Open orders margin                                           |
| › realized_funding            | string   | Realized Funding in current session included in session realized profit or loss, only for positions of perpetual instruments |
| › realized_profit_loss        | string   | Realized profit or loss                                      |
| › settlement_price            | string   | Last settlement price for position's instrument 0 if instrument wasn't settled yet |
| › size                        | string   | Position size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › size_currency               | string   | Only for futures, position size in base currency             |
| › theta                       | string   | Only for options, Theta parameter                            |
| › total_profit_loss           | string   | Profit or loss from position                                 |
| › vega                        | string   | Only for options, Vega parameter                             |

example:

```json
{
	"id": "166",
	"jsonrpc": "2.0",
	"usIn": 1597128675858,
	"usOut": 1597128677822,
	"usDiff": 1964,
	"result": {
		"average_price": "12217",
		"delta": "0.01",
		"direction": "buy",
		"floating_profit_loss": "-0.037",
		"instrument_name": "BTC-25DEC20",
		"kind": "future",
		"mark_price": "12217.88",
		"realized_profit_loss": "0",
		"size": "1",
		"session_price": "12221.58",
		"vega": "0",
		"zero_margin_size": "0",
		"version": "42162"
	}
}
```

