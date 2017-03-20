# GetUserIndex

## DESCRIPTION
This command allows to get an index of a subuser account.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetUserIndex` | COMMAND
USER | 1 | Subuser account ID | TEXT

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
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
PARENTUSERINDEX | 1 | 1 | Account index of the user, which is the parent of the subuser | TEXT
USERINDEX | 1 | 1 | Account index of the subuser | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetUserIndex
USER = test.guest
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[PARENTUSERINDEX][0] = 659
PROPERTY[USERINDEX][0] = 977
EOF
```

----
