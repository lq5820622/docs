**URL** 

- `/private/cancel_all_by_currency`

Cancels all orders by currency, optionally filtered by instrument kind and/or order type.



*This is a private method; it can only be used after authentication.*

*This is a matching engine method.*

**Parameters** 

| Parameter | Required | Type   | Enum              | Description                                                  |
| :-------- | :------- | :----- | :---------------- | :----------------------------------------------------------- |
| currency  | true     | string | `BTC` `ETH` `MARGIN` | The currency symbol                                          |
| kind      | false    | string | `future` `option` `margin`| Instrument kind, if not provided instruments of all kinds are considered |
| type      | false    | string | `all` `limit`              | Order type - limit, stop or all, default - `all`             |



**Response**

| Name    | Type    | Description                                   |
| :------ | :------ | :-------------------------------------------- |
| id      | integer | The id that was sent in the request           |
| jsonrpc | string  | The JSON-RPC version (2.0)                    |
| usIn    | integer | The timestamp when the requests was received (microseconds since the Unix epoch)                                     |
| usOut   | integer | The timestamp when the response was sent (microseconds since the Unix epoch)                                    |
| usDiff  | integer | The number of microseconds that was spent handling the request                                          |
| result  | string  | Total number of successfully cancelled orders |



