**URL** 

- `/private/get_open_orders_by_instrument`

Retrieves list of user's open orders within given Instrument.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter       | Required | Type   | Enum          | Description                 |
| :-------------- | :------- | :----- | :------------ | :-------------------------- |
| instrument_name | true     | string |               | Instrument name             |
| type            | false    | string | `all` `limit` | Order type, default - `all` |



**Response**

| Name                    | Type              | Description                                                  |
| :---------------------- | :---------------- | :----------------------------------------------------------- |
| id                      | integer           | The id that was sent in the request                          |
| jsonrpc                 | string            | The JSON-RPC version (2.0)                                   |
| usIn                    | integer           | The timestamp when the requests was received (microseconds since the Unix epoch) |
| usOut                   | integer           | The timestamp when the response was sent (microseconds since the Unix epoch) |
| usDiff                  | integer           | The number of microseconds that was spent handling the request |
| result                  | array of *object* |                                                              |
| › amount                | number            | It represents the requested order size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › average_price         | number            | Average fill price of the order                              |
| › creation_timestamp    | integer           | The timestamp (milliseconds since the Unix epoch)            |
| › direction             | string            | Direction: `buy`, or `sell`                                  |
| › filled_amount         | number            | Filled amount of the order. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › instrument_name       | string            | Unique instrument identifier                                 |
| › last_update_timestamp | integer           | The timestamp (milliseconds since the Unix epoch)            |
| › order_id              | string            | Unique order identifier                                      |
| › order_state           | string            | order state, `"open"`, `"filled"`, `"rejected"`, `"cancelled"` |
| › order_type            | string            | order type, `"limit"`                                        |
| › price                 | number            | Price in base currency                                       |
| › time_in_force         | string            | Order time in force: `"good_til_cancelled"`                  |
| › version               | number            | version                                                      |
| › api                   | boolean           | `true` if created with API                                   |
| › is_liquidation        | boolean           | `true` if order was automatically created during liquidation |

example:

```json
{
	"id": "234",
	"jsonrpc": "2.0",
	"usIn": 1597129996498,
	"usOut": 1597129996512,
	"usDiff": 14,
	"result": [{
		"amount": "1",
		"price": "10000.00",
		"direction": "buy",
		"version": 0,
		"order_state": "open",
		"instrument_name": "BTC-07AUG20-12250-C",
		"time_in_force": "good_til_cancelled",
		"last_update_timestamp": 1596768194123,
		"filled_amount": "0",
		"average_price": "0.00",
		"order_id": "37487825633021952",
		"creation_timestamp": 1596768194121,
		"order_type": "limit"
	}, {
		"amount": "20",
		"price": "1000.00",
		"direction": "buy",
		"version": 0,
		"order_state": "open",
		"instrument_name": "BTC-07AUG20-12125-C",
		"time_in_force": "good_til_cancelled",
		"last_update_timestamp": 1596768171805,
		"filled_amount": "0",
		"average_price": "0.00",
		"order_id": "37487732024545280",
		"creation_timestamp": 1596768171803,
		"order_type": "limit"
	}]
}
```




