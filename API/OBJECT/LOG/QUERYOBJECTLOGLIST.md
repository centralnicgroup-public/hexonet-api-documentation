# QueryObjectLogList

## DESCRIPTION
Query a list of object logs. For the most objects related operations logging entries are created.<br> Example: If user `user.com` deletes his domain `reseller.com` the reseller can query the logging entry for the deletion via this command.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryObjectLogList` | COMMAND
OBJECTCLASS | 0 | Filter result by a specific class of objects, e. g. `DOMAIN` | TEXT or NULL
OBJECTID | 0 | Filter result by a specific object ID, e. g. `domainname.com` | TEXT or NULL
OPERATIONTYPE | 0 | Search for object log entries with a certain operation type, e.g.: <br>`CREATE`<br>`RENEW`<br>`DELETE` | TEXT or NULL
OPERATIONSTATUS | 0 | Search for object log entries with a certain operation status, e.g.:<br>`SUCCESSFUL`<br>`REQUEST`<br>`FAILED` | TEXT or NULL
FIRST | 0 | Index of the first entry to be returned | INT or NULL
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT or NULL
MINDATE | 0 | Minimum date of entries | TEXT or NULL
MAXDATE | 0 | Maximum date of entries | TEXT or NULL
ORDERBY | 0 | The parameter by which the output will be sorted. <br> Must be one of the following: <br> `OBJECTID`, `OBJECTIDDESC`, `OBJECTCLASS`, `OBJECTCLASSDESC`, `LOGDATE`, `LOGDATEDESC` | `OBJECTID`, `OBJECTIDDESC`, `OBJECTCLASS`, `OBJECTCLASSDESC`, `LOGDATE`, `LOGDATEDESC` or NULL
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
LOGDATE[0..N] | 0 | N | Date of the logging entry | DATETIME
LOGINDEX[0..N] | 0 | N | Index of the logging entry | INT
LOGROLEID[0..N] | 0 | N | Name of the role user who caused the log entry | TEXT
LOGUSER[0..N] | 0 | N | Name of user who caused the log entry | TEXT
OBJECTCLASS[0..N] | 0 | N | The class of object | TEXT
OBJECTID[0..N] | 0 | N | ID the object the log entry relates to | TEXT
OPERATIONSTATUS[0..N] | 0 | N | Status of the operation | TEXT
OPERATIONTYPE[0..N] | 0 | N | Type of the operation | TEXT
REFERENCE[0..N] | 0 | N | Log entry reference | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryObjectLogList
FIRST = 2
LIMIT = 2
OBJECTCLASS = DOMAIN
OBJECTID = testdomain-124.it
USERDEPTH = SELF
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully;
PROPERTY[FIRST][0] = 2
PROPERTY[LAST][0] = 3
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 12
PROPERTY[LIMIT][0] = 2
PROPERTY[LOGDATE][0] = 2016-11-18 22:15:25
PROPERTY[LOGDATE][1] = 2016-11-17 21:15:22
PROPERTY[LOGINDEX][0] = 31277401
PROPERTY[LOGINDEX][1] = 31264235
PROPERTY[LOGROLEID][0] =
PROPERTY[LOGROLEID][1] =
PROPERTY[LOGUSER][0] = test.user
PROPERTY[LOGUSER][1] = test.user
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTCLASS][1] = DOMAIN
PROPERTY[OBJECTID][0] = testdomain-124.it
PROPERTY[OBJECTID][1] = testdomain-124.it
PROPERTY[OPERATIONSTATUS][0] = PENDING
PROPERTY[OPERATIONSTATUS][1] = PENDING
PROPERTY[OPERATIONTYPE][0] = CREATE
PROPERTY[OPERATIONTYPE][1] = CREATE
PROPERTY[REFERENCE][0] = test.user
PROPERTY[REFERENCE][1] = test.user
EOF
```

----
