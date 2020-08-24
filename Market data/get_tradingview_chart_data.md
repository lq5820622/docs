**URL** 

- `/public/get_tradingview_chart_data`

Publicly available market data used to generate a TradingView candle chart.



**Parameters** 

| Parameter       | Required | Type    | Enum                                                         | Description                                                  |
| :-------------- | :------- | :------ | :----------------------------------------------------------- | :----------------------------------------------------------- |
| instrument_name | true     | string  |                                                              | Instrument name                                              |
| start_timestamp | true     | integer |                                                              | The earliest timestamp to return result for                  |
| end_timestamp   | true     | integer |                                                              | The most recent timestamp to return result for               |
| resolution      | true     | string  | `1` `3` `5` `10` `15` `30` `60` `120` `180` `360` `720` `1D` | Chart bars resolution given in full minutes or keyword `1D` (only some specific resolutions are supported) |



**Response**

| Name     | Type             | Description                                                  |
| :------- | :--------------- | :----------------------------------------------------------- |
| id       | integer          | The id that was sent in the request                          |
| jsonrpc  | string           | The JSON-RPC version (2.0)                                   |
| usIn     | integer          | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut    | integer          | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff   | integer          | The number of microseconds that was spent handling the request                                                         |
| result   | *object*         |                                                              |
| › close  | array of number  | List of prices at close (one per candle)                     |
| › cost   | array of number  | List of cost bars (volume in quote currency, one per candle) |
| › high   | array of number  | List of highest price levels (one per candle)                |
| › low    | array of number  | List of lowest price levels (one per candle)                 |
| › open   | array of number  | List of prices at open (one per candle)                      |
| › status | string           | Status of the query: `ok` or `no_data`                       |
| › ticks  | array of integer | Values of the time axis given in milliseconds since UNIX epoch |
| › volume | array of number  | List of volume bars (in base currency, one per candle)       |

example:

```json
{
	"id": "27",
	"jsonrpc": "2.0",
	"usIn": 1597129256713,
	"usOut": 1597129257730,
	"usDiff": 1017,
	"result": [{
		"tick": 1596683700,
		"open": "11679.227",
		"high": "11679.227",
		"low": "11679.227",
		"close": "11679.227",
		"volume": "0.0000",
		"cost": "0.000"
	}, {
		"tick": 1596684000,
		"open": "11679.227",
		"high": "11679.227",
		"low": "11679.227",
		"close": "11679.227",
		"volume": "0.0000",
		"cost": "0.000"
	}]
}
```

