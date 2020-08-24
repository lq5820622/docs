The JSON-RPC API always responds with a JSON object with the following fields.

| Name   | Type         | Description                                                  |
| :----- | :----------- | :----------------------------------------------------------- |
| id     | integer      | This is the same id that was sent in the request.            |
| result | any          | If successful, the result of the API call. The format for the result is described with each method. |
| error  | error object | Only present if there was an error invoking the method. The error object is described below. |
| usIn   | integer      | The timestamp when the requests was received (microseconds since the Unix epoch) |
| usOut  | integer      | The timestamp when the response was sent (microseconds since the Unix epoch) |
| usDiff | integer      | The number of microseconds that was spent handling the request |

