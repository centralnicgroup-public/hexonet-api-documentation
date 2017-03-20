# QueryObjectDeletionLogList

## DESCRIPTION
Query a list of log entries for deleted objects.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryObjectDeletionLogList` | COMMAND
OBJECTCLASS | 0 | CLASS of the object, e. g. `DOMAIN` | TEXT or NULL
OBJECTID | 0 | ID of a object, e. g. `domainname.com` | TEXT or NULL
FIRST | 0 | Index of the first entry to be returned | INT or NULL
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT or NULL
MINDATE | 0 | Min date of the log entry | TEXT or NULL
MAXDATE | 0 | Max date of the log entry | TEXT or NULL
ORDERBY | 0 | Parameter by which the output will be ordered.<br>Must be one of the following:<br>`OBJECTID`, `OBJECTIDDESC`, `OBJECTCLASS`, `OBJECTCLASSDESC`, `LOGDATE`, `LOGDATEDESC` | `OBJECTID`, `OBJECTIDDESC`, `OBJECTCLASS`, `OBJECTCLASSDESC`, `LOGDATE`, `LOGDATEDESC` or NULL

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
506 | Invalid option value
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
LOGINDEX[0..N] | 0 | N | ID of the logging entry  | INT
LOGROLEID[0..N] | 0 | N | Name of the role user who caused the log entry  | TEXT
LOGUSER[0..N] | 0 | N | Name of user who caused the log entry  | TEXT
OBJECTCLASS[0..N] | 0 | N | Class of the object | TEXT
OBJECTID[0..N] | 0 | N | ID of the object  | TEXT
REFERENCE[0..N] | 0 | N | Name of the referring object | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryObjectDeletionLogList
LIMIT = 2
MAXDATE = 2016-11-17
MINDATE = 2016-11-01
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully;
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 14
PROPERTY[LIMIT][0] = 2
PROPERTY[LOGDATE][0] = 2016-11-17 11:00:44
PROPERTY[LOGDATE][1] = 2016-11-17 10:12:51
PROPERTY[LOGINDEX][0] = 174586
PROPERTY[LOGINDEX][1] = 174578
PROPERTY[LOGROLEID][0] =
PROPERTY[LOGROLEID][1] =
PROPERTY[LOGUSER][0] = test.user
PROPERTY[LOGUSER][1] = test.user
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTCLASS][1] = DOMAIN
PROPERTY[OBJECTID][0] = topdata5.io
PROPERTY[OBJECTID][1] = topdata4.io
PROPERTY[REFERENCE][0] = test.user
PROPERTY[REFERENCE][1] = test.user
EOF
```

----
