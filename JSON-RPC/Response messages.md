According to the JSON-RPC sepcification the requests must be JSON objects with the following fields.

| Name    | Type              | Description                                                  |
| :------ | :---------------- | :----------------------------------------------------------- |
| jsonrpc | string            | The version of the JSON-RPC spec: "2.0"                      |
| id      | integer or string | An identifier of the request. If it is included, then the response will contain the same identifier |
| method  | string            | The method to be invoked                                     |
| params  | object            | The parameters values for the method. The field names must match with the expected parameter names. The parameters that are expected are described in the documentation for the methods, below. |

