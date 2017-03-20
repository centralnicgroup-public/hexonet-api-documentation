# QueryExchangeRates

## DESCRIPTION
Query list of all current exchange rates. The list represents the daily exchange rates of the ECB (European Central Bank). The rates are used if the object class currency and user account currency are different.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryExchangeRates` | COMMAND
MINDATE | 0 | The minimal date when the exchange rate was determined | TEXT or NULL
MAXDATE | 0 | The maximal date when the exchange rate was determined | TEXT or NULL
FIRST | 0 | Index of the first entry to be returned | INT or NULL
LIMIT | 0 | Max. number of entries to be returned (default = `100`) | INT or NULL
CURRENCYTO | 0 | Returns the last exchange rate for the target currency | TEXT or NULL

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
CURRENCYFROM[0..N] | 0 | N | The source currency | TEXT
CURRENCYTO[0..N] | 0 | N | The target currency | TEXT
DATE[0..N] | 0 | N | The date when the exchange rate was determined | DATETIME
RATE[0..N] | 0 | N | The respective exchange rate | DECIMAL

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryExchangeRates
CURRENCYTO = USD
FIRST = 0
LIMIT = 2
MAXDATE = 2016-11-15 00:00:00
MINDATE = 2016-11-12 00:00:00
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 2
PROPERTY[LIMIT][0] = 2
PROPERTY[CURRENCYFROM][0] = EUR
PROPERTY[CURRENCYFROM][1] = EUR
PROPERTY[CURRENCYTO][0] = USD
PROPERTY[CURRENCYTO][1] = USD
PROPERTY[DATE][0] = 2016-11-14
PROPERTY[DATE][1] = 2016-11-15
PROPERTY[RATE][0] = 1.0777
PROPERTY[RATE][1] = 1.0765
EOF
```

----
