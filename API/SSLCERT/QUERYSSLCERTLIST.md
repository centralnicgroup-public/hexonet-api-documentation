# QuerySSLCertList

## DESCRIPTION
Query a list of all certificate orders.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QuerySSLCertList` | COMMAND
WIDE | 0 | If set to `1` additional information is returned | `0` or `1`
ORDERBY | 0 | Property by which the list should be ordered; possible values:<br>`CREATEDDATE`<br>`CREATEDDATEDESC`<br>`EXPIRATIONDATE`<br>`EXPIRATIONDATEDESC`<br>`SSLCERTCLASS`<br>`SSLCERTCLASSDESC`<br>`SSLCERTID`<br>`SSLCERTIDDESC`<br>`SSLCERTCN`<br>`SSLCERTCNDESC`<br>`STATUS`<br>`STATUSDESC`<br>`UPDATEDDATE`<br>`UPDATEDDATEDESC` | TEXT
FIRST | 0 | Position from which on entries of the entire list should be returned; default: FIRST = `0` | INT
LIMIT | 0 | Maximum number of entries that should be returned from the entire list; default: LIMIT = `10000` | INT
USERDEPTH | 0 | Depth of subuser accounts to consider | `SELF`, `SUBUSER` or `ALL`
SSLCERTCLASS | 0 | Limit the search to certificate orders of certain product types | PATTERN
SSLCERTID | 0 | Limit the search to certificate orders with certain certificate IDs | PATTERN
STATUS | 0 | Limit the search to certificate orders having a certain status | PATTERN
SSLCERTCN | 0 | Limit the search to certificate orders with certain Common Names | TEXT or NULL
MINCREATEDDATE | 0 | Limit the search to certificate orders that have been created after MINCREATEDDATE | NULL or TEXT
MAXCREATEDDATE | 0 | Limit the search to certificate orders that have been created before MAXCREATEDDATE | NULL or TEXT
MINUPDATEDDATE | 0 | Limit the search to certificate orders that have been last modified after MINUPDATEDDATE | NULL or TEXT
MAXUPDATEDDATE | 0 | Limit the search to certificate orders that have been last modified before MAXUPDATEDDATE | NULL or TEXT
MINEXPIRATIONDATE | 0 | Limit the search to certificate orders that will expire after MINEXPIRATIONDATE | NULL or TEXT
MAXEXPIRATIONDATE | 0 | Limit the search to certificate orders that will expire before MAXEXPIRATIONDATE | NULL or TEXT


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
FIRST | 1 | 1 | Index of the first element in the response | INT
LAST | 1 | 1 | Index of the last element in the response | INT
COUNT | 1 | 1 | Number of entries returned | INT
TOTAL | 1 | 1 | Total count of records | INT
LIMIT | 1 | 1 | Maximum number of entries returned | INT
PARENTUSER[0..N] | 0 | N | User ID of the parent user; only available with parameter WIDE set to `1` | TEXT
PEERUSER[0..N] | 0 | N | String with all users in the user chain; only available with parameter WIDE set to `1` | TEXT
SSLCERTCLASS[0..N] | 0 | N | Product type; only available with parameter WIDE set to `1` | TEXT
SSLCERTCN[0..N] | 0 | N | Common Name; only available with parameter WIDE set to `1` | TEXT
SSLCERTCREATEDDATE[0..N] | 0 | N | SSL certificate order date; only available with parameter WIDE set to `1` | DATETIME
SSLCERTEXPIRATIONDATE[0..N] | 0 | N | SSL certificate expiration date; only available with parameter WIDE set to `1` | DATETIME
SSLCERTID[0..N] | 0 | N | SSL certificate ID | TEXT
SSLCERTSTATUS[0..N] | 0 | N | SSL certificate status; only available with parameter WIDE set to `1` | TEXT
SSLCERTUPDATEDDATE[0..N] | 0 | N | SSL certificate updated date; only available with parameter WIDE set to `1` | DATETIME
USER[0..N] | 0 | N | User managing the SSL certificate; only available with parameter WIDE set to `1` | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = QuerySSLCertList
MAXCREATEDDATE = 2016-02-18 23:59:59
MINCREATEDDATE = 2016-02-11 00:00:00
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
PROPERTY[LIMIT][0] = 10000
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[SSLCERTCLASS][0] = COMODO_ESSENTIALSSL
PROPERTY[SSLCERTCLASS][1] = COMODO_ESSENTIALSSL
PROPERTY[SSLCERTCN][0] = hexonet.net
PROPERTY[SSLCERTCN][1] = 1api.net
PROPERTY[SSLCERTCREATEDDATE][0] = 2016-02-11 13:10:05
PROPERTY[SSLCERTCREATEDDATE][1] = 2016-02-18 09:58:51
PROPERTY[SSLCERTEXPIRATIONDATE][0] = 2017-02-10 23:59:59
PROPERTY[SSLCERTEXPIRATIONDATE][1] = 2017-02-17 09:58:51
PROPERTY[SSLCERTID][0] = 2251338301
PROPERTY[SSLCERTID][1] = 2261231414
PROPERTY[SSLCERTSTATUS][0] = ACTIVE
PROPERTY[SSLCERTSTATUS][1] = FAILED
PROPERTY[SSLCERTUPDATEDDATE][0] = 2016-02-11 13:10:05
PROPERTY[SSLCERTUPDATEDDATE][1] = 2016-02-18 09:58:51
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----

