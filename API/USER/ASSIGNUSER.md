# AssignUser

## DESCRIPTION
Assign an existing subuser to another parent user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AssignUser` | COMMAND
SUBUSER | 1 | Subuser ID | TEXT
USER | 1 | New Parentuser ID | TEXT

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

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = AssignUser
SUBUSER = firstuser
USER = seconduser
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
* This command works only for accounts, which have subusers.
* Subusers can only be moved under your user account.
* All objects, environment entries, accounting records and invoices are assigned to the subuser and are moved with the subuser.
* To move objects see API function AssignObject.
