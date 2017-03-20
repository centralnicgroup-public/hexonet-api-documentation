# ActivateDomainTrade

## DESCRIPTION
The ActivateDomainTrade command is used to approve a domain trade, which requires the active participation of the registrar or repository owner (e.g. for .SE domains).

If a customer initiates a Trade for such a domain, the Trade will not be submitted to the registry until the registrar or repository owner activates it using this command.

## AVAILABILITY
The command can only be executed by registrars or owners of domain repositories.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ActivateDomainTrade` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
TRIGGER | 0 | Repository trigger code | TEXT

----
## RESPONSE

Code | Description
---- | ----
200	| Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
506 | Invalid option value
507 | Invalid command format
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
545 | Object not found
549 | Command failed

No properties are returned


----
## Example

### Command

```
[COMMAND]
COMMAND = ActivateDomainTrade
DOMAIN = hexonet.se
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
