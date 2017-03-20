# CheckUsername

## DESCRIPTION
Checks if a user ID is valid and available.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckUsername` | COMMAND
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
540 | Attribute value is not unique
541 | Invalid attribute value

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckUsername
SUBUSER = subreseller.com
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
* If a user ID already exists the error code 540 is being returned
* If a user ID contains invalid characters the error code 505 is being returned
