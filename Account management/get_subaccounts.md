**URL** 

- `/private/get_subaccounts`

Get information about subaccounts



*This is a private method; it can only be used after authentication.*

**Parameters** 

*This method takes no parameters*



**Response**

| **Name**                | **Type**          | **Description**                                              |
| :---------------------- | :---------------- | ------------------------------------------------------------ |
| id                      | string            | The id that was sent in the request                          |
| jsonrpc                 | string            | The JSON-RPC version (2.0)                                   |
| usIn                    | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                   | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                  | integer           | The number of microseconds that was spent handling the request                                                         |
| result                  | array of *object* |                                                              |
| › email                 | string            | User email                                                   |
| › id                    | string            | Subaccount identifier                                        |
| › is_password           | boolean           | `true` when password for the subaccount has been configured  |
| › login_enabled         | boolean           | Informs whether login to the subaccount is enabled           |
| › receive_notifications | boolean           | When `true` - receive all notification emails on the main email |
| › system_name           | string            | System generated user nickname                               |
| › tfa_enabled           | boolean           | Whether the two factor authentication is enabled             |
| › type                  | string            | Account type                                                 |
| › username              | string            | Account name (given by user)                                 |

example:

```json
{
	"id": "75",
	"jsonrpc": "2.0",
	"usIn": 1597128267735,
	"usOut": 1597128267746,
	"usDiff": 11,
	"result": [{
		"email": "test@test.com",
		"id": "37257268672204800",
		"is_password": true,
		"login_enabled": true,
		"receive_notifications": false,
		"system_name": "test",
		"tfa_enabled": false,
		"type": "main",
		"username": "test"
	}, {
		"email": "test@test.com",
		"id": "37270169109794816",
		"is_password": false,
		"login_enabled": false,
		"receive_notifications": false,
		"system_name": "test",
		"tfa_enabled": false,
		"type": "subaccount",
		"username": "test"
	}]
}
```

