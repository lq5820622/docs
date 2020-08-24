## trades.{instrument_name}.{interval}

Get notifications about trades for an instrument.

### Channel Parameters

| Parameter       | Required | Type   | Enum  | Description                                                  |
| :-------------- | :------- | :----- | :---- | :----------------------------------------------------------- |
| instrument_name | true     | string |       | Instrument name                                              |
| interval        | true     | string | `raw` | Frequency of notifications. Events will be aggregated over this interval. The value `raw` means no aggregation will be applied |

### Response

| Name              | Type     | Description                                                  |
| :---------------- | :------- | :----------------------------------------------------------- |
| data              | *object* |                                                              |
| › amount          | number   | Trade amount. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › block_trade_id  | string   | Block trade id - when trade was part of block trade          |
| › direction       | string   | Direction: `buy`, or `sell`                                  |
| › index_price     | number   | Index Price at the moment of trade                           |
| › instrument_name | string   | Unique instrument identifier                                 |
| › iv              | number   | Option implied volatility for the price (Option only)        |
| › liquidation     | string   | Optional field (only for trades caused by liquidation): `"M"` when maker side of trade was under liquidation, `"T"` when taker side was under liquidation, `"MT"` when both sides of trade were under liquidation |
| › mark_price      | number   | Mark Price at the moment of trade                            |
| › price           | number   | Price in base currency                                       |
| › tick_direction  | integer  | Direction of the "tick" (`0` = Plus Tick, `1` = Zero-Plus Tick, `2` = Minus Tick, `3` = Zero-Minus Tick). |
| › timestamp       | integer  | The timestamp of the trade                                   |
| › trade_id        | string   | Unique (per currency) trade identifier                       |
| › trade_seq       | integer  | The sequence number of the trade within instrument           |

example:

```json
{
	"params": {
		"data": [{
			"instrument_name": "BTC-USDT",
			"trade_seq": "5707645",
			"trade_id": "5707645",
			"timestamp": "1597130650175.000000",
			"price": "11733.145",
			"amount": "0.00187000",
			"direction": "buy"
		}],
		"channel": "trades.BTC-USDT.raw"
	},
	"method": "subscription",
	"jsonrpc": "2.0"
}
```

