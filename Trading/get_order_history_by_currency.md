**URL** 

- `/private/get_order_history_by_currency`

Retrieves history of orders that have been fully filled or canceled.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter | Required | Type    | Enum                       | Description                                                  |
| :-------- | :------- | :------ | :------------------------- | :----------------------------------------------------------- |
| currency  | true     | string  | `BTC` `ETH` `MARGIN`       | The currency symbol                                          |
| kind      | false    | string  | `future` `option` `margin` | Instrument kind, if not provided instruments of all kinds are considered |
| count     | false    | integer |                            | Number of requested items, default - `20`                    |
| offset    | false    | integer |                            | The offset for pagination, default - `0`                     |



**Response**

| Name                    | Type              | Description                                                  |
| :---------------------- | :---------------- | :----------------------------------------------------------- |
| id                      | integer           | The id that was sent in the request                          |
| jsonrpc                 | string            | The JSON-RPC version (2.0)                                   |
| usIn                    | integer           | The timestamp when the requests was received (microseconds since the Unix epoch) |
| usOut                   | integer           | The timestamp when the response was sent (microseconds since the Unix epoch) |
| usDiff                  | integer           | The number of microseconds that was spent handling the request |
| result                  | array of *object* |                                                              |
| › order_state           | string            | order state, `"open"`, `"filled"`,`"canceled"`               |
| › amount                | number            | It represents the requested order size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.)                      |
| › instrument_name       | string            | Unique instrument identifier                                 |
| › advanced              | string            | advanced type: `iv` (Only for options; field is omitted if not applicable). |
| › price                 | number            | Price in base currency                                       |
| › time_in_force         | string            | Order time in force: `"good_til_cancelled"`                  |
| › last_update_timestamp | long              | The timestamp (milliseconds since the Unix epoch)            |
| › filled_amount         | number            | Filled amount of the order. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › average_price         | number            | Average fill price of the order                              |
| › order_id              | string            | Unique order identifier                                      |
| › creation_timestamp    | long              | The timestamp (milliseconds since the Unix epoch)            |
| › direction             | string            | Direction: `buy`, or `sell`                                  |
| › is_liquidation        | boolean           | `true` if order was automatically created during liquidation |
| › order_type            | string            | order type, `"limit"`                                        |
|                         |                   |                                                              |
|                         |                   |                                                              |

example:

```json
{
	"id": "248",
	"jsonrpc": "2.0",
	"usIn": 1597130045270,
	"usOut": 1597130046950,
	"usDiff": 1680,
	"result": [{
		"amount": "1",
		"price": "855",
		"direction": "buy",
		"version": 1,
		"order_state": "canceled",
		"instrument_name": "BTC-14AUG20-11000-C",
		"time_in_force": "good_til_cancelled",
		"last_update_timestamp": 1597129894026,
		"filled_amount": "0",
		"average_price": "0",
		"order_id": "39004881276768256",
		"creation_timestamp": 1597129894025,
		"order_type": "limit"
	}, {
		"amount": "1",
		"price": "859",
		"direction": "buy",
		"version": 1,
		"order_state": "canceled",
		"instrument_name": "BTC-14AUG20-11000-C",
		"time_in_force": "good_til_cancelled",
		"last_update_timestamp": 1597129894026,
		"filled_amount": "0",
		"average_price": "0",
		"order_id": "39004865862701056",
		"creation_timestamp": 1597129894025,
		"order_type": "limit"
	}]
}
```



