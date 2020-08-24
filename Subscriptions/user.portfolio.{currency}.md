## user.portfolio.{currency}

Get the asset information of users in each trading area, including wallet assets.

 This is a private subscription; subscribing is only possible when authenticated.

### **Parameters** 

| Parameter | Required | Type   | Enum           | Description         |
| :-------- | :------- | :----- | :------------- | :------------------ |
| currency  | true     | string | `BTC` `MARGIN` | The currency symbol |

### Response

| Name                           | Type     | Description                                                  |
| :----------------------------- | :------- | :----------------------------------------------------------- |
| data                           | *object* |                                                              |
| › available_funds              | number   | The account's available funds                                |
| › available_withdrawal_funds   | number   | The account's available to withdrawal funds                  |
| › balance                      | number   | The account's balance                                        |
| › currency                     | string   | The selected currency                                        |
| › delta_total                  | number   | The sum of position deltas                                   |
| › equity                       | number   | The account's current equity                                 |
| › futures_pl                   | number   | Futures profit and Loss                                      |
| › futures_session_rpl          | number   | Futures session realized profit and Loss                     |
| › futures_session_upl          | number   | Futures session unrealized profit and Loss                   |
| › initial_margin               | number   | The account's initial margin                                 |
| › maintenance_margin           | number   | The maintenance margin.                                      |
| › margin_balance               | number   | The account's margin balance                                 |
| › options_delta                | number   | Options summary delta                                        |
| › options_gamma                | number   | Options summary gamma                                        |
| › options_pl                   | number   | Options profit and Loss                                      |
| › options_session_rpl          | number   | Options session realized profit and Loss                     |
| › options_session_upl          | number   | Options session unrealized profit and Loss                   |
| › options_theta                | number   | Options summary theta                                        |
| › options_value                | number   | Options value                                                |
| › options_vega                 | number   | Options summary vega                                         |
| › session_funding              | number   | Session funding                                              |
| › session_rpl                  | number   | Session realized profit and loss                             |
| › session_upl                  | number   | Session unrealized profit and loss                           |
| › total_pl                     | number   | Profit and loss                                              |
| › wallet_asset             | Object | Wallet asset details |
| ›› currency                | number | Asset currency |
| ›› count                   | number | Available amount |
| ›› frozen                  | number | Frozen amount |
| ›› mark_price              | number | Exchange rate of current currency to usdt |
| › cushion_rate | number | Risk Level (margin only) |
| › total | number | Total assets in USDT (margin only) |
| › interest_owed | number | Total interest in usdt (margin only) |
| › net | number | Net assets in usdt (margin only) |
| › available | number | Available assets in usdt (margin only) |
| › borrowed | number | Borrowed amount in usdt (margin only) |
| › margin_asset             | Object | Margin asset details(margin only) |
| ›› coin_type               | number | Currency |
| ›› total                   | number | Total assets in current currency |
| ›› available               | number | Amount available in current currency |
| ›› borrowed                | number | Borrowed amount in current currency |
| ›› interest_owed           | number | Amount of interest in current currency |
| ›› freeze                  | number | Frozen amount in current currency |
| ›› coin_leverage           | number | Maximum leverage multiple of current currency |
| ›› debt                    | number | Total liabilities in current currency |
| ›› max_transfer            | number | The maximum transfer out amount of current currency |
| ›› current_mark_price      | number | Current currency mark price |
| ›› net                     | number | Net assets in current currency |
| ›› canborrow               | number | Available borrowing amount in current currency |
| ›› daily_interest_rate     | number | Daily interest rate of current currency |



example:

MARGIN

```json
{
  "jsonrpc": "2.0",
  "method": "subscription",
  "params": {
    "channel": "user.portfolio.MARGIN",
    "data": {
      "cushion_rate": "2.23",
      "total": "1580.13094943",
      "interest_owed": "1.37825781",
      "net": "1109.95751465",
      "available": "1580.13094943",
      "borrowed": "468.79517697",
      "margin_asset": [
        {
          "coin_type": "BTC",
          "total": "0.14067902",
          "available": "0.14067902",
          "borrowed": "0",
          "interest_owed": "0",
          "freeze": "0",
          "coin_leverage": "10",
          "debt": "0",
          "max_transfer": "0.09221009",
          "current_mark_price": "11232.172",
          "net": "0.14067902",
          "canborrow": "0.84751589",
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
          "current_mark_price": "388.896",
          "net": "0",
          "canborrow": "10.87916586",
          "daily_interest_rate": "0"
        },
        {
          "coin_type": "USDT",
          "total": "0",
          "available": "0",
          "borrowed": "468.79517697",
          "interest_owed": "1.37825781",
          "freeze": "0",
          "coin_leverage": "10",
          "debt": "470.17343478",
          "max_transfer": "0",
          "current_mark_price": "1",
          "net": "0",
          "canborrow": "9519.4441971",
          "daily_interest_rate": "0"
        }
      ],
      "wallet_asset": [
        {
          "currency": "BTC",
          "count": "0",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "11239.5475"
        },
        {
          "currency": "ETH",
          "count": "0",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "387.67249999"
        },
        {
          "currency": "USDT",
          "count": "34800",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "1"
        }
      ]
    }
  }
}
```

BTC:

```json
{
  "jsonrpc": "2.0",
  "method": "subscription",
  "params": {
    "channel": "user.portfolio.BTC",
    "data": {
      "available_funds": "4792.65",
      "available_withdrawal_funds": "4792.65",
      "balance": "4864.69",
      "equity": "4916.64",
      "futures_pl": "3.95",
      "futures_session_rpl": "0",
      "futures_session_upl": "0",
      "initial_margin": "72.04",
      "maintenance_margin": "0",
      "options_delta": "0.0977",
      "options_gamma": "0",
      "options_pl": "13.95",
      "options_session_rpl": "0",
      "options_session_upl": "13.95",
      "options_theta": "0",
      "options_value": "51.95",
      "options_vega": "0.054",
      "session_funding": "0",
      "session_rpl": "0",
      "session_upl": "13.95",
      "total_pl": "17.9",
      "delta_total": "0.097",
      "wallet_asset": [
        {
          "currency": "BTC",
          "count": "0",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "11170.37733006"
        },
        {
          "currency": "ETH",
          "count": "0",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "387.64067037"
        },
        {
          "currency": "USDT",
          "count": "34800",
          "frozen": "0",
          "usdt_value": "0",
          "mark_price": "1"
        }
      ]
    }
  }
}
```

