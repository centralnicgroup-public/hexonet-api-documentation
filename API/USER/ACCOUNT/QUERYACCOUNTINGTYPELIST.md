# QueryAccountingTypeList

## DESCRIPTION
Queries a list of distinct accounting types.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryAccountingTypeList` | COMMAND
SUBUSER | 0 | Get the accounting type for the subuser specified here | TEXT
MINDATE | 0 | The minimal creation date of accountings which will be taken into consideration | TEXT
MAXDATE | 0 | The maximal creation date of accountings which will be taken into consideration | TEXT
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
USERDEPTH | 0 | Depth of the list, may be `SELF` or `SUBUSER`| `SELF` or `SUBUSER`
INVOICEID | 0 | Get all accounting types of a certain invoice | TEXT
DESCRIPTION | 0 | Only takes accountings with a description stated here into consideration | TEXT
REFERENCE | 0 | Only takes accountings with a reference stated here into consideration | TEXT or NULL

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
541 | Invalid attribute value

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
ACCOUNTINGTYPE[0..N] | 0 | N | The respective accounting type | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryAccountingTypeList
LIMIT = 2
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 1
PROPERTY[LAST][0] = 2
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 3
PROPERTY[LIMIT][0] = 2
PROPERTY[ACCOUNTINGTYPE][0] = PAYMENT
PROPERTY[ACCOUNTINGTYPE][1] = TESTTYPE000_//A
EOF
```

----
