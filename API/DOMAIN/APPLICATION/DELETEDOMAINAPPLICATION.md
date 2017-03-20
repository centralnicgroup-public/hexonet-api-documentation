# DeleteDomainApplication

## DESCRIPTION
Delete a domain application.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteDomainApplication` | COMMAND
APPLICATION | 1 | Application ID | TEXT

----
## RESPONSE

Code | Description
---- | ----
200	| Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505	| Invalid attribute value syntax
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
545	| Object not found
549	| Command failed
552	| Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAIN | 1 | 1 | Domain name the application was made for | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = DeleteDomainApplication
APPLICATION = 10696
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[DOMAIN][0] = hexonet-backorder.com
EOF
```

----
