# QueryRoleUserList

## DESCRIPTION
Shows a list of all role users within the current user account.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryRoleUserList` | COMMAND
ROLEID | 0 | Filter result by a specific role user ID | TEXT or NULL
SUBUSER | 0 | Only show role users of a specific subuser | TEXT
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | Parameter by which the output will be sorted. Can be either `ROLEID` to sort by the role user ID in ascending order or `ROLEIDDESC` to sort by the role user ID in descending order. Default is `ROLEID` | TEXT
USERDEPTH | 0 | Depth of subuser accounts to check; can be `SELF`, `ALL` or `SUBUSER` | `SELF`, `SUBUSER` or `ALL`

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | Index of the first item in the response list | INT
LAST | 1 | 1 | Index of the last item in the response list | INT
COUNT | 1 | 1 | Response list length | INT
TOTAL | 1 | 1 | Total number of records, returned by the query | INT
LIMIT | 1 | 1 | Response list length limit | INT
CREATEDDATE[0..N] | 0 | N | Date of creation of the role user | DATETIME
DEFAULTPOLICY[0..N] | 0 | N | Default access policy of the role user | TEXT
DESCRIPTION[0..N] | 0 | N | Description entered at the creation of the role user | TEXT
ROLEID[0..N] | 0 | N | The role user ID | TEXT
STATUS[0..N] | 0 | N | Current status of the role user | TEXT
UPDATEDDATE[0..N] | 0 | N | Date of last modification of the role user | DATETIME
USER[0..N] | 0 | N | The user to which the role user belongs | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryRoleUserList
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
PROPERTY[TOTAL][0] = 7
PROPERTY[LIMIT][0] = 2
PROPERTY[CREATEDDATE][0] = 2014-06-18 09:06:50
PROPERTY[CREATEDDATE][1] = 2014-04-23 09:04:35
PROPERTY[DEFAULTPOLICY][0] = ALLOW
PROPERTY[DEFAULTPOLICY][1] = ALLOW
PROPERTY[DESCRIPTION][0] = test
PROPERTY[DESCRIPTION][1] =
PROPERTY[ROLEID][0] = anton
PROPERTY[ROLEID][1] = dg
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS][1] = ACTIVE
PROPERTY[UPDATEDDATE][0] = 2016-04-21 12:29:41
PROPERTY[UPDATEDDATE][1] = 2016-07-30 13:25:43
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
EOF
```

----
