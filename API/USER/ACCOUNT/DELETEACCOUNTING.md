# DeleteAccounting

## DESCRIPTION
Delete an accounting entry of a subuser's account and update it's current account balance.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteAccounting` | COMMAND
SUBUSER | 1 | ID of the subuser account | TEXT
ACCOUNTINGID | 1 | ID of the accounting entry | INT

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

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteAccounting
ACCOUNTINGID = 800460
SUBUSER = test.customer
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
