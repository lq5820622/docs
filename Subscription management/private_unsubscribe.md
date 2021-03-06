**URL：** 

- `/private/unsubscribe`

Unsubscribe from one or more channels.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter | Required | Type  | Enum | Description                             |
| :-------- | :------- | :---- | ---- | --------------------------------------- |
| channels  | true     | array |      | A list of channels to unsubscribe from. |



**Response**

| **Name** | **Type**        | **Description**                     |
| :------- | :-------------- | ----------------------------------- |
| id       | string          | The id that was sent in the request |
| jsonrpc  | string          | The JSON-RPC version (2.0)          |
| usIn     | integer         | The timestamp when the requests was received (microseconds since the Unix epoch)                           |
| usOut    | integer         | The timestamp when the response was sent (microseconds since the Unix epoch)                          |
| usDiff   | integer         | The number of microseconds that was spent handling the request                                |
| result   | array of string | A list of subscribed channels.      |

request

```json
{ 
  "jsonrpc":"2.0",
  "id": 1,
  "method": "/private/unsubscribe",
   "params":{
       "channels":[
           "user.trades.BTC-14AUG20.raw",
         	 "user.trades.BTC-14AUG20.raw"
       ]
   }
}
```

