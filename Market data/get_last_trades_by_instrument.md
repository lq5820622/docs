**URL** 

- `/public/get_last_trades_by_instrument`

Retrieve the latest trades that have occurred for a specific instrument.



**Parameters** 

| Parameter       | Required | Type    | Enum                   | Description                                                  |
| :-------------- | :------- | :------ | :--------------------- | :----------------------------------------------------------- |
| instrument_name | true     | string  |                        | Instrument name                                              |
| start_seq       | false    | integer |                        | The sequence number of the first trade to be returned        |
| end_seq         | false    | integer |                        | The sequence number of the last trade to be returned         |
| count           | false    | integer |                        | Number of requested items, default - `10`                    |
| include_old     | false    | boolean |                        | Include trades older than a few recent days, default - `false` |
| sorting         | false    | string  | `asc` `desc` `default` | Direction of results sorting (`default` value means no sorting, results will be returned in order in which they left the database) |



**Response**

| Name                 | Type              | Description                                        |
| :------------------- | :---------------- | :------------------------------------------------- |
| id                   | integer           | The id that was sent in the request                |
| jsonrpc              | string            | The JSON-RPC version (2.0)                         |
| usIn                 | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                         |
| usOut                | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                        |
| usDiff               | integer           | The number of microseconds that was spent handling the request                                               |
| result               | *object*          |                                                    |
| › has_more           | boolean           |                                                    |
| › trades             | array of *object* |                                                    |
| ›  › amount          | number            | Trade amount. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.).                                     |
| ›  › direction       | string            | Direction: `buy`, or `sell`                        |
| ›  › index_price     | number            | Index Price at the moment of trade                 |
| ›  › instrument_name | string            | Unique instrument identifier                       |
| ›  › mark_price      | number            | Mark Price at the moment of trade                  |
| ›  › price           | number            | Price in base currency                             |
| ›  › timestamp       | integer           | The timestamp of the trade                         |
| ›  › trade_id        | string            | Unique (per currency) trade identifier             |
| ›  › trade_seq       | integer           | The sequence number of the trade within instrument |

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

