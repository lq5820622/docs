## user.orders.{instrument_name}.raw

Get notifications about changes in user's orders for given instrument.

 This is a private subscription; subscribing is only possible when authenticated.

### Channel Parameters

| Parameter       | Required | Type   | Enum | Description     |
| :-------------- | :------- | :----- | :--- | :-------------- |
| instrument_name | true     | string |      | Instrument name |

### Response

| Name                    | Type     | Description                                                  |
| :---------------------- | :------- | :----------------------------------------------------------- |
| data                    | *object* |                                                              |
| › order_state           | string   | order state, `"open"`, `"filled"`, `"canceled"`              |
| › max_show              | number   | Maximum amount within an order to be shown to other traders, 0 for invisible order. |
| › api                   | boolean  | `true` if created with API                                   |
| › amount                | number   | It represents the requested order size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › web                   | boolean  | `true` if created via Derinow frontend (optional)            |
| › instrument_name       | string   | Unique instrument identifier                                 |
| › advanced              | string   | advanced type: `"usdt"` or `"implv"` (Only for options; field is omitted if not applicable). |
| › original_order_type   | string   | Original order type. Optional field                          |
| › price                 | number   | Price in base currency                                       |
| › time_in_force         | string   | Order time in force: `"good_til_cancelled"`                  |
| › auto_replaced         | boolean  | Options, advanced orders only - `true` if last modification of the order was performed by the pricing engine, otherwise `false`. |
| › last_update_timestamp | integer  | The timestamp (milliseconds since the Unix epoch)            |
| › post_only             | boolean  | `true` for post-only orders only                             |
| › replaced              | boolean  | `true` if the order was edited (by user or - in case of advanced options orders - by pricing engine), otherwise `false`. |
| › filled_amount         | number   | Filled amount of the order. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › average_price         | number   | Average fill price of the order                              |
| › order_id              | string   | Unique order identifier                                      |
| › reduce_only           | boolean  | `true` for reduce-only orders only                           |
| › commission            | number   | Commission paid so far (in base currency)                    |
| › stop_price            | number   | stop price (Only for future stop orders)                     |
| › label                 | string   | user defined label (up to 64 characters)                     |
| › creation_timestamp    | integer  | The timestamp (milliseconds since the Unix epoch)            |
| › direction             | string   | Direction: `buy`, or `sell`                                  |
| › is_liquidation        | boolean  | `true` if order was automatically created during liquidation |
| › order_type            | string   | order type, `"limit"`                                        |

example:

```json
{
	"jsonrpc": "2.0",
	"method": "subscription",
	"params": {
		"channel": "user.orders.BTC-14AUG20.raw",
		"data": {
			"amount": "1",
			"price": "11895.00",
			"direction": "buy",
			"version": 0,
			"order_state": "filled",
			"instrument_name": "BTC-14AUG20",
			"time_in_force": "good_til_cancelled",
			"last_update_timestamp": 1597130534567,
			"filled_amount": "1",
			"average_price": "11770.00",
			"order_id": "39007591615041536",
			"creation_timestamp": 1597130534567,
			"order_type": "limit"
		}
	}
}
```

