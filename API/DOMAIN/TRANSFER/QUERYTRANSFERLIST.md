# QueryTransferList

## DESCRIPTION
Query a list of incoming domain transfers.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryTransferList` | COMMAND
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned | INT
DOMAIN | 0 | Domain pattern, e. g. `*.com`, `a*.de` | PATTERN
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL`. Default: `ALL` | `SELF`, `SUBUSER` or `ALL`
MINCREATEDDATE | 0 | Filter for transfers that haven been initiated after the date specified there | TEXT
MAXCREATEDDATE | 0 | Filter for transfers that haven been initiated before the date specified there | TEXT
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`DOMAIN`, `DOMAINDESC`, `USER`, `USERDESC`, `CREATEDDATE`, `CREATEDDATEDESC` | TEXT

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
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
CREATEDDATE[0..N] | 0 | N | Date when the transfer was initiated | DATETIME
DOMAIN[0..N] | 0 | N | The domain name | TEXT
DOMAINUMLAUT[0..N] | 0 | N | The domain name displayed as an IDN | TEXT
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PEERUSER[0..N] | 0 | N |  String with all users in the user chain | TEXT
USER[0..N] | 0 | N | The user ID | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = QueryTransferList
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
PROPERTY[TOTAL][0] = 27
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2016-11-21 21:26:38
PROPERTY[CREATEDDATE][1] = 2016-11-11 16:44:27
PROPERTY[DOMAIN][0] = bahrainbox.com
PROPERTY[DOMAIN][1] = btc.info
PROPERTY[DOMAINUMLAUT][0] = bahrainbox.com
PROPERTY[DOMAINUMLAUT][1] = btc.info
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

* USERDEPTH defines the depth of the returned list. `SELF` returns a list with only domain transfers of the user itself. `SUBUSER` returns a list with domain transfers of all direct subusers. `ALL` returns a list with domain transfers of all subusers and all subusers below them.
* FIRST and LIMIT should be used to implement paging

----
