# QueryAccountBalanceList

## DESCRIPTION
Lists the financial properties of one or several accounts.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryAccountBalanceList` | COMMAND
USERDEPTH | 1 | `SELF` lists the properties of the executing account, `SUBUSER` lists the properties for all subuser accounts | `SELF`, `SUBUSER` or NULL
WIDE | 0 | If set to `1`: verbose output (more parameters) | `0`, `1` or NULL
DATE | 0 | Addionally shows the financial properties at the date stated here | TEXT or NULL
FIRST | 0 | Index of the first entry to be returned | INT or NULL
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT or NULL
TASK | 0 | `ALL` - Consider all account balances. This is the default<br>`AR` - Only consider negative account balances<br>`AP` - Only consider positive account balances | `ALL`, `AR`, `AP` or NULL
ORDERBY | 0 | Only allowed parameter is `CURRENCYUSERID` which will sort the output by the account's currency fist and then by the user ID | TEXT or NULL
SKIPSUBUSER[0..N] | 0 | Do not show the properties of the subuser accounts listed here | TEXT

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
506 | Invalid option value
530 | Authentication failed
541 | Invalid attribute value

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
BILLINGTYPE[0..N] | 0 | N | The account's type of billing | TEXT
CREDIT[0..N] | 0 | N | The credit limit of the account | DECIMAL
CURRENCY[0..N] | 0 | N | The accounts default currency | TEXT
CURRENTBALANCE[0..N] | 0 | N | The current account balance | DECIMAL
CURRENTBALANCEALLOWANCE[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all current negative account balances of your subusers.<br>If USERDEPTH=SELF: Your account balance if it is negative. Otherwise 0 | DECIMAL
CURRENTBALANCECURRENCY[0..N] | 0 | N | The current account currencies of your subusers or yourself | TEXT
CURRENTBALANCEDEBTS[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all current positive account balances of your subusers.<br>If USERDEPTH=SELF: Your account balance if it is positive. Otherwise 0. | DECIMAL
CURRENTBALANCESUM[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all current account balances of your subusers.<br>If USERDEPTH=SELF: Your account balance | DECIMAL
DATE[0..N] | 0 | N | The date for which the account balance has been queried | DATETIME
DATEBALANCE[0..N] | 0 | N | The account balance at the date specified in the command | DECIMAL
DATEBALANCEALLOWANCE[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all negative account balances of your subusers at the given date.<br>If USERDEPTH=SELF: Your account balance at the given date if it was negative. Otherwise 0 | DECIMAL
DATEBALANCECURRENCY[0..N] | 0 | N | The account currencies of your subusers or yourself at the given date | TEXT
DATEBALANCEDEBTS[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all positive account balances of your subusers at the given date.<br>If USERDEPTH=SELF: Your account balance at the given date if it was positive. Otherwise 0 | DECIMAL
DATEBALANCESUM[0..N] | 0 | N | If USERDEPTH=SUBUSER: The sum of all account balances of your subusers at the given date.<br>If USERDEPTH=SELF: Your account balance at the given date | DECIMAL
USER[0..N] | 0 | N | The respective user ID | TEXT
----
## Example

### Command

```
[COMMAND]
COMMAND = QueryAccountBalanceList
DATE = 2016-01-10
USERDEPTH = SELF
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 0
PROPERTY[COUNT][0] = 1
PROPERTY[TOTAL][0] = 1
PROPERTY[LIMIT][0] = 999999
PROPERTY[CREDIT][0] = 1000000.0000
PROPERTY[CURRENCY][0] = EUR
PROPERTY[CURRENTBALANCE][0] = 217051.26
PROPERTY[CURRENTBALANCEALLOWANCE][0] = 0.00
PROPERTY[CURRENTBALANCECURRENCY][0] = EUR
PROPERTY[CURRENTBALANCEDEBTS][0] = 217051.26
PROPERTY[CURRENTBALANCESUM][0] = 217051.26
PROPERTY[DATE][0] = 2016-01-10 00:00:00
PROPERTY[DATEBALANCE][0] = 236814.34
PROPERTY[DATEBALANCEALLOWANCE][0] = 0.00
PROPERTY[DATEBALANCECURRENCY][0] = EUR
PROPERTY[DATEBALANCEDEBTS][0] = 236814.34
PROPERTY[DATEBALANCESUM][0] = 236814.34
PROPERTY[USER][0] = test.user
EOF
```

----
