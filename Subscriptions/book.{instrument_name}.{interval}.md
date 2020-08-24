## book.{instrument_name}.{interval}

Notifies about changes to the order book for a certain instrument.

The first notification will contain the whole book (bid and ask amounts for all prices). After that there will only be information about changes to individual price levels.

The first notification will contain the amounts for all price levels (list of `['new', price, amount]` tuples). All following notifications will contain a list of tuples with action, price level and new amount (`[action, price, amount]`). Action can be either `new`, `change` or `delete`.

Each notification will contain a `change_id` field, and each message except for the first one will contain a field `prev_change_id`. If `prev_change_id` is equal to the `change_id` of the previous message, this means that no messages have been missed.

The minsize of futures and options is one contract, while margin is measured in base currency(BTC, ETH, etc.).

### Channel Parameters

| Parameter       | Required | Type   | Enum  | Description                                                  |
| :-------------- | :------- | :----- | :---- | :----------------------------------------------------------- |
| instrument_name | true     | string |       | Instrument name                                              |
| interval        | true     | string | `raw` | Frequency of notifications. Events will be aggregated over this interval. |

### Response

| Name              | Type                             | Description                                                  |
| :---------------- | :------------------------------- | :----------------------------------------------------------- |
| data              | *object*                         |                                                              |
| › asks            | array of [action, price, amount] | The first notification will contain the amounts for all price levels (a list of ["new", price, amount] tuples). All following notifications will contain a list of tuples with action, price level and new amount ([action, price, amount]). Action can be `new`, `change` or `delete`. |
| › bids            | array of [action, price, amount] | (See 'asks' above.)                                          |
| › change_id       | integer                          | Identifier of the notification                               |
| › instrument_name | string                           | Unique instrument identifier                                 |
| › prev_change_id  | integer                          | Identifier of the previous notification (it's **not** included for the first notification) |
| › timestamp       | integer                          | The timestamp of last change (milliseconds since the Unix epoch) |
| › type            | string                           | Type of notification: `snapshot` for initial, `change` for others. The field is only included in aggregated response (when input parameter `interval` != `raw`) |

example:

```json
{
	"params": {
		"data": {
			"timestamp": 1597130461800,
			"asks": [
				["11770.000", "4.00000"],
				["11783.000", "4.00000"],
				["11785.000", "4.00000"],
				["11797.000", "3.00000"],
				["11809.000", "4.00000"],
				["11822.000", "5.00000"],
				["11834.000", "4.00000"],
				["11846.000", "4.00000"],
				["11862.000", "4.00000"],
				["11869.000", "5.00000"],
				["11879.000", "60.00000"],
				["11890.000", "8.00000"],
				["11909.000", "8.00000"],
				["11914.000", "85.00000"],
				["11927.000", "15.00000"],
				["11939.000", "29.00000"],
				["11951.000", "93.00000"],
				["11963.000", "8.00000"],
				["11979.000", "32.00000"],
				["11991.000", "87.00000"],
				["12005.000", "85.00000"],
				["12010.000", "30.00000"],
				["12124.000", "6.00000"],
				["12281.000", "54.00000"],
				["12400.000", "53.00000"],
				["12522.000", "90.00000"],
				["12642.000", "10.00000"],
				["12762.000", "87.00000"],
				["12883.000", "47.00000"],
				["13003.000", "91.00000"],
				["13124.000", "95.00000"],
				["13244.000", "75.00000"],
				["13364.000", "97.00000"],
				["13485.000", "87.00000"],
				["13605.000", "13.00000"],
				["13726.000", "20.00000"],
				["13846.000", "84.00000"],
				["13968.000", "95.00000"],
				["14068.000", "38.00000"],
				["14194.000", "25.00000"]
			],
			"bids": [
				["11740.000", "4.00000"],
				["11728.000", "4.00000"],
				["11716.000", "3.00000"],
				["11714.000", "4.00000"],
				["11701.000", "4.00000"],
				["11690.000", "6.00000"],
				["11677.000", "5.00000"],
				["11665.000", "5.00000"],
				["11653.000", "6.00000"],
				["11642.000", "6.00000"],
				["11626.000", "53.00000"],
				["11614.000", "18.00000"],
				["11602.000", "41.00000"],
				["11586.000", "57.00000"],
				["11578.000", "49.00000"],
				["11564.000", "72.00000"],
				["11561.000", "9.00000"],
				["11546.000", "50.00000"],
				["11535.000", "87.00000"],
				["11523.000", "56.00000"],
				["11513.000", "35.00000"],
				["11314.000", "68.00000"],
				["11196.000", "17.00000"],
				["11076.000", "38.00000"],
				["10945.000", "71.00000"],
				["10823.000", "17.00000"],
				["10704.000", "30.00000"],
				["10581.000", "86.00000"],
				["10462.000", "41.00000"],
				["10340.000", "12.00000"],
				["10339.000", "46.00000"],
				["10222.000", "94.00000"],
				["10103.000", "76.00000"],
				["9982.000", "90.00000"],
				["9862.000", "33.00000"],
				["9741.000", "81.00000"],
				["9622.000", "17.00000"],
				["9494.000", "33.00000"],
				["9390.000", "42.00000"]
			],
			"instrument_name": "BTC-14AUG20"
		},
		"channel": "book.BTC-14AUG20.raw"
	},
	"method": "subscription",
	"jsonrpc": "2.0"
}
```

