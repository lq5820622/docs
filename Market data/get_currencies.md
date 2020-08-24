**URL** 

- `/public/get_currencies`

Retrieves all cryptocurrencies supported by the API.



**Parameters** 

*This method takes no parameters*

**Response**

| Name                    | Type              | Description                                                  |
| :---------------------- | :---------------- | :----------------------------------------------------------- |
| id                      | integer           | The id that was sent in the request                          |
| jsonrpc                 | string            | The JSON-RPC version (2.0)                                   |
| usIn                    | integer           | The timestamp when the requests was received (microseconds since the Unix epoch)                                                    |
| usOut                   | integer           | The timestamp when the response was sent (microseconds since the Unix epoch)                                                   |
| usDiff                  | integer           | The number of microseconds that was spent handling the request                                                         |
| result                  | array of *object* |                                                              |
| › currency              | string            | The abbreviation of the currency. This abbreviation is used elsewhere in the API to identify the currency. |
| › currency_long         | string            | The full name for the currency.                              |
| › fee_precision         | integer           | fee precision                                                |
| › min_confirmations     | integer           | Minimum number of block chain confirmations before deposit is accepted. |
| › min_withdrawal_fee    | string            | The minimum transaction fee paid for withdrawals             |
| › withdrawal_fee        | number            | The total transaction fee paid for withdrawals               |
| › block_chain_explorers | string            | Address of blockchain browse            |
| › min_draw_limit        | number            | Min withdrawal amount            |
| › min_deposit_limit     | number            | Min deposit amount           |
| › regular               | string            | Regular expression of withdrawal address            |
| › memo_regular          | string            | Regular expression of memo            |
| › recharge_status       | boolean           | Deposit status            |
| › withdraw_status       | boolean           | Withdrawal status            |
| › memo_status           | boolean           | Is there a memo            |
| › memo_name             | string            | The name of the memo or tag            |
| › max_lever             | integer           | Maximum leverage multiple of current currency            |
| ›› list                 | object            |             |

example:

```json
{
	"id": "0",
	"jsonrpc": "2.0",
	"usIn": 1597129154031,
	"usOut": 1597129154045,
	"usDiff": 14,
	"result": [{
		"currency": "BTC",
		"currency_long": "Bitcoin",
		"min_confirmations": 2,
		"block_chain_explorers": "https://btc.com/{##}",
		"min_draw_limit": "0.001",
		"min_deposit_limit": "0.0001",
		"regular": "^[13][a-km-zA-HJ-NP-Z0-9]{26,33}$",
		"recharge_status": false,
		"withdraw_status": false,
		"memo_status": false,
		"memo_name": "no",
		"withdrawal_fee": "0",
		"max_lever": 10
	}, {
		"currency": "ETH",
		"currency_long": "ETH",
		"min_confirmations": 12,
		"block_chain_explorers": "https://etherscan.io/tx/{##}",
		"min_draw_limit": "1",
		"min_deposit_limit": "1",
		"regular": "^0x[a-fA-F0-9]{40}$",
		"recharge_status": false,
		"withdraw_status": false,
		"memo_status": false,
		"memo_name": "no",
		"withdrawal_fee": "0.1",
		"max_lever": 5
	}, {
		"currency": "USDT",
		"list": [{
			"currency": "USDT",
			"currency_long": "USDT",
			"min_confirmations": 2,
			"block_chain_explorers": "https://omniexplorer.info/tx/",
			"min_draw_limit": "20",
			"min_deposit_limit": "1",
			"regular": "^([13][a-km-zA-HJ-NP-Z0-9]{26,33})|((bc1)[a-zA-HJ-NP-Z0-9]{25,39})$",
			"recharge_status": false,
			"withdraw_status": false,
			"memo_status": false,
			"memo_name": "no",
			"withdrawal_fee": "0",
			"max_lever": 10
		}, {
			"currency": "USDT-ERC20",
			"currency_long": "Tether USD",
			"min_confirmations": 12,
			"block_chain_explorers": "https://etherscan.io/tx/{##}",
			"min_draw_limit": "2",
			"min_deposit_limit": "0.1",
			"regular": "^0x[a-fA-F0-9]{40}$",
			"recharge_status": false,
			"withdraw_status": false,
			"memo_status": false,
			"memo_name": "no",
			"withdrawal_fee": "0",
			"max_lever": 10
		}, {
			"currency": "USDT-TRC20",
			"currency_long": "Tether USD (USDT)",
			"min_confirmations": 36,
			"block_chain_explorers": "https://tronscan.org/#/transaction/{##}",
			"min_draw_limit": "0",
			"min_deposit_limit": "1",
			"regular": "^[T][a-km-zA-HJ-NP-Z1-9]{25,34}$",
			"recharge_status": false,
			"withdraw_status": false,
			"memo_status": false,
			"memo_name": "no",
			"withdrawal_fee": "0",
			"max_lever": 10
		}]
	}]
}
```






