**URL** 

- `/private/get_user_trades_by_currency_and_time`

Retrieve the latest user trades that have occurred for instruments in a specific currency symbol and within given time range.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter       | Required | Type    | Enum                       | Description                                                  |
| :-------------- | :------- | :------ | :------------------------- | :----------------------------------------------------------- |
| currency        | true     | string  | `BTC` `ETH` `MARGIN`       | The currency symbol                                          |
| kind            | false    | string  | `future` `option` `margin` | Instrument kind, if not provided instruments of all kinds are considered |
| start_timestamp | true     | integer |                            | The earliest timestamp to return result for                  |
| end_timestamp   | true     | integer |                            | The most recent timestamp to return result for               |
| count           | false    | integer |                            | Number of requested items, default - `10`                    |
| sorting         | false    | string  | `asc` `desc`               | Direction of results sorting, default - `desc`               |



**Response**

| Name                 | Type              | Description                                                  |
| :------------------- | :---------------- | :----------------------------------------------------------- |
| id                   | integer           | The id that was sent in the request                          |
| jsonrpc              | string            | The JSON-RPC version (2.0)                                   |
| usIn                 | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                   |
| usOut                | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff               | integer           | The number of microseconds that was spent handling the request                                                         |
| result               | *object*          |                                                              |
| › has_more           | boolean           |                                                              |
| › trades             | array of *object* |                                                              |
| ›  › amount          | number            | Trade amount. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.)                                               |
| ›  › direction       | string            | Direction: `buy`, or `sell`                                  |
| ›  › fee             | number            | User's fee in units of the specified `fee_currency`          |
| ›  › fee_currency    | string            | Currency, i.e `BTC`, `ETH`                                   |
| ›  › index_price     | number            | Index Price at the moment of trade                           |
| ›  › instrument_name | string            | Unique instrument identifier                                 |
| ›  › iv              | number            | Option implied volatility for the price (Option only)        |
| ›  › order_id        | string            | Id of the user order (maker or taker), i.e. subscriber's order id that took part in the trade |
| ›  › order_type      | string            | Order type: `limit`                                          |
| ›  › price           | number            | Price in base currency                                       |
| ›  › state           | string            | order state, `open`, `filled`, `canceled`                    |
| ›  › timestamp       | integer           | The timestamp of the trade                                   |
| ›  › trade_id        | string            | Unique (per currency) trade identifier                       |
| ›  › trade_seq       | integer           | The sequence number of the trade within instrument           |

example:

```json
{
	"id": "75",
	"jsonrpc": "2.0",
	"usIn": 1597130232751,
	"usOut": 1597130232819,
	"usDiff": 68,
	"result": {
		"count": 8,
		"trades": [{
			"amount": "9",
			"direction": "buy",
			"fee": "3.6",
			"iv": "0",
			"price": "5000",
			"state": "filled",
			"timestamp": 1596767572049,
			"index_price": "5000",
			"instrument_name": "BTC-07AUG20-13000-C",
			"order_id": "37485216473944064",
			"order_type": "limit",
			"trade_id": "12",
			"trade_seq": 3,
			"fee_currency": "USDT"
		}, {
			"amount": "1",
			"direction": "buy",
			"fee": "0.4",
			"iv": "0",
			"price": "5000",
			"state": "filled",
			"timestamp": 1596767561893,
			"index_price": "5000",
			"instrument_name": "BTC-07AUG20-13000-C",
			"order_id": "37485173876592640",
			"order_type": "limit",
			"trade_id": "11",
			"trade_seq": 2,
			"fee_currency": "USDT"
		}],
		"has_more": false
	}
}
```



