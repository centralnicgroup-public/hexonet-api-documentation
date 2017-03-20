# QueryForeignTransferList

## DESCRIPTION
Query a list of outgoing domain transfers

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryForeignTransferList` | COMMAND
USERDEPTH | 0 | Depth of the list, may be SELF, SUBUSER or ALL | `ALL`, `SELF` or `SUBUSER`
WIDE | 0 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
DOMAIN | 0 | Only lists transfer for domains which match the pattern specified here, e.g. `*.com` | PATTERN
TARGET | 0 | Controls if the list shows all transfers and trades, only trades, or only user transfers and trades | `ALL`, `SELF`, `TRADE` or `SUBUSER`
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`DOMAIN`, `DOMAINDESC`, `CREATEDDATE`, `CREATEDDATEDESC` | `DOMAIN`, `DOMAINDESC`, `CREATEDDATE` or `CREATEDDATEDESC`
MINCREATEDDATE | 0 | Only search for transfer which have been initiated after the date specified here | TEXT
MAXCREATEDDATE | 0 | Only search for transfer which have been initiated before the date specified here | TEXT

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
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
COUNT | 1 | 1 | The number of entries returned | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
CREATEDDATE[0..N] | 0 | N | Date when the respective transfer has been initiated | DATETIME
DOMAIN[0..N] | 0 | N | The domain name | TEXT
DOMAINUMLAUT[0..N] | 0 | N | The domain name dispayed as  an IDN | TEXT
NEWREGISTRAR[0..N] | 0 | N | Name of the new registrar - value gets submitted by the registry and may be empty for some TLDs | TEXT
OLDREGISTRAR[0..N] | 0 | N | Name of the old registrar - value gets submitted by the registry and may be empty for some TLDs | TEXT
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain | TEXT
STATUS[0..N] | 0 | N | The current transfer status | TEXT
USER[0..N] | 0 | N | The user ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryForeignTransferList
LIMIT = 2
ORDERBY = CREATEDDATE
USERDEPTH = ALL
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
PROPERTY[TOTAL][0] = 2
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2016-05-10 13:47:55
PROPERTY[CREATEDDATE][1] = 2016-05-25 12:46:01
PROPERTY[DOMAIN][0] = sexy.asia
PROPERTY[DOMAIN][1] = btc.asia
PROPERTY[DOMAINUMLAUT][0] = sexy.asia
PROPERTY[DOMAINUMLAUT][1] = btc.asia
PROPERTY[NEWREGISTRAR][0] = 1apiGmbh2
PROPERTY[NEWREGISTRAR][1] = 1apiGmbh2
PROPERTY[OLDREGISTRAR][0] = 1apiGmbh1
PROPERTY[OLDREGISTRAR][1] = 1apiGmbh1
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[STATUS][0] = PENDING
PROPERTY[STATUS][1] = PENDING
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----

## NOTES

* USERDEPTH defines the depth of the returned list. `SELF` returns a list with only domain transfers of the user itself. `SUBUSER` returns a list with domain foreign transfers of all direct subusers. `ALL` returns a list with domain foreign transfers of all subusers and all subusers below them.
* FIRST and LIMIT should be used to implement paging

----
