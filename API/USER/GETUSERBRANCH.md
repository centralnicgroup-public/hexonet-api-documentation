# GetUserBranch

## DESCRIPTION
Query the hierarchical list of of subusers between your user and the given subuser.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetUserBranch` | COMMAND
SUBUSER | 1 | User ID of the subuser to get the branch to | TEXT

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
531 | Authorization failed
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
TOTAL | 1 | 1 | The total number of entries found | INT
USER[0..N] | 1 | N | The user ID | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetUserBranch
SUBUSER = subusertesta16.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 2
PROPERTY[COUNT][0] = 3
PROPERTY[TOTAL][0] = 3
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = testsubuser16.com
PROPERTY[USER][2] = subusertesta16.com
EOF
```

----
