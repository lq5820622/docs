**URL** 

- `/private/close_position`

Makes closing position reduce only order .



*This is a private method; it can only be used after authentication.*

*This is a matching engine method.*

**Parameters** 

| Parameter       | Required | Type   | Enum    | Description                     |
| :-------------- | :------- | :----- | :------ | :------------------------------ |
| instrument_name | true     | string |         | Instrument name                 |
| type            | true     | string | `limit` | The order type                  |
| price           | false    | string |         | Optional price for limit order. |



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
| ›  › order_id              | string            | Id of the user order (maker or taker), i.e. subscriber's order id that took part in the trade |

example:

```json
{
	"id": "223",
	"jsonrpc": "2.0",
	"usIn": 1597129965170,
	"usOut": 1597129965187,
	"usDiff": 17,
	"result": {
		"order": {
			"order_id": "39005203453841408"
		}
	}
}
```



