## user.changes.{kind}.{currency}.{interval}

Get notifications about changes in user's updates related to order, trades, etc. in instruments of a given kind and currency.

 This is a private subscription; subscribing is only possible when authenticated.

### Channel Parameters

| Parameter | Required | Type   | Enum                    | Description                                                  |
| :-------- | :------- | :----- | :---------------------- | :----------------------------------------------------------- |
| kind      | true     | string | `future` `option` `any` | Instrument kind or `"any"` for all                           |
| currency  | true     | string | `BTC` `ETH` `any`       | The currency symbol or `"any"` for all                       |
| interval  | true     | string | `raw`                   | Frequency of notifications. Events will be aggregated over this interval. The value `raw` means no aggregation will be applied |

### Response

| Name                             | Type              | Description                                                  |
| :------------------------------- | :---------------- | :----------------------------------------------------------- |
| data                             | array of *object* |                                                              |
| › instrument_name                | string            | Unique instrument identifier                                 |
| › orders                         | array of *object* |                                                              |
| ›  › order_state                 | string            | order state, `"open"`, `"filled"`,  `"canceled"`             |
| ›  › max_show                    | number            | Maximum amount within an order to be shown to other traders, 0 for invisible order. |
| ›  › api                         | boolean           | `true` if created with API                                   |
| ›  › amount                      | number            | It represents the requested order size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.) |
| ›  › web                         | boolean           | `true` if created via Derinow frontend (optional)            |
| ›  › instrument_name             | string            | Unique instrument identifier                                 |
| ›  › advanced                    | string            | advanced type: `"usdt"` or `"implv"` (Only for options; field is omitted if not applicable). |
|                                  |                   |                                                              |
| ›  › triggered                   | boolean           | Whether the stop order has been triggered (Only for stop orders) |
| ›  › block_trade                 | boolean           | true if order made from block_trade trade, added only in that case. |
| ›  › original_order_type         | string            | Original order type. Optional field                          |
| ›  › price                       | number            | Price in base currency                                       |
| ›  › time_in_force               | string            | Order time in force: `"good_til_cancelled"`                  |
| ›  › auto_replaced               | boolean           | Options, advanced orders only - `true` if last modification of the order was performed by the pricing engine, otherwise `false`. |
| ›  › stop_order_id               | string            | Id of the stop order that was triggered to create the order (Only for orders that were created by triggered stop orders). |
| ›  › last_update_timestamp       | integer           | The timestamp (milliseconds since the Unix epoch)            |
| ›  › post_only                   | boolean           | `true` for post-only orders only                             |
| ›  › replaced                    | boolean           | `true` if the order was edited (by user or - in case of advanced options orders - by pricing engine), otherwise `false`. |
| ›  › filled_amount               | number            | Filled amount of the order. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| ›  › average_price               | number            | Average fill price of the order                              |
| ›  › order_id                    | string            | Unique order identifier                                      |
| ›  › reduce_only                 | boolean           | `true` for reduce-only orders only                           |
| ›  › commission                  | number            | Commission paid so far (in base currency)                    |
| ›  › app_name                    | string            | Name of the application that placed the order on behalf of the user (optional). |
| ›  › stop_price                  | number            | stop price (Only for future stop orders)                     |
| ›  › label                       | string            | user defined label (up to 64 characters)                     |
| ›  › creation_timestamp          | integer           | The timestamp (milliseconds since the Unix epoch)            |
| ›  › direction                   | string            | Direction: `buy`, or `sell`                                  |
| ›  › is_liquidation              | boolean           | `true` if order was automatically created during liquidation |
| ›  › order_type                  | string            | order type, `"limit"`                                        |
| ›  › usd                         | number            | Option price in USDT (Only if `advanced="usdt"`)             |
| ›  › profit_loss                 | number            | Profit and loss in base currency.                            |
| ›  › implv                       | number            | Implied volatility in percent. (Only if `advanced="implv"`)  |
| ›  › trigger                     | string            | Trigger type (Only for stop orders). Allowed values: `"index_price"`, `"mark_price"`, `"last_price"`. |
| › position                       | array of *object* |                                                              |
| ›  › average_price               | number            | Average price of trades that built this position             |
| ›  › average_price_usd           | number            | Only for options, average price in USDT                      |
| ›  › delta                       | number            | Delta parameter                                              |
| ›  › direction                   | string            | Direction: `buy`, `sell` or `zero`                           |
| ›  › estimated_liquidation_price | number            | Only for futures, estimated liquidation price                |
| ›  › floating_profit_loss        | number            | Floating profit or loss                                      |
| ›  › floating_profit_loss_usd    | number            | Only for options, floating profit or loss in USDT            |
| ›  › gamma                       | number            | Only for options, Gamma parameter                            |
| ›  › index_price                 | number            | Current index price                                          |
| ›  › initial_margin              | number            | Initial margin                                               |
| ›  › instrument_name             | string            | Unique instrument identifier                                 |
| ›  › kind                        | string            | Instrument kind, `"future"` or `"option"`                    |
| ›  › leverage                    | integer           | Current available leverage for future position               |
| ›  › maintenance_margin          | number            | Maintenance margin                                           |
| ›  › mark_price                  | number            | Current mark price for position's instrument                 |
| ›  › open_orders_margin          | number            | Open orders margin                                           |
| ›  › realized_funding            | number            | Realized Funding in current session included in session realized profit or loss, only for positions of perpetual instruments |
| ›  › realized_profit_loss        | number            | Realized profit or loss                                      |
| ›  › settlement_price            | number            | Last settlement price for position's instrument 0 if instrument wasn't settled yet |
| ›  › size                        | number            | Position size. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| ›  › size_currency               | number            | Only for futures, position size in base currency             |
| ›  › theta                       | number            | Only for options, Theta parameter                            |
| ›  › total_profit_loss           | number            | Profit or loss from position                                 |
| ›  › vega                        | number            | Only for options, Vega parameter                             |
| › trades                         | array of *object* |                                                              |
| ›  › amount                      | number            | Trade amount. The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.). |
| ›  › block_trade_id              | string            | Block trade id - when trade was part of block trade          |
| ›  › direction                   | string            | Direction: `buy`, or `sell`                                  |
| ›  › fee                         | number            | User's fee in units of the specified `fee_currency`          |
| ›  › fee_currency                | string            | Currency, i.e `"BTC"`, `"ETH"`                               |
| ›  › index_price                 | number            | Index Price at the moment of trade                           |
| ›  › instrument_name             | string            | Unique instrument identifier                                 |
| ›  › iv                          | number            | Option implied volatility for the price (Option only)        |
| ›  › label                       | string            | User defined label (presented only when previously set for order by user) |
| ›  › liquidation                 | string            | Optional field (only for trades caused by liquidation): `"M"` when maker side of trade was under liquidation, `"T"` when taker side was under liquidation, `"MT"` when both sides of trade were under liquidation |
| ›  › liquidity                   | string            | Describes what was role of users order: `"M"` when it was maker order, `"T"` when it was taker order |
| ›  › mark_price                  | number            | Mark Price at the moment of trade                            |
| ›  › matching_id                 | string            | Always `null`, except for a self-trade which is possible only if self-trading is switched on for the account (in that case this will be id of the maker order of the subscriber) |
| ›  › order_id                    | string            | Id of the user order (maker or taker), i.e. subscriber's order id that took part in the trade |
| ›  › order_type                  | string            | Order type: `"limit`                                         |
| ›  › post_only                   | string            | `true` if user order is post-only                            |
| ›  › price                       | number            | Price in base currency                                       |
| ›  › profit_loss                 | number            | Profit and loss in base currency.                            |
| ›  › reduce_only                 | string            | `true` if user order is reduce-only                          |
| ›  › self_trade                  | boolean           | `true` if the trade is against own order. This can only happen when your account has self-trading enabled. Contact an administrator if you think you need that |
| ›  › state                       | string            | order state, `"open"`, `"filled"`, `"canceled"` (if order was archived) |
| ›  › tick_direction              | integer           | Direction of the "tick" (`0` = Plus Tick, `1` = Zero-Plus Tick, `2` = Minus Tick, `3` = Zero-Minus Tick). |
| ›  › timestamp                   | integer           | The timestamp of the trade                                   |
| ›  › trade_id                    | string            | Unique (per currency) trade identifier                       |
| ›  › trade_seq                   | integer           | The sequence number of the trade within instrument           |
| ›  › underlying_price            | number            | Underlying price for implied volatility calculations (Options only) |

example:

```json
{
	"jsonrpc": "2.0",
	"method": "subscription",
	"params": {
		"channel": "user.changes.future.BTC.raw",
		"data": {
			"trades": [],
			"positions": [{
				"average_price": "12217",
				"delta": "0",
				"direction": "-",
				"floating_profit_loss": "0",
				"instrument_name": "BTC-25DEC20",
				"mark_price": "12218.21",
				"realized_profit_loss": "-0.0558",
				"size": "0",
				"session_price": "12221.58",
				"total_profit_loss": "0",
				"vega": "0",
				"zero_margin_size": "0",
				"version": "42478"
			}, {
				"average_price": "11770",
				"delta": "0.02",
				"direction": "buy",
				"floating_profit_loss": "-0.107",
				"instrument_name": "BTC-14AUG20",
				"mark_price": "11764.65",
				"realized_profit_loss": "0",
				"size": "2",
				"session_price": "11770",
				"total_profit_loss": "-0.107",
				"vega": "0",
				"zero_margin_size": "0",
				"version": "8"
			}],
			"orders": []
		}
	}
}
```

