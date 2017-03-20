# RenewTMCHMark

## DESCRIPTION
Renew a trademark registration at TMCH.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RenewTMCHMark` | COMMAND
ORDER | 0 | Renew order action:<br>`CREATE` - create a renew order<br>`REPLACE` - replace a renew order<br>`UPDATE` - update a renew order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | Renew order ID | INT
ID | 0 | Trademark ID | TEXT or NULL
PERIOD | 0 | Renew period in years, default value: `1` | INT or NULL

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
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ORDERID | 0 | 1 | Renew order ID | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = RenewTMCHMark
ID = 0005581308200001-1
PERIOD = 1
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
