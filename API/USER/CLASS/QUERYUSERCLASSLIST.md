# QueryUserClassList

## DESCRIPTION
Query a list of user classes for the executing user.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryUserClassList` | COMMAND

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
USERCLASS[0..N] | 0 | N | The user class name | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryUserClassList
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[USERCLASS][0] = MYNEWPRICECLASS1
PROPERTY[USERCLASS][1] = TEST123
EOF
```

----
