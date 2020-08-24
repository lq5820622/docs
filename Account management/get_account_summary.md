**URL** 

- `/private/get_account_summary`

Retrieves user account summary.



*This is a private method; it can only be used after authentication.*

**Parameters** 

| Parameter | Required | Type   | Enum      | Description |
| :-------- | :------- | :----- | --------- | ----------- |
| currency  | true     | string | `BTC` `ETH` `MARGIN` | The currency symbol |



**Response**

| **Name**                                  | **Type**          | **Description**                                       |
| :-----------------------------------------| :---------------- | ------------------------------------------------      |
| id                                        | string            | The id that was sent in the request                   |
| jsonrpc                                   | string            | The JSON-RPC version (2.0)                            |
| usIn                                      | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                        |
| usOut                                     | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                       |
| usDiff                                    | integer           | The number of microseconds that was spent handling the request                                             |
| result                                    | object            |                                                       |
| › email                                   | string            | User email                                            |
| › id                                      | string            | Account id                                            |
| › system_name                             | string            | System generated user nickname                        |
| › tfa_enabled                             | boolean           | Whether the two factor authentication is enabled      |
| › type                                    | boolean           | Account type                                          |
| › username                                | string            | Account name (given by user)                          |
| › available_funds                         | string            | The account's available funds                         |
| › available_withdrawal_funds              | string            | The account's available to withdrawal funds           |
| › balance                                 | string            | The account's balance                                 |
| › currency                                | string            | The currency the fee applies to                       |
| › user_id                                 | string            |                                                       |
| › equity                                  | string            | The account's current equity                          |
| › futures_pl                              | string            | Futures profit and Loss                               |
| › futures_session_rpl                     | string            | Futures session realized profit and Loss              |
| › futures_session_upl                     | string            | Futures session unrealized profit and Loss            |
| › initial_margin                          | string            | The account's initial margin                          |
| › maintenance_margin                      | string            | The maintenance margin.                               |
| › options_delta                           | string            | Options summary delta                                 |
| › options_gamma                           | string            | Options summary gamma                                 |
| › options_session_rpl                     | string            | Options session realized profit and Loss              |
| › options_session_upl                     | string            | Options session unrealized profit and Loss            |
| › options_theta                           | string            | Options summary theta                                 |
| › options_value                           | string            | Options value                                         |
| › options_vega                            | string            | Options summary vega                                  |
| › session_funding                         | string            | Session funding                                       |
| › session_rpl                             | string            | Session realized profit and loss                      |
| › session_upl                             | string            | Session unrealized profit and loss                    |
| › total_pl                                | string            | Profit and loss                                                 |
| › delta_total                             | string            | The sum of position deltas                                                 |
| › cushion_rate                            | string            | Risk level of margin                                                 |
| › total                                   | string            | Total assets of margin                                                 |
| › interest_owed                           | string            | Interest of margin                                                 |
| › net                                     | string            | Net assets of margin                                                 |
| › available                               | string            | Available assets of margin                                              |
| › borrowed                                | string            | Available borrowing assets of margin                  |
| › wallet_asset                            | array of *object* |                                                  |
| ›  › currency                             | string            | Currency                                                 |
| ›  › count                                | string            | Available amount                                                |
| ›  › frozen                               | string            | Frozen amount                                                 |
| ›  › usdt_value                           | string            |                                                  |
| ›  › mark_price                           | string            | Current currency mark price                                                 |
| › margin_asset                            | array of *object* |                                                  |
| ›  › coin_type                            | string            | Currency                                                 |
| ›  › total                                | string            | Total assets in current currency                                                |
| ›  › available                            | string            | Amount available in current currency                                                 |
| ›  › borrowed                             | string            | Borrowed amount in current currency                                                 |
| ›  › interest_owed                        | string            | Amount of interest in current currency                                                 |
| ›  › freeze                               | string            | Frozen amount in current currency                                                 |
| ›  › coin_leverage                        | string            | Maximum leverage multiple of current currency                                                 |
| ›  › debt                                 | string            | Total liabilities in current currency                                                 |
| ›  › max_transfer                         | string            | The maximum transfer out amount of current currency    |
| ›  › current_mark_price                   | string            | Current currency mark price                                              |
| ›  › net                                  | string            | Net assets in current currency                                                |
| ›  › canborrow                            | string            | Available borrowing amount in current currency                                            |
| ›  › daily_interest_rate                  | string            | Daily interest rate of current currency                                                |

