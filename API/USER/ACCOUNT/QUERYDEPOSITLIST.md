# QueryDepositList

## DESCRIPTION
This command allows to see which deposits were created for the user, executing the command, or its subuser.<br>
Please note that a negative deposit amount relates to a credit while a positive amount relates to a deposit being substracted from the user's credit. 

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
PROPERTY[ACCOUNTINGTYPE][0]=BUILD_LANDRUSH
PROPERTY[ACCOUNTINGTYPE][1]=BUILD_LANDRUSH
PROPERTY[CREATEDDATE][0]=2016-09-09 18:43:04
PROPERTY[CREATEDDATE][1]=2016-09-09 18:43:04
PROPERTY[CURRENCY][0]=EUR
PROPERTY[CURRENCY][1]=EUR
PROPERTY[DEPOSIT][0]=100.06
PROPERTY[DEPOSIT][1]=100.06
PROPERTY[DEPOSITID][0]=490
PROPERTY[DEPOSITID][1]=488
PROPERTY[DESCRIPTION][0]=gegergegregr.build
PROPERTY[DESCRIPTION][1]=gergerg.build
PROPERTY[EXPIRATIONDATE][0]=2017-10-20 14:23:04
PROPERTY[EXPIRATIONDATE][1]=2017-10-20 14:23:03
PROPERTY[UPDATEDDATE][0]=2017-10-20 11:23:04
PROPERTY[UPDATEDDATE][1]=2017-10-20 11:23:03
PROPERTY[USER][0]=test.user
PROPERTY[USER][1]=test.user
EOF
```

----
