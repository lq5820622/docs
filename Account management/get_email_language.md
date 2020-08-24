**URL** 

- `/private/get_email_language`

Retrieves the language to be used for emails.



*This is a private method; it can only be used after authentication.*

**Parameters** 

*This method takes no parameters*



**Response**

| **Name** | **Type** | **Description**                     |
| :------- | :------- | ----------------------------------- |
| id       | string   | The id that was sent in the request |
| jsonrpc  | string   | The JSON-RPC version (2.0)          |
| usIn     | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                           |
| usOut    | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                          |
| usDiff   | integer  | The number of microseconds that was spent handling the request                                |
| result   | string   | The abbreviation of the language    |

example:

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597128657076,
    "usOut": 1597128657091,
    "usDiff": 15,
    "result": "en-us"
}
```

