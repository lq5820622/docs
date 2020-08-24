## user.trades.{instrument_name}.{interval}

Get notifications about user's trades in an instrument.

 This is a private subscription; subscribing is only possible when authenticated.

### Channel Parameters

| Parameter       | Required | Type   | Enum  | Description                                                  |
| :-------------- | :------- | :----- | :---- | :----------------------------------------------------------- |
| instrument_name | true     | string |       | Instrument name                                              |
| interval        | true     | string | `raw` | Frequency of notifications. Events will be aggregated over this interval. The value `raw` means no aggregation will be applied |

### Response

| Name               | Type              | Description                                                  |
| :----------------- | :---------------- | :----------------------------------------------------------- |
| data               | array of *object* |                                                              |
| › amount           | number            | Trade amount. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| › block_trade_id   | string            | Block trade id - when trade was part of block trade          |
| › direction        | string            | Direction: `buy`, or `sell`                                  |
| › fee              | number            | User's fee in units of the specified `fee_currency`          |
| › fee_currency     | string            | Currency, i.e `"BTC"`, `"ETH"`                               |
| › index_price      | number            | Index Price at the moment of trade                           |
| › instrument_name  | string            | Unique instrument identifier                                 |
| › iv               | number            | Option implied volatility for the price (Option only)        |
| › label            | string            | User defined label (presented only when previously set for order by user) |
| › liquidation      | string            | Optional field (only for trades caused by liquidation): `"M"` when maker side of trade was under liquidation, `"T"` when taker side was under liquidation, `"MT"` when both sides of trade were under liquidation |
| › liquidity        | string            | Describes what was role of users order: `"M"` when it was maker order, `"T"` when it was taker order |
| › mark_price       | number            | Mark Price at the moment of trade                            |
| › matching_id      | string            | Always `null`, except for a self-trade which is possible only if self-trading is switched on for the account (in that case this will be id of the maker order of the subscriber) |
| › order_id         | string            | Id of the user order (maker or taker), i.e. subscriber's order id that took part in the trade |
| › order_type       | string            | Order type: `"limit`                                         |
| › post_only        | string            | `true` if user order is post-only                            |
| › price            | number            | Price in base currency                                       |
| › profit_loss      | number            | Profit and loss in base currency.                            |
| › reduce_only      | string            | `true` if user order is reduce-only                          |
| › self_trade       | boolean           | `true` if the trade is against own order. This can only happen when your account has self-trading enabled. Contact an administrator if you think you need that |
| › state            | string            | order state, `"open"`, `"filled"`, `"cancelled"` (if order was archived) |
| › tick_direction   | integer           | Direction of the "tick" (`0` = Plus Tick, `1` = Zero-Plus Tick, `2` = Minus Tick, `3` = Zero-Minus Tick). |
| › timestamp        | integer           | The timestamp of the trade                                   |
| › trade_id         | string            | Unique (per currency) trade identifier                       |
| › trade_seq        | integer           | The sequence number of the trade within instrument           |
| › underlying_price | number            | Underlying price for implied volatility calculations (Options only) |

example:

```json
{
	"jsonrpc": "2.0",
	"method": "subscription",
	"params": {
		"channel": "user.trades.BTC-14AUG20.raw",
		"data": {
			"tradeId": 4552,
			"userId": 310,
			"orderId": "39016506486558720",
			"market": "BTC",
			"baseCurrency": "USDT",
			"kind": "future",
			"direction": "buy",
			"instrumentName": "BTC-14AUG20",
			"amount": "3",
			"fee": "0.15",
			"feeCurrency": "USDT",
			"price": "11834",
			"iv": "0",
			"orderType": "limit",
			"orderState": "filled",
			"creationTimestamp": "1597132660038",
			"role": "taker",
			"shardName": "future_trades_single_user"
		}
	}
}
```

