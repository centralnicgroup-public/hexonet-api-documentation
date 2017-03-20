# DeleteContact

## DESCRIPTION
Delete an existing contact handle.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteContact` | COMMAND
CONTACT | 1 | Contact Handle ID | CONTACT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
506 | Object is in use
530	| Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
545 | Object not found
549 | Command Failed

No properties are returned.
----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteContact
CONTACT = P-TCN1379052
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

## Notes

* You can only delete contact handles that are not assigned to any other object
