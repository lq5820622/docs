**URL** 

- `/private/create_subaccount`

Create a new subaccount



*This is a private method; it can only be used after authentication.*

**Parameters** 

*This method takes no parameters*



**Response**

| **Name**                | **Type** | **Description**                                              |
| :---------------------- | :------- | ------------------------------------------------------------ |
| id                      | string   | The id that was sent in the request                          |
| jsonrpc                 | string   | The JSON-RPC version (2.0)                                   |
| usIn                    | integer  | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                   | integer  | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                  | integer  | The number of microseconds that was spent handling the request                                                         |
| result                  | object   |                                                              |
| › email                 | string   | User email                                                   |
| › id                    | string   | Subaccount identifier                                        |
| › is_password           | boolean  | `true` when password for the subaccount has been configured  |
| › login_enabled         | boolean  | Informs whether login to the subaccount is enabled           |
| › receive_notifications | boolean  | When `true` - receive all notification emails on the main email |
| › system_name           | string   | System generated user nickname                               |
| › tfa_enabled           | boolean  | Whether the two factor authentication is enabled             |
| › type                  | string   | Account type                                                 |
| › username              | string   | Account name (given by user)                                 |

example:

```json
{
	"id": "74",
	"jsonrpc": "2.0",
	"usIn": 1597128266781,
	"usOut": 1597128267596,
	"usDiff": 815,
	"result": {
		"email": "test@test.com",
		"id": 38998083106902016,
		"is_password": true,
		"login_enabled": false,
		"system_name": "test5",
		"tfa_enabled": false,
		"type": "subaccount",
		"username": "test5"
	}
}
```