example:

MARGIN

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597128354425,
    "usOut": 1597128354473,
    "usDiff": 48,
    "result": {
        "currency": "MARGIN",
        "email": "test@test.com",
        "id": "37257268672204800",
        "system_name": "test",
        "tfa_enabled": false,
        "type": "main",
        "username": "test",
        "delta_total": "0",
        "margin_asset": [
            {
                "coin_type": "BTC",
                "total": "0.99",
                "available": "0.99",
                "borrowed": "0",
                "interest_owed": "0",
                "freeze": "0",
                "coin_leverage": "10",
                "debt": "0",
                "max_transfer": "0.99",
                "current_mark_price": "11767.622",
                "net": "0.99",
                "canborrow": "8.99909689",
                "daily_interest_rate": "0"
            },
            {
                "coin_type": "ETH",
                "total": "0",
                "available": "0",
                "borrowed": "0",
                "interest_owed": "0",
                "freeze": "0",
                "coin_leverage": "5",
                "debt": "0",
                "max_transfer": "0",
                "current_mark_price": "391.547",
                "net": "0",
                "canborrow": "120.20463615",
                "daily_interest_rate": "0"
            },
            {
                "coin_type": "USDT",
                "total": "116.495388",
                "available": "116.495388",
                "borrowed": "0",
                "interest_owed": "0",
                "freeze": "0",
                "coin_leverage": "10",
                "debt": "0",
                "max_transfer": "116.495388",
                "current_mark_price": "1",
                "net": "116.495388",
                "canborrow": "105897.970512",
                "daily_interest_rate": "0"
            }
        ],
        "cushion_rate": "0",
        "total": "11766.441168",
        "interest_owed": "0",
        "net": "11766.441168",
        "available": "11766.441168",
        "borrowed": "0",
        "wallet_asset": [
            {
                "currency": "BTC",
                "count": "0",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "11762.575"
            },
            {
                "currency": "ETH",
                "count": "30",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "391.5625"
            },
            {
                "currency": "USDT",
                "count": "904899",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "1"
            }
        ]
    }
}
```

BTC

```json
{
    "id": "1",
    "jsonrpc": "2.0",
    "usIn": 1597128450907,
    "usOut": 1597128450951,
    "usDiff": 44,
    "result": {
        "available_funds": "94448.95",
        "available_withdrawal_funds": "94448.95",
        "balance": "94472.81",
        "currency": "BTC",
        "email": "test@test.com",
        "equity": "94472.77",
        "futures_pl": "0.01",
        "futures_session_rpl": "0",
        "futures_session_upl": "-0.04",
        "id": "37257268672204800",
        "initial_margin": "23.83",
        "maintenance_margin": "18.33",
        "margin_balance": "94472.77",
        "options_delta": "0",
        "options_gamma": "0",
        "options_pl": "0",
        "options_session_rpl": "0",
        "options_session_upl": "0",
        "options_theta": "0",
        "options_value": "0",
        "options_vega": "0",
        "session_funding": "0",
        "session_rpl": "0",
        "session_upl": "-0.04",
        "system_name": "test",
        "tfa_enabled": false,
        "total_pl": "0.01",
        "type": "main",
        "username": "test",
        "delta_total": "0.01",
        "cushion_rate": "0",
        "total": "0",
        "interest_owed": "0",
        "net": "0",
        "available": "0",
        "borrowed": "0",
        "wallet_asset": [
            {
                "currency": "BTC",
                "count": "0",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "11769.2316848"
            },
            {
                "currency": "ETH",
                "count": "30",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "391.935"
            },
            {
                "currency": "USDT",
                "count": "904899",
                "frozen": "0",
                "usdt_value": "0",
                "mark_price": "1"
            }
        ]
    }
}
```

