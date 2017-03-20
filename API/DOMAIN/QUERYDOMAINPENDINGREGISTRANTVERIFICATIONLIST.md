# QueryDomainPendingRegistrantVerificationList

## DESCRIPTION
Query a list of domains with pending registrant verification

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainPendingRegistrantVerificationList` | COMMAND
FIRST | 0 | Index of the first entry. Default: `0` | INT
LIMIT | 0 | Query limit (max. number of entries returned) | INT
ORDERBY | 0 | Sort the list based on the specified parameter. Default order is ascending. Possible values: `DOMAIN`, `X-REGISTRANT-VERIFICATION-EMAIL`, `X-REGISTRANT-VERIFICATION-STATUS`, `X-REGISTRANT-VERIFICATION-NAME`, `X-REGISTRANT-VERIFICATION-REQUESTEDDATE`, `DOMAINDESC`, `X-REGISTRANT-VERIFICATION-EMAILDESC`, `X-REGISTRANT-VERIFICATION-STATUSDESC`, `X-REGISTRANT-VERIFICATION-NAMEDESC` or `X-REGISTRANT-VERIFICATION-REQUESTEDDATEDESC` | TEXT
USERDEPTH | 0 | Depth of the list. Default: `ALL` | `SELF`, `SUBUSER` or `ALL`
DOMAIN | 0 | Filter result by a specific domain name | PATTERN or TEXT

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
FIRST | 1 | 1 | Index of the first entry | INT
LAST | 1 | 1 | Index of the last entry | INT
COUNT | 1 | 1 | Number of entries returned | INT
TOTAL | 1 | 1 | Total number of entries found | INT
LIMIT | 1 | 1 | Query limit (max. number of entries returned) | INT
DOMAIN[0..N] | 0 | N | Domain name | TEXT
DOMAINREPOSITORY[0..N] | 0 | N | Domain repository name | TEXT
DOMAINUMLAUT[0..N] | 0 | N | Domain written in IDN | TEXT
X-REGISTRANT-VERIFICATION-DUEDATE[0..N] | 0 | N | The due date for registrant verification | DATETIME
X-REGISTRANT-VERIFICATION-EMAIL[0..N] | 0 | N | The registrant's email | TEXT
X-REGISTRANT-VERIFICATION-NAME[0..N] | 0 | N | The registrant's name | TEXT
X-REGISTRANT-VERIFICATION-REQUESTEDDATE[0..N] | 0 | N | The requested date for registrant verification | DATETIME
X-REGISTRANT-VERIFICATION-STATUS[0..N] | 0 | N | The current registrant verification status | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainPendingRegistrantVerificationList
DOMAIN = test123456abcdef.net
LIMIT = 2
ORDERBY = X-REGISTRANT-VERIFICATION-REQUESTEDDATE
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
PROPERTY[LIMIT][0] = 2
PROPERTY[DOMAIN][0] = test123456abcdef.net
PROPERTY[DOMAINREPOSITORY][0] = COM-OTE-1API1
PROPERTY[DOMAINUMLAUT][0] = test123456abcdef.net
PROPERTY[X-REGISTRANT-VERIFICATION-DUEDATE][0] = 2015-12-12 09:11:54
PROPERTY[X-REGISTRANT-VERIFICATION-EMAIL][0] = jdoe@example.com
PROPERTY[X-REGISTRANT-VERIFICATION-NAME][0] = John Doe
PROPERTY[X-REGISTRANT-VERIFICATION-REQUESTEDDATE][0] = 2015-11-27 09:11:54
PROPERTY[X-REGISTRANT-VERIFICATION-STATUS][0] = OVERDUE
EOF
```

----
