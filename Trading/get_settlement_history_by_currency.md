**URL** 

- `/private/get_settlement_history_by_currency`

Retrieves settlement, delivery and apport events that have affected your account.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter | Required | Type    | Enum                             | Description                               |
| :-------- | :------- | :------ | :------------------------------- | :---------------------------------------- |
| currency  | true     | string  | `BTC` `ETH`                      | The currency symbol                       |
| type      | false    | string  | `settlement` `delivery` `apport` | Settlement type                           |
| count     | false    | integer |                                  | Number of requested items, default - `20` |



**Response**

| Name                     | Type              | Description                                                  |
| :----------------------- | :---------------- | :----------------------------------------------------------- |
| id                       | integer           | The id that was sent in the request                          |
| jsonrpc                  | string            | The JSON-RPC version (2.0)                                   |
| usIn                     | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                    | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                   | integer           | The number of microseconds that was spent handling the request                                                         |
| result                   | *object*          |                                                              |
| › continuation           | string            | Continuation token for pagination.                           |
| › settlements            | array of *object* |                                                              |
| ›  › instrument_name     | string            | instrument name (settlement and delivery only)               |
| ›  › mark_price          | number            | mark price for at the settlement time (in quote currency; settlement and delivery only) |
| ›  › position            | number            | position size (in quote currency; settlement and delivery only) |
| ›  › session_profit_loss | number            | total value of session profit and losses (in base currency)  |
| ›  › timestamp           | integer           | The timestamp (milliseconds since the Unix epoch)            |
| ›  › type                | string            | The type of settlement. `settlement`, `delivery` or `apport`. |

example:

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597134901691,
    "usOut": 1597134901971,
    "usDiff": 280,
    "result": {
        "continuation": "FGluY2x1ZGVfY29udGV4dF91dWlkDXF1ZXJ5QW5kRmV0Y2gBFGp6aW8zSE1CdTg0VzRoZ3ZrcEtZAAAAAAARob4WYmFPNUY2OGlUVW0tR0Z2TkNQa1pCUQ==",
        "settlements": [
            {
                "position": "23",
                "type": "settlement",
                "timestamp": "1597132800009",
                "session_profit_loss": "-24.47",
                "instrument_name": "BTC-14AUG20",
                "mark_price": "11774"
            },
            {
                "position": "0",
                "type": "settlement",
                "timestamp": "1597132800009",
                "session_profit_loss": "-0.0558",
                "instrument_name": "BTC-25DEC20",
                "mark_price": "12216.93"
            }
        ]
    }
}
```



