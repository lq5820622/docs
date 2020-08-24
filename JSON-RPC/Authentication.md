The API consists of `public` and `private` methods. The public methods do not require authentication. The private methods use OAuth 2.0 authentication. This means that a valid OAuth access token must be included in the request, which can be achived by calling method `public/auth`

When the token was assigned to the user, it should be passed along, with other request parameters, back to the server:

| Connection type | Access token placement                                     |
| :-------------- | :--------------------------------------------------------- |
| **Websocket**   | Inside request JSON parameters, as an `access_token` field |
| **HTTP (REST)** | Header `Authorization: bearer``Token``` value              |

### Additional authorization method - basic user credentials

**! Not recommended - however, it could be useful for quick testing API**

Every `private` method could be accessed by providing, inside HTTP `Authorization: Basic XXX` header, values with user `ClientId` and assigned `ClientSecret` (both values can be found on the API page on the Derinow website) encoded with `Base64`:

```
Authorization: Basic BASE64(ClientId + : + ClientSecret)
```

### Access scope

When asking for `access token` user can provide the required access level (called `scope`) which defines what type of functionality he/she wants to use, and whether requests are only going to check for some data or also to update them. Scopes are required and checked for `private` methods, so if you plan to use only `public` information you can stay with values assigned by default.

| Scope                                       | Description                                                  |
| :------------------------------------------ | :----------------------------------------------------------- |
| *account:read*                              | Access to **account** methods - read only data.              |
| *account:read_write*                        | Access to **account** methods - allows to manage account settings, add subaccounts, etc. |
| *trade:read*                                | Access to **trade** methods - read only data.                |
| *trade:read_write*                          | Access to **trade** methods - required to create and modify orders. |
| *wallet:read*                               | Access to **wallet** methods - read only data.               |
| *wallet:read_write*                         | Access to **wallet** methods - allows to withdraw, generate new deposit address, etc. |
| *wallet:none*, *account:none*, *trade:none* | Blocked access to specified functionality.                   |
| *block_trade:read*                          | Access to **block_trade** methods - reading info about block trades - read only data. |
| *block_trade:read_write*                    | Access to **block_trade** methods - required to create block trades. |

**NOTICE:** Depending on choosing an authentication method (`grant type`) some scopes could be narrowed by the server or limited by user API key configured scope, e.g. when `grant_type = client_credentials` and `scope = wallet:read_write` could be modified by the server as `scope = wallet:read`.

**The user shouldn't assume that requested values are blindly accepted and should verify assigned scoped.**