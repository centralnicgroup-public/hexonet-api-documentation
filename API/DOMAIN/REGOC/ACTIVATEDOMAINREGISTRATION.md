# ActivateDomainRegistration

## DESCRIPTION
This command is used to submit a domain registration request to the registry.

## AVAILABILITY
Only for registrars using our RegistrarOC system.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ActivateDomainRegistration` | COMMAND
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
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
545 | Object not found
546 | Credit limit exceeded
547 | Invalid command sequence
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
REGISTRATIONEXPIRATIONDATE | 1 | 1 | Expiration date of the domain name | DATETIME
STATUS | 1 | 1 | Status of the domain name,  e.g. `ACTIVE` | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = ActivateDomainRegistration
DOMAIN = exampledomain.no
EOF
```

### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-09-21 14:48:15
PROPERTY[STATUS][0] = ACTIVE
EOF
```

----
## Notes

* This command is only required, if a registrar needs to interact with the registry before the registration request is being submitted to the registry (e.g. for `.NO` domains a registration form is required upfront). If a customer requests a registration for such a domain using the `AddDomain` command the registration will not be submitted to the registry until the registrar activates it with the `ActivateDomainRegistration` command.
