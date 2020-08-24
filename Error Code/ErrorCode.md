

| code | short_msg  | desc |
| ---- | ---- | ---- |
| 9999 | SYSTEM_INNER_ERROR | System error, please try again later |
| 9900 | SERVICE_BUSY | Service is busy，please try again later |
|  |  |  |
| 401 | UNAUTHENTICATION_ERROR | UnAuthentication |
| 403 | ACCESS_DENIED_ERROR | Access denied |
|  |  |  |
| 1000 | NO_SERVICE | No service found |
| 1001 | BAD_REQUEST | Bad requested |
| | | |
| 2000 | NEED_LOGIN | Login is required |
| 2001 | ACCOUNT_NOT_MATCH | Account information does not match |
| 2002 | ACCOUNT_NEED_ENABLE | Account needs to be activated |
| 2003 | ACCOUNT_NOT_AVAILABLE | Account not available |
|  |  |  |
| 3000 | TEST | user |
| 3002 | NICKNAME_EXIST | Nicknames exist |
| 3003 | ACCOUNT_NOT_EXIST | No account |
| 3004 | PARAM_ERROR | Parameter exception |
| 3005 | LANGUAGE_NONSUPPORT | Unsupported languages |
| 3007 | ONLY_SUBACCOUNT_OPE | Sub-account operations only |
| 3008 | LOGIN_ENABLE | Account not logged |
| 3009 | TFA_EXPIRE_ERROR | Google key failed |
| 3011 | PASSWORD_ERROR | Password error |
| 3012 | TFA_UUID_ERROR | One-time unlock code error |
| 3013 | TIME_OUT | time out |
| 3015 | ID_IS_ERROR | id_is_error |
| 3016 | WRONG_SUBACCOUNT_NAME | already taken |
| 3018 | USER_NAME_AT_LEAST_5_BYTE | The user name must have at least 5 digits |
| 3019 | PASSWORD_AT_LEAST_8_BYTE | 8-32 bits contain at least three of the numbers, capital, lowercase letters and special symbols! |
| 3020 | TFA_ALREADY_SET | GoogleCode Already Set |
| 3021 | PWD_MATCH_ERROR | pwd_match_error |
| 3022 | ILLEGAL_OPERATION | illegal operation |
| 3023 | REMOVE_SUBACCOUNT_OVER_LIMIT | remove subaccount over limit |
| 3024 | GOOGLE_VERIFICATION_CODE_TURNED_ON | Google verification code turned on |
| 3025 | OPERATION_FAILURE | The operation failure |
| 3026 | ACCOUNT_ACTIVED | Account has Actived |
| 3027 | INVALID_EMAIL_ADDRESS | Invalid email address! |
| 3028 | PASSWORD_FORMAT_ERROR | Password format err |
| 3029 | ONE_MINUTE_LIMIT | Only one operation per minute and the remaining ${times}s |
| 3030 | ONE_HOUR_LIMIT | Do this up to 5 times per hour |
| 3031 | USER_NAME_UP_12_BYTE | Up to 12 characters, only letters and numbers are supported |
| 3032 | EMAIL_SETTED | You need to set email address and password first |
| 3033 | PASSWORD_SETTED | You need to set password first |
| 3034 | SUBACCOUNT_EMAIL_ACTIVATE | You need to wait for email confirmation |
| 3035 | API_NOT_EXIST | No api message |
| 3036 | UNAVAILABLE_IN_SUBACCOUNT | Unavailable in subaccount |
| 3037 | MAX_SUBACCOUNT_NUMBER | Limit of subaccounts is reached |
| 3038 | MAIN_SUBACCOUNT_EMAIL_SAME | Provided email address is already used for your other subaccount |
| 3039 | MAX_API_KEY_NUMBER | You cannot have more than 8 API keys |
| 3040 | ALPHA_TEST | Non-invited users shall contact Derinow Team to obtain the internal tests qualification |
| 3041 | API_NAME_MAX_LENGTH | Name of key maximum length - 16 characters |
|  |  |  |
| 4000 | WALLET_ERROR | Wallet error |
| 4000 | RECHARGE_CLOSED | Recharge closed |
| 4001 | WRONG_WITHDRAWAL_ADDRESS | Wrong withdrawal address |
| 4002 | ADDRESS_DOES_NOT_EXIST | Address does not exist |
| 4003 | WITHDRAWAL_CLOSED | Withdrawal closed |
| 4003 | TOO_SMALL_WITHDRAWAL_AMOUNT | Too small withdrawal amount |
| 4004 | INTERNAL_TRANSFER_IS_NOT_SUPPORTED_TEMPORARILY | Internal transfer is not supported temporarily |
| 4005 | WITHDRAW_FAIL | Withdrawal failed |
| 4006 | INSUFFICIENT_ASSET | ser asset not enough |
| 4007 | TRANSFER_ACCOUNT_ERROR | Transfer account error |
| 4008 | AMOUNT_ERROR | Amount error |
| 4009 | NO_RECHARGE_ADDRESS | No recharge address |
| 4010 | GET_TRANSFER_SUBACCOUNT_ERROR | Get transfer subaccount error |
| 4011 | TRANSFER_SUBMIT_URL_ERROR | Transfer submit url error |
|  |  |  |
| 5001 | ORDER_PARAM_WRONG | Order's param wrong. |
| 5002 | ORDER_DOSE_NOT_EXIST | Order does not exist. |
| 5003 | CONTRACT_DOSE_NOT_EXIST | Contract does not exist. |
| 5004 | ORDER_STATUS_ERR | Order status error. |
| 5005 | ORDER_AMOUNT_MIN_TRANCSACTION_ERR | Order amount min transaction error. |
| 5006 | ORDER_PRICE_MIN_TRANCSACTION_ERR | Order price min price error. |
| 5007 | ORDER_PRICE_TICK_SIZE_ERR | Order price tick size error. |
| 5008 | ORDER_TYPE_ERR | Order type error. |
| 5009 | ORDER_OPTION_IS_EXPIRED | Order option is expired. |
| 5010 | ORDER_IS_NOT_ACTIVE | Order is not active. |
| 5011 | IV_ORDER_ARE_NOT_SUPPORTED | Iv orders are not supported. |
| 5012 | ORDER_NO_MARK_PRICE_ERROR | No mark price error. |
| 5013 | ORDER_PRICE_RANGE_IS_TOO_HIGH | order price range is too high. |
| 5014 | ORDER_PRICE_RANGE_IS_TOO_LOW | Order price range is too low. |
|  |  |  |
| 5901 | TRANSFER_RESULT | transfer out success. |
| 5902 | ORDER_SUCCESS | place order success. |
| 5903 | ORDER_FAIL | place order fail. |
| 5904 | PRICE_TRIGGER_LIQ | price trigger liquidation |
| 5905 | LIQ_CANCEL | liquidation make order cancel. |
| 5906 | LIQ_ORDER | liquidation place a new order |
| 5907 | ASSET_NOT_ENOUTH | asset not enough |
|  |  |  |
| 8000 | PARAM_ERROR | Request params not valid! |
| 8001 | DATA_NOT_EXIST | The data doesn't exist! |
| 8100 | CODE_CHECK_FAIL | Incorrect verification code |
| 8101 | CODE_NOT_EXIST | Verification code time out, please retry later |
| 8102 | CODE_CHECK_FAIL_LIMIT | Errors exceed the limit. Please try again after 24H. |
| 8103 | SMS_CODE_CHECK_FAIL | Incorrect SMS verification code |
| 8104 | MAIL_CODE_CHECK_FAIL | Incorrect mail verification code |
| 8105 | GOOGLE_CODE_CHECK_FAIL | 2FA Code error! |
| 8106 | SMS_CODE_LIMIT | Your message service is over limit today, please try tomorrow |
| 8107 | REQUEST_FAILED | Request failed |
|  |  |  |
| 11000 | CHANNEL_REGEX_ERROR | channel regex not match |




