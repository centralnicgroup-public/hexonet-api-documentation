# QueryUserList

## DESCRIPTION
Query a list of subusers.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryUserList` | COMMAND
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned | INT
USERDEPTH | 0 | Depth of the list, may be:`SELF`, `SUBUSER`, `ALL` | `ALL`, `SELF` or `SUBUSER`
USER[0..N] | 0 | Provide several dedicated users IDs for which the respective subusers will be queried | TEXT
USERDEPTH[0..N] | 0 | If several users are stated you can specify the userdepth (`SELF` or `SUBUSER`) for each user individually. If not stated the standard value `SELF` will be chosen | `SELF` or `SUBUSER`
ACTIVE | 0 | List shows only active/inactive users | `1`, `0` or NULL
SUBUSER | 0 | List shows only users of given subuser | TEXT
ORDERBY | 0 | Order of the list:<br>`CREATEDDATE`<br>`CREATEDDATEDESC` | TEXT or NULL
SCOPE | 0 | If `INVOICERECIPIENT` is stated only users that are recipients of invoices are returned | `INVOICERECIPIENT` or NULL
MINCREATEDDATE | 0 | Search for minimum created date of user | TEXT or NULL
MAXCREATEDDATE | 0 | Search for maximum created date of user | TEXT or NULL
MINUPDATEDDATE | 0 | Search for minimum updated date of user | TEXT or NULL
MAXUPDATEDDATE | 0 | Search for maximum updated date of user | TEXT or NULL
USERREGEX | 0 | Search for users for which the ID matches this regular expression | TEXT or NULL
USERCLASS | 0 | Search for certain user class | TEXT or NULL
ACCOUNTVAT | 0 | Search for certain account VAT, e.g. 19.00 | TEXT or NULL

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
531 | Authorization failed
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
USER[0..N] | 0 | N | The user ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryUserList
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
PROPERTY[TOTAL][0] = 63
PROPERTY[LIMIT][0] = 2
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = test.user
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = hexotestman.com
EOF
```

----
## NOTES
* This command only works for accounts, which have subusers.
* USERDEPTH defines the depth of the returned list. `SELF` returns a list with only one element, the user itself. `SUBUSER` returns a list with all direct subusers. `ALL` returns a list with all subusers and all subusers below them.
