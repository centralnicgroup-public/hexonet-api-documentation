# DeleteRoleUser

## DESCRIPTION
With this command you can delete a certain role user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteRoleUser` | COMMAND
ROLEID | 1 | The role ID of the role user | TEXT
SUBUSER | 0 | By providing this parameter you can delete the role user of a certain subuser | TEXT

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
531 | Authorization failed
545 | Object not found
549 | Command failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteRoleUser
ROLEID = myroleuser
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
EOF
```

----
