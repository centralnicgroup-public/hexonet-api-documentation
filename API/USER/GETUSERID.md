# GetUserId

## DESCRIPTION
This command allows to get a subuser account ID.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetUserId` | COMMAND
USERINDEX | 1 | Subuser index | TEXT

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
PARENTUSER | 1 | 1 | Account ID of the user, which is the parent of the subuser | TEXT
USER | 1 | 1 | Account ID of the subuser | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetUserId
USERINDEX = 977
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[PARENTUSER][0] = test.user
PROPERTY[USER][0] = test.guest
EOF
```

----
