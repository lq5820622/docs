## chart.trades.{instrument_name}.{resolution}

Publicly available market data used to generate a TradingView candle chart. During single resolution period, many events can be sent, each with updated values for the recent period.

**NOTICE** When there is no trade during the requested resolution period (e.g. 1 minute), then filling sample is generated which uses data from the last available trade candle (open and close values).

### Channel Parameters

| Parameter       | Required | Type   | Enum                                                         | Description                                                  |
| :-------------- | :------- | :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| instrument_name | true     | string |                                                              | Instrument name                                              |
| resolution      | true     | string | `1` `3` `5` `10` `15` `30` `60` `120` `180` `360` `720` `1D` | Chart bars resolution given in full minutes or keyword `1D` (only some specific resolutions are supported) |

### Response

| Name     | Type     | Description                                       |
| :------- | :------- | :------------------------------------------------ |
| data     | *object* |                                                   |
| › close  | number   | The close price for the candle                    |
| › cost   | number   | Cost data for the candle                          |
| › high   | number   | The highest price level for the candle            |
| › low    | number   | The lowest price level for the candle             |
| › open   | number   | The open price for the candle'                    |
| › tick   | integer  | The timestamp (milliseconds since the Unix epoch) |
| › volume | number   | Volume data for the candle\                       |

example:

```json
{
	"params": {
		"data": {
			"tick": 1597130400,
			"open": 11794.000,
			"high": 11794.000,
			"low": 11770.000,
			"close": 11770.000,
			"volume": 2.0000,
			"cost": 23540.000
		},
		"channel": "chart.trades.BTC-14AUG20.5"
	},
	"method": "subscription",
	"jsonrpc": "2.0"
}
```

