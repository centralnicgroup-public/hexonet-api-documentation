# FindUser

## DESCRIPTION
Finds a certain user by searching for a certain keyword through the user's environments "user-info/contact/company" and "user-info/contact/private". Additionally you may use FindUser to search for an exact username or a part of such one.

## AVAILABILITY
All users have access to this command. The command only works if you are searching for your own subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `FindUser` | COMMAND
ORDERBY | 0 | Parameter by which the output will be sorted, must be one of the following: `USERID`, `USERIDDESC`, `USERCREATEDDATE`, `USERCREATEDDATEDESC` | TEXT or NULL
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `ALL`, `SELF` or `SUBUSER`
MATCHMODE | 0 | `USER`: search for username<br>`ENVIRONMENT`: search through the enviroments mentioned above<br>Default value: `USER` | `USER`, `ENVIRONMENT` or NULL
EXACTMATCH | 0 | Flag to control if the search should match exactly or not; can be `0` or `1`, DEFAULT: `0` | `0` or `1`
PATTERN | 1 | Search pattern | TEXT
FIRST | 0 | The index of the first entry to be returned | INT or NULL
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT or NULL
INVERT | 0 | If INVERT = `1`, all users are found which DO NOT include the search pattern | `0`, `1` or NULL
WIDE | 0 | If set to `1`: verbose output (more parameters) | `0`, `1` or NULL
ACTIVE | 0 | Only search for active users if set to `1` | `1`, `0` or NULL

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
531 | Authorization failed
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned with the restrictions you gave. | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
TOTAL | 1 | 1 | The number of entries returned in total | INT
LIMIT | 1 | 1 | Max. number of entries returned | INT
ENVIRONMENTKEY[0..N] | 0 | N | The environment key where the search pattern has been found, only returned if MATCHMODE is set to `ENVIRONMENT` | TEXT
ENVIRONMENTNAME[0..N] | 0 | N | The environment name where the search pattern has been found, only returned if MATCHMODE is set to `ENVIRONMENT` | TEXT
ENVIRONMENTVALUE[0..N] | 0 | N | The environment value where the search pattern has been found, only returned if MATCHMODE is set to `ENVIRONMENT` | TEXT
PARENTUSER[0..N] | 0 | N | The user ID of the parent user | TEXT
USER[0..N] | 0 | N | The user ID | TEXT
USER< ENVIRONMENTNAME >[0..N] | 0 | N | Only returned if WIDE is set to `1`: Returns the user's contact environment values | TEXT
USERCREATEDDATE[0..N] | 0 | N | The user's created date | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = FindUser
LIMIT = 2
MATCHMODE = USER
PATTERN = .stone
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
PROPERTY[TOTAL][0] = 4
PROPERTY[LIMIT][0] = 2
PROPERTY[PARENTUSER][0] = test.user
PROPERTY[PARENTUSER][1] = test.user
PROPERTY[USER][0] = johanatton.living.stone
PROPERTY[USER][1] = john.bach.stone
PROPERTY[USERCOUNTRY3][0] =
PROPERTY[USERCOUNTRY3][1] =
PROPERTY[USERCREATEDDATE][0] = 2016-11-16 12:37:16
PROPERTY[USERCREATEDDATE][1] = 2016-11-16 12:38:00
EOF
```

----
