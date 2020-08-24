## markprice.{kind}.{currency}

Provides information about options and futures markprices

### Channel Parameters

| Parameter | Required | Type   | Enum              | Description         |
| :-------- | :------- | :----- | :---------------- | :------------------ |
| kind      | true     | string | `future` `option` | Instrument kind     |
| currency  | true     | string | `BTC` `ETH`       | The currency symbol |

### Response

| Name                | Type     | Description                                       |
| :------------------ | :------- | :------------------------------------------------ |
| data                | *object* |                                                   |
| › instrument_name   | string   | Instrument name                                   |
| › mark_price        | number   | Current index price                               |
| › mark_iv           | number   | Current index iv                                  |
| › mut               | integer  | The timestamp (milliseconds since the Unix epoch) |
| ›  underlying_price | number   | Underlying price                                  |
| › underlying_index  | number   | Underlying name                                   |

example:

```json
{
  "jsonrpc": "2.0",
  "method": "subscription",
  "params": {
    "channel": "markprice.option.ETH",
    "data": [
      {
        "mut": "1597303073115",
        "instrument_name": "ETH-26MAR21-440-P",
        "mark_iv": "0.8341",
        "mark_price": "132.6479",
        "underlying_price": "391.3781",
        "underlying_index": "ETH-26MAR21"
      },
      {
        "mut": "1596959999594",
        "instrument_name": "ETH-09AUG20-470-C",
        "mark_iv": "0.9532",
        "mark_price": "0",
        "underlying_price": "380.3464"
      }
    ]
  }
}
```