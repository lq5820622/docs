API users can subscribe to certain types of notifications. This means that they will receive JSON-RPC notification-messages from the server when certain events occur, such as changes to the index price or changes to the order book for a certain instrument.

The API methods `public/subscribe` and `private/subscribe` are used to set up a subscription. Since HTTP does not support the sending of messages from server to client, these methods are only availble when using the Websocket transport mechanism.

At the moment of subscription a "channel" must be specified. The channel determines the type of events that will be received. See [Subscriptions] for more details about the channels.

In accordance with the JSON-RPC specification, the format of a notification is that of a request message without an `id` field. The value of the `method` field will always be `"subscription"`. The `params` field will always be an object with 2 members: `channel` and `data`. The value of the `channel` member is the name of the channel (a string). The value of the `data` member is an object that contains data that is specific for the channel.
