## price_index.{index_name}

Provides information about current value (price) for Derinow Index

### Channel Parameters

| Parameter  | Required | Type   | Enum                  | Description                                                  |
| :--------- | :------- | :----- | :-------------------- | :----------------------------------------------------------- |
| index_name | true     | string | `btc_usdt` `eth_usdt` | Index identifier, matches (base) cryptocurrency with quote currency |

### Response

| Name         | Type     | Description                                                  |
| :----------- | :------- | :----------------------------------------------------------- |
| data         | *object* |                                                              |
| › index_name | string   | Index identifier, matches (base) cryptocurrency with quote currency |
| › price      | number   | Current index price                                          |
| › timestamp  | integer  | The timestamp (milliseconds since the Unix epoch)            |

example:

```json
{
	"jsonrpc": "2.0",
	"method": "subscription",
	"params": {
		"channel": "price_index.btc_usdt",
		"data": {
			"price": "11738.73",
			"index_name": "btc_usdt",
			"timestamp": 1597130683001
		}
	}
}
```

