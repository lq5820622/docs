**URL** 

- `/public/get_instruments`

Retrieves available trading instruments. This method can be used to see which instruments are available for trading, or which instruments have existed historically.



**Parameters** 

| Parameter | Required | Type    | Enum                       | Description                                                  |
| :-------- | :------- | :------ | :------------------------- | :----------------------------------------------------------- |
| currency  | true     | string  | `BTC` `ETH` `MARGIN`       | The currency symbol                                          |
| kind      | false    | string  | `future` `option` `margin` | Instrument kind, if not provided instruments of all kinds are considered |
| expired   | false    | boolean |                            | Set to true to show expired instruments instead of active ones. |



**Response**

| Name                   | Type              | Description                                                  |
| :--------------------- | :---------------- | :----------------------------------------------------------- |
| id                     | integer           | The id that was sent in the request                          |
| jsonrpc                | string            | The JSON-RPC version (2.0)                                   |
| usIn                   | integer           | The timestamp when the requests was received (microseconds since the Unix epoch) |
| usOut                  | integer           | The timestamp when the response was sent (microseconds since the Unix epoch) |
| usDiff                 | integer           | The number of microseconds that was spent handling the request |
| result                 | array of *object* |                                                              |
| › base_currency        | string            | The underlying currency being traded.                        |
| › contract_size        | integer           | Contract size for instrument                                 |
| › creation_timestamp   | integer           | The time when the instrument was first created (milliseconds) |
| › expiration_timestamp | integer           | The time when the instrument will expire (milliseconds)      |
| › instrument_name      | string            | Unique instrument identifier                                 |
| › is_active            | boolean           | Indicates if the instrument can currently be traded.         |
| › kind                 | string            | Instrument kind, `"future"` or `"option"` or `margin`        |
| › leverage             | integer           | Maximal leverage for instrument, for futures only            |
| › maker_commission     | number            | Maker commission for instrument                              |
| › min_trade_amount     | number            | Minimum amount for trading. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.) |
| › option_type          | string            | The option type (only for options)                           |
| › quote_currency       | string            | The currency in which the instrument prices are quoted.      |
| › settlement_period    | string            | The settlement period.                                       |
| › strike               | number            | The strike value. (only for options)                         |
| › taker_commission     | number            | Taker commission for instrument                              |
| › tick_size            | number            | specifies minimal price change and, as follows, the number of decimal places for instrument prices |
| › instr_multiple       | number            | Contract multiplier                                               |

example:

```json
{
	"id": "23",
	"jsonrpc": "2.0",
	"usIn": 1597129154439,
	"usOut": 1597129154502,
	"usDiff": 63,
	"result": [{
		"base_currency": "USDT",
		"contract_size": "1",
		"creation_timestamp": "1596712745291",
		"expiration_timestamp": "1597392000000",
		"instrument_name": "BTC-14AUG20",
		"is_active": true,
		"kind": "future",
		"leverage": 0,
		"maker_commission": "0.02",
		"min_trade_amount": "1",
		"option_type": "init",
		"quote_currency": "USDT",
		"settlement_period": "week",
		"strike": "0",
		"taker_commission": "0.05",
		"tick_size": "1",
		"instr_multiple": "0.01"
	}, {
		"base_currency": "USDT",
		"contract_size": "1",
		"creation_timestamp": "1596784607906",
		"expiration_timestamp": "1597996800000",
		"instrument_name": "BTC-21AUG20",
		"is_active": true,
		"kind": "future",
		"leverage": 0,
		"maker_commission": "0.02",
		"min_trade_amount": "1",
		"option_type": "init",
		"quote_currency": "USDT",
		"settlement_period": "week",
		"strike": "0",
		"taker_commission": "0.05",
		"tick_size": "1",
		"instr_multiple": "0.01"
	}, {
		"base_currency": "USDT",
		"contract_size": "1",
		"creation_timestamp": "1596712747692",
		"expiration_timestamp": "1601020800000",
		"instrument_name": "BTC-25SEP20",
		"is_active": true,
		"kind": "future",
		"leverage": 0,
		"maker_commission": "0.02",
		"min_trade_amount": "1",
		"option_type": "init",
		"quote_currency": "USDT",
		"settlement_period": "month",
		"strike": "0",
		"taker_commission": "0.05",
		"tick_size": "1",
		"instr_multiple": "0.01"
	}, {
		"base_currency": "USDT",
		"contract_size": "1",
		"creation_timestamp": "1596712749898",
		"expiration_timestamp": "1608883200000",
		"instrument_name": "BTC-25DEC20",
		"is_active": true,
		"kind": "future",
		"leverage": 0,
		"maker_commission": "0.02",
		"min_trade_amount": "1",
		"option_type": "init",
		"quote_currency": "USDT",
		"settlement_period": "season",
		"strike": "0",
		"taker_commission": "0.05",
		"tick_size": "1",
		"instr_multiple": "0.01"
	}]
}
```

