# QueryTMCHMarkList

## DESCRIPTION
The command lists trademarks, regsitered at TMCH for a given user and/or its subusers.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryTMCHMarkList` | COMMAND
MARKNAME | 0 | Filter results by the trademark name | TEXT or NULL
MARKTYPE | 0 | Filter results by the trademark type | TEXT or NULL
STATUS | 0 | Filter results by the trademark verification status | TEXT or NULL
FIRST | 0 | Index of the first item in the response list | INT
LIMIT | 0 | Response list length limit | INT
ORDERBY | 0 | Sort the response list by the following response parameters in ascending or descending order:<br><br>`CREATEDDATE`<br>`CREATEDDATEDESC`<br>`EXPIRATIONDATE`<br>`EXPIRATIONDATEDESC`<br>`ID`<br>`IDDESC`<br>`MARKNAME`<br>`MARKNAMEDESC`<br>`MARKTYPE`<br>`MARKTYPEDESC`<br>`POUSTATUS`<br>`POUSTATUSDESC`<br>`STATUS`<br>`STATUSDESC`<br>`UPDATEDDATE`<br>`UPDATEDDATEDESC`<br>`USER`<br>`USERDESC` | TEXT
WIDE | 0 | `0` (default): concise response<br>`1`: verbose response | `0`, `1` or NULL
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
MINCREATEDDATE | 0 | Limit the search with an earliest trademark registration date | NULL or TEXT
MAXCREATEDDATE | 0 | Limit the search with a latest trademark registration date | NULL or TEXT
MINUPDATEDDATE | 0 | Limit the search with an earliest trademark update date  | NULL or TEXT
MAXUPDATEDDATE | 0 | Limit the search with a latest trademark update date | NULL or TEXT
MINEXPIRATIONDATE | 0 | Limit the search with an earliest trademark expiration date | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Limit the search with a latest trademark expiration date | NULL or TEXT

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
FIRST | 1 | 1 | Index of the first item in the response list | INT
LAST | 1 | 1 | Index of the last item in the response list | INT
COUNT | 1 | 1 | Response list length | INT
TOTAL | 1 | 1 | Total number of records, returned by the query | INT
LIMIT | 1 | 1 | Response list length limit | INT
CREATEDDATE[0..N] | 0 | N | Date of the trademark registration at TMCH | DATETIME
EXPIRATIONDATE[0..N] | 0 | N | Date of the trademark expiration at TMCH | DATETIME
ID[0..N] | 0 | N | Trademark ID | TEXT
MARKNAME[0..N] | 0 | N | Trademark name | TEXT
MARKTYPE[0..N] | 0 | N | Trademark type | TEXT
PARENTUSER[0..N] | 0 | N | Parent user name | TEXT
PEERUSER[0..N] | 0 | N | List of subusers, which have a control over the given trademark object | TEXT
POUSTATUS[0..N] | 0 | N | Proof of use status | TEXT
STATUS[0..N] | 0 | N | Verification status | TEXT
UPDATEDDATE[0..N] | 0 | N | Last update date | DATETIME
USER[0..N] | 0 | N | User name | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = QueryTMCHMarkList
LIMIT = 2
USERDEPTH = SELF
WIDE = 1
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
PROPERTY[TOTAL][0] = 16
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2013-08-20 16:22:40
PROPERTY[CREATEDDATE][1] = 2013-08-20 16:22:51
PROPERTY[EXPIRATIONDATE][0] = 2014-08-20 00:00:00
PROPERTY[EXPIRATIONDATE][1] = 2014-08-20 00:00:00
PROPERTY[ID][0] = 0005581308200001-1
PROPERTY[ID][1] = 0005581308200002-1
PROPERTY[MARKNAME][0] = HEXONET
PROPERTY[MARKNAME][1] = HEXONET
PROPERTY[MARKTYPE][0] = TRADEMARK
PROPERTY[MARKTYPE][1] = TRADEMARK
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[POUSTATUS][0] = verified
PROPERTY[POUSTATUS][1] = verified
PROPERTY[STATUS][0] = verified
PROPERTY[STATUS][1] = verified
PROPERTY[UPDATEDDATE][0] = 2016-10-03 22:19:18
PROPERTY[UPDATEDDATE][1] = 2013-08-20 16:30:01
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
