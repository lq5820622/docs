**URL** 

- `/private/list_api_keys`

Retrieves list of api keys



*This is a private method; it can only be used after authentication.*

**Parameters** 

*This method takes no parameters*

**Response**

| **Name**        | **Type**          | **Description**                                              |
| :-------------- | :---------------- | ------------------------------------------------------------ |
| id              | string            | The id that was sent in the request                          |
| jsonrpc         | string            | The JSON-RPC version (2.0)                                   |
| usIn            | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut           | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff          | integer           | The number of microseconds that was spent handling the request                                                         |
| result          | array of *object* |                                                              |
| › client_id     | string            | Client identifier used for authentication                    |
| › client_secret | string            | Client secret used for authentication                        |
| › default       | boolean           | Informs whether this api key is default (default one is used for api console or trading view) |
| › enabled       | boolean           | Informs whether api key is enabled and can be used for authentication |
| › id            | integer           | key identifier                                               |
| › max_scope     | string            | Describes maximal access for tokens generated with given key, possible values: `trade:[read, read_write, none]`, `wallet:[read, read_write, none]`, `account:[read, read_write, none]`, `block_trade:[read, read_write, none]`. If scope is not provided, it value is set as none. |
| › name          | string            | Api key name that can be displayed in transaction log        |
| › timestamp     | integer           | The timestamp (milliseconds since the Unix epoch)            |
| › ip_whitelist     | array of *string*   |    IP address                                 |

example:

```json
{
	"id": "11",
	"jsonrpc": "2.0",
	"usIn": 1597127976248,
	"usOut": 1597127976286,
	"usDiff": 38,
	"result": [{
		"timestamp": "1596837665180",
		"max_scope": "account:read_write,block_trade:read_write,trade:read_write,wallet:read_write",
		"id": 124,
		"enabled": true,
		"client_secret": "a07d4394b4ed7b8f7567432c",
		"client_id": "b2b76b28",
		"name": "test",
		"ip_whitelist": [],
		"default": true
	}]
}
```

