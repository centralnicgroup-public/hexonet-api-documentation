# ReleaseDomain

## DESCRIPTION
Deletes a Domain name from Hexonet's system without executing the deletion at the registry level. This command can be used by registrarOC customers e.g. after a domain was deleted at the registry level only.

## AVAILABILITY
The command can only be executed by the owner of the domain repository the respective domain is located in.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ReleaseDomain` | COMMAND
DOMAIN | 1 | The domain name to be released | TEXT
REPOSITORY | 0 | The repository the domain is located in | TEXT
REASON | 0 | The reason for the release can be stated here | TEXT

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
510 | Command not supported for this class
530 | Authentication failed
531	| Authorization failed
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
INREGISTRATIONGRACEPERIOD | 0 | 1 | Returns, if the domains was still in the registration grace period. This is only relevant to RegistrarOC customers, who might want to handle refunds in specific cases, or utilize this information to check registry invoices | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = ReleaseDomain
DOMAIN = exampledomain.no
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
