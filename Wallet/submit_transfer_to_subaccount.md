**URL** 

- `/private/submit_transfer_to_subaccount`

Transfer funds to subaccount.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter   | Required | Type    | Enum | Description                                                  |
| :---------- | :------- | :------ | :--- | :----------------------------------------------------------- |
| currency    | true     | string  |      | The currency symbol                                          |
| count       | false    | integer |      | Number of requested items, default - `10`                    |
| destination | true     | integer |      | Id of destination subaccount. Can be found in `My Account >> Subaccounts` tab |



**Response**

| Name                | Type     | Description                                                  |
| :------------------ | :------- | :----------------------------------------------------------- |
| id                  | integer  | The id that was sent in the request                          |
| jsonrpc             | string   | The JSON-RPC version (2.0)                                   |
| usIn                | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut               | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff              | integer  | The number of microseconds that was spent handling the request                                                         |
| result              | *object* |                                                              |
| › amount            | number   | Amount of funds in given currency                            |
| › created_timestamp | integer  | The timestamp (milliseconds since the Unix epoch)            |
| › currency          | string   | Currency, i.e `"BTC"`, `"ETH"`                               |
| › direction         | string   | Transfer direction                                           |
| › id                | integer  | Id of transfer                                               |
| › other_side        | string   | For transfer from/to subaccount returns this subaccount name, for transfer to other account returns address, for transfer from other account returns that accounts username. |
| › state             | string   | Transfer state, allowed values : `prepared`, `confirmed`, `cancelled`, `waiting_for_admin`, `rejection_reason` |
| › type              | string   | Type of transfer: `user` - sent to user, `subaccount` - sent to subaccount |
| › updated_timestamp | integer  | The timestamp (milliseconds since the Unix epoch)            |

example:

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597133526986,
    "usOut": 1597133527301,
    "usDiff": 315,
    "result": {
        "updated_timestamp": "1597133494226",
        "state": "confirmed",
        "other_side": "sy123_2",
        "id": 39020005324623872,
        "direction": "payment",
        "currency": "BTC",
        "created_timestamp": "1597133494226",
        "amount": "1"
    }
}
```

