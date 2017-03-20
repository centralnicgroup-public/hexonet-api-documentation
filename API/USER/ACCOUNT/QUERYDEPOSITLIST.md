# QueryDepositList

## DESCRIPTION
This command allows to see which deposits were created for the user, executing the command, or its subuser.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDepositList` | COMMAND
SUBUSER | 0 | Subuser account ID; if omitted, then the deposits, assigned to the user, executing the command, are being returned | TEXT
FIRST | 0 | Response list offset | INT
LIMIT | 0 | Response list length limit | INT
USERDEPTH | 0 | Depth of the response list, may be only `SELF` here; it is also the default value | `SELF` or NULL
ACCOUNTINGTYPE | 0 | The type of deposit, for example `PAYMENT` or `COM_BACKORDER` | TEXT or NULL

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
531 | Authorization failed
541 | Invalid attribute value

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | Index of the first item in the response list | INT
LAST | 1 | 1 | Index of the last item in the response list | INT
COUNT | 1 | 1 | Response list length | INT
TOTAL | 1 | 1 | Total number of records, returned by the query | INT
LIMIT | 1 | 1 | Response list length limit | INT
ACCOUNTINGTYPE[0..N] | 0 | N | Deposit type | TEXT
CREATEDDATE[0..N] | 0 | N | Deposit created date | DATETIME
CURRENCY[0..N] | 0 | N | Deposit currency code | TEXT
DEPOSIT[0..N] | 0 | N | Deposit amount | DECIMAL
DEPOSITID[0..N] | 0 | N | Deposit ID | INT
DESCRIPTION[0..N] | 0 | N | Deposit description | TEXT
EXPIRATIONDATE[0..N] | 0 | N | Deposit expiration date | DATETIME
UPDATEDDATE[0..N] | 0 | N | Deposit last update date | DATETIME
USER[0..N] | 0 | N | Account ID of the user, to whom the respective deposit was assigned | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDepositList
LIMIT = 2
SUBUSER = test.guest
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
PROPERTY[ACCOUNTINGTYPE][0] = PAYMENT
PROPERTY[ACCOUNTINGTYPE][1] = PAYMENT
PROPERTY[CREATEDDATE][0] = 2016-11-11 12:47:22
PROPERTY[CREATEDDATE][1] = 2016-11-11 14:12:52
PROPERTY[CURRENCY][0] = LVL
PROPERTY[CURRENCY][1] = LVL
PROPERTY[DEPOSIT][0] = -100.00
PROPERTY[DEPOSIT][1] = -100.00
PROPERTY[DEPOSITID][0] = 578
PROPERTY[DEPOSITID][1] = 584
PROPERTY[DESCRIPTION][0] = test deposit
PROPERTY[DESCRIPTION][1] = Test deposit 003
PROPERTY[EXPIRATIONDATE][0] = 2016-12-01 10:00:00
PROPERTY[EXPIRATIONDATE][1] = 2016-12-01 10:00:00
PROPERTY[UPDATEDDATE][0] = 0000-00-00 00:00:00
PROPERTY[UPDATEDDATE][1] = 0000-00-00 00:00:00
PROPERTY[USER][0] = test.guest
PROPERTY[USER][1] = test.guest
EOF
```

----
