# GetCurrencies

## DESCRIPTION
This command returns a list of the currencies, which are supported in the system.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetCurrencies` | COMMAND

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CURRENCY[0..N] | 0 | N | ISO 4217 currency code | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetCurrencies
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CURRENCY][0] = AUD
PROPERTY[CURRENCY][1] = BGN
PROPERTY[CURRENCY][2] = BRL
PROPERTY[CURRENCY][3] = CAD
PROPERTY[CURRENCY][4] = CHF
PROPERTY[CURRENCY][5] = CNY
PROPERTY[CURRENCY][6] = CZK
PROPERTY[CURRENCY][7] = DKK
PROPERTY[CURRENCY][8] = GBP
PROPERTY[CURRENCY][9] = HKD
PROPERTY[CURRENCY][10] = HRK
PROPERTY[CURRENCY][11] = HUF
PROPERTY[CURRENCY][12] = IDR
PROPERTY[CURRENCY][13] = ILS
PROPERTY[CURRENCY][14] = INR
PROPERTY[CURRENCY][15] = JPY
PROPERTY[CURRENCY][16] = KRW
PROPERTY[CURRENCY][17] = MXN
PROPERTY[CURRENCY][18] = MYR
PROPERTY[CURRENCY][19] = NOK
PROPERTY[CURRENCY][20] = NZD
PROPERTY[CURRENCY][21] = PHP
PROPERTY[CURRENCY][22] = PLN
PROPERTY[CURRENCY][23] = RON
PROPERTY[CURRENCY][24] = RUB
PROPERTY[CURRENCY][25] = SEK
PROPERTY[CURRENCY][26] = SGD
PROPERTY[CURRENCY][27] = THB
PROPERTY[CURRENCY][28] = TRY
PROPERTY[CURRENCY][29] = USD
PROPERTY[CURRENCY][30] = ZAR
PROPERTY[CURRENCY][31] = EUR
EOF
```

----
