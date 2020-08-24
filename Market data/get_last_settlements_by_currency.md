**URL** 

- `/public/get_last_settlements_by_currency`

Retrieves historical settlement, delivery and bankruptcy events coming from all instruments within given currency.



**Parameters** 

| Parameter              | Required | Type    | Enum                                 | Description                               |
| :--------------------- | :------- | :------ | :----------------------------------- | :---------------------------------------- |
| currency               | true     | string  | `BTC` `ETH`                          | The currency symbol                       |
| type                   | false    | string  | `settlement` `delivery` `bankruptcy` | Settlement type                           |
| count                  | false    | integer |                                      | Number of requested items, default - `20` |
| continuation           | false    | string  |                                      | Continuation token for pagination         |
| search_start_timestamp | false    | integer |                                      | The latest timestamp to return result for |



**Response**

| Name                     | Type              | Description                                                  |
| :----------------------- | :---------------- | :----------------------------------------------------------- |
| id                       | integer           | The id that was sent in the request                          |
| jsonrpc                  | string            | The JSON-RPC version (2.0)                                   |
| usIn                     | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                    | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                   | integer           | The number of microseconds that was spent handling the request                                                         |
| result                   | *object*          |                                                              |
| › continuation           | string            | Continuation token for pagination.                           |
| › settlements            | array of *object* |                                                              |
| ›  › instrument_name     | string            | instrument name (settlement and delivery only)               |
| ›  › mark_price          | number            | mark price for at the settlement time                        |
| ›  › position            | number            | position size                                                |
| ›  › session_profit_loss | number            | total value of session profit and losses (in base currency)  |
| ›  › timestamp           | integer           | The timestamp (milliseconds since the Unix epoch)            |
| ›  › type                | string            | The type of settlement. `settlement`, `delivery` or `apport`. |

example:

```json
{
	"id": "17",
	"jsonrpc": "2.0",
	"usIn": 1597129255816,
	"usOut": 1597129256618,
	"usDiff": 802,
	"result": {
		"trades": [{
			"amount": "1",
			"direction": "sell",
			"iv": "0",
			"price": "11794",
			"timestamp": "1597128058502",
			"index_price": "11773.42",
			"instrument_name": "BTC-14AUG20",
			"trade_id": 4504,
			"trade_seq": 28
		}, {
			"amount": "1",
			"direction": "buy",
			"iv": "0",
			"price": "11821",
			"timestamp": "1597127989718",
			"index_price": "11778.96",
			"instrument_name": "BTC-14AUG20",
			"trade_id": 4503,
			"trade_seq": 27
		}],
		"has_more": false
	}
}
```

