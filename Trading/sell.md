**URL** 

- `/private/sell`

Places a sell order for an instrument.



*This is a private method; it can only be used after authentication.*

*This is a matching engine method.*

**Parameters** 

| Parameter       | Required | Type   | Enum    | Description                                              |
| --------------- | -------- | ------ | ------- | -------------------------------------------------------- |
| instrument_name | true     | string |         | Instrument name                                          |
| amount          | false    | string |         | The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.)                                                         |
| type            | false    | string | `limit` | The order type, default: "limit"                         |
| label           | false    | string |         | user defined label for the order (maximum 64 characters) |
| price           | false    | string |         |                                                          |



**Response**

| Name                       | Type              | Description                                                  |
| :------------------------- | :---------------- | :----------------------------------------------------------- |
| id                         | integer           | The id that was sent in the request                          |
| jsonrpc                    | string            | The JSON-RPC version (2.0)                                   |
| usIn                       | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                      | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                     | integer           | The number of microseconds that was spent handling the request                                                         |
| result                     | *object*          |                                                              |
| › order                    | *object*          |                                                              |
| ›  › order_id              | string            | Unique order identifier                                      |

example:

```json
{
	"id": "114",
	"jsonrpc": "2.0",
	"usIn": 1597129591020,
	"usOut": 1597129591034,
	"usDiff": 14,
	"result": {
		"order": {
			"order_id": "39003634138222592"
		}
	}
}
```







