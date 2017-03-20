# ResendDomainTransferConfirmationEmails

## DESCRIPTION
Resends the confirmation mail for a pending domain transfer/trade.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ResendDomainTransferConfirmationEmails` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531	| Authorization failed
540	| Attribute value is not unique
545	| Object not found
549 | Command Failed
552	| Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ResendDomainTransferConfirmationEmails
DOMAIN = hexonet-transfer.net
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
