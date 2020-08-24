**URL** 

- `/private/cancel`

Cancel an order, specified by order id



*This is a private method; it can only be used after authentication.*

*This is a matching engine method.*

**Parameters** 

| Parameter | Required | Type   | Enum | Description  |
| :-------- | :------- | :----- | :--- | :----------- |
| order_id  | true     | string |      | The order id |



**Response**

| Name                    | Type     | Description                                                  |
| :---------------------- | :------- | :----------------------------------------------------------- |
| id                      | integer  | The id that was sent in the request                          |
| jsonrpc                 | string   | The JSON-RPC version (2.0)                                   |
| usIn                    | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                   | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                  | integer  | The number of microseconds that was spent handling the request                                                         |
| result                  | *object* |                                                              |
| › order_id              | string   | Unique order identifier                                      |

example:

```json
{
	"id": "154",
	"jsonrpc": "2.0",
	"usIn": 1597129786929,
	"usOut": 1597129786937,
	"usDiff": 8,
	"result": {
		"order_id": "39003634138222592"
	}
}
```







