# DeleteUser

## DESCRIPTION
Deletes a subuser.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteUser` | COMMAND
SUBUSER | 1 | User ID of the subuser | TEXT

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
541	| Invalid attribute value
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteUser
SUBUSER = customertodelete
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
## NOTES
* Only own subusers can be deleted
* The subuser must not have any objects in its account
* The subuser must not have any subusers itself
* The account of the subuser must have a balance of 0.00
