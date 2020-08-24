**URL** 

- `/private/set_email_language`

Changes the language to be used for emails.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter | Required | Type   | Enum | Description                                                  |
| :-------- | :------- | :----- | ---- | ------------------------------------------------------------ |
| language  | true     | string |      | The abbreviated language name. Valid values include `"en-us"` |



**Response**

| **Name** | **Type** | **Description**                                     |
| :------- | :------- | --------------------------------------------------- |
| id       | string   | The id that was sent in the request                 |
| jsonrpc  | string   | The JSON-RPC version (2.0)                          |
| usIn     | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                           |
| usOut    | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                          |
| usDiff   | integer  | The number of microseconds that was spent handling the request                                                |
| result   | string   | Result of method execution. `ok` in case of success |

example:

```json
{
	"id": "264",
	"jsonrpc": "2.0",
	"usIn": 1597128982211,
	"usOut": 1597128982991,
	"usDiff": 780,
	"result": "ok"
}
```

