# QueryObjectList

## DESCRIPTION
Query a list of objects.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryObjectList` | COMMAND
WIDE | 1 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned | INT
ORDERBY | 0 | The parameter the output should be sorted by. <br> Must be one of the following: <br> `OBJECTCLASS`,`OBJECTCLASSDESC`,`OBJECTID`,`OBJECTIDDESC`,`EXPIRATIONDATE`,`EXPIRATIONDATEDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`
OBJECTCLASS | 0 | Filter query result by the object class stated here | PATTERN
OBJECTID | 0 | Filter the query result by the object ID stated here | PATTERN

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
OBJECTCLASS[0..N] | 0 | N | The object class | TEXT
OBJECTID[0..N] | 0 | N | The object ID | TEXT
CREATEDDATE[0..N] | 0 | N | The creation date of the object | DATETIME
UPDATEDDATE[0..N] | 0 | N | Last modification date of the object | DATETIME
EXPIRATIONDATE[0..N] | 0 | N | Expiration date of the domain name | DATETIME
PEERUSER[0..N] | 0 | N | Only displayed if wide is set to `1`: String with all users in the user chain | TEXT
PARENTUSER[0..N] | 0 | N | Only displayed if wide is set to `1`: The user ID of the parent user | TEXT
USER[0..N] | 0 | N | Only displayed if wide is set to `1`: The user ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryObjectList
FIRST = 2
LIMIT = 2
USERDEPTH = ALL
WIDE = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 2
PROPERTY[LAST][0] = 3
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 51143
PROPERTY[LIMIT][0] = 2
PROPERTY[OBJECTCLASS][0] = CONTACT
PROPERTY[OBJECTCLASS][1] = CONTACT
PROPERTY[OBJECTID][0] = P-SSV28511
PROPERTY[OBJECTID][1] = P-FCZ28558
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
## NOTES
* USERDEPTH defines the depth of the returned list. `SELF` returns a list with only objects of the user itself. `SUBUSER` returns a list with objects of all direct subusers. `ALL` returns a list with objects of all subusers and all subusers below them.
* FIRST and LIMIT should be used to implement paging.
