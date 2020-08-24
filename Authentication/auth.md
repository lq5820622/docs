**URL** 

- `/public/auth`

**Parameters** 

| Parameter     | Required | Type   | Enum                                                     | Description                                                  |
| :------------ | :------- | :----- | -------------------------------------------------------- | ------------------------------------------------------------ |
| grant_type    | true     | string | `client_credentials ` `client_signature` `refresh_token` | Method of authentication                                     |
| client_id     | true     | tring  |                                                          | Required for grant type `client_credentials` and `client_signature` |
| client_secret | true     | string |                                                          | Required for grant type `client_credentials`                 |
| refresh_token | true     | string |                                                          | Required for grant type `refresh_token`                      |
| signature     | true     | string |                                                          | Required for grant type `client_signature`; it's a cryptographic signature calculated over provided fields using user **secret key**. The signature should be calculated as an HMAC (Hash-based Message Authentication Code) with `SHA256` hash algorithm |



**Response**

| **Name**        | **Type** | **Description**                                          |
| :-------------- | :------- | -------------------------------------------------------- |
| id              | string   | The id that was sent in the request                      |
| jsonrpc         | string   | The JSON-RPC version (2.0)                               |
| usIn            | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                |
| usOut           | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                               |
| usDiff          | integer  | The number of microseconds that was spent handling the request                                                     |
| result          | object   |                                      |
| › access_token  | string   |                                                          |
| › expires_in    | integer  | Token lifetime in seconds                                |
| › refresh_token | string   | Can be used to request a new token (with a new lifetime) |
| › scope         | string   | Type of the access for assigned token                    |
| › token_type    | string   | Authorization type, allowed value - `bearer`             |
|                 |          |                                                          |
|                 |          |                                                          |

example:

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597127926021,
    "usOut": 1597127926052,
    "usDiff": 31,
    "result": {
        "access_token": "ba3avFNzHyIC45NqVmHGOsztEFQafE/ojM9afJMfBMxhLMGMfQqVslIr6syAYbZQtzyoFHaglZB+pvk2jMzOwGPFUbNQzsD88ntzAuo1PQlZ/+uK8GV/NYifFc+j3lfC",
        "token_type": "bearer",
        "refresh_token": "X9VtGUvnWiA6FnTnnBpUnr74eFDlNvJfI8UqCsNknGNkIoYsRFXHhTK87k3ErhWy/sWvzPAjx63jzZnY+yTPTC8Ip8GYHSK29j0teOXcjsA=",
        "expires_in": 43199,
        "scope": "account:read_write block_trade:read_write trade:read_write wallet:read_write"
    }
}
```

