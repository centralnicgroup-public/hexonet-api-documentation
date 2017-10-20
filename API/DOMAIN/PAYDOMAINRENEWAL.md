# PayDomainRenewal

## DESCRIPTION
Pay renewal of a single domain. Set the PAIDUNTILDATE of a domain according to the given renewal
period. If domain is paid (as given by PAIDUNTILDATE) it will be renewed automatically when registry's
EXPIREDATE is reached.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `PayDomainRenewal` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
PERIOD | 0 | Renewal period in years, the default depends on the domain name to be renewed | PERIOD
EXPIRATION | 0 | Current expiration year, e.g. `2018` | INT
EXPIRATIONDATE | 0 | Current expiration date, e.g. `2018-09-26 14:53:20` | TEXT
CLASS | 0 | The class of the domain name in case it is a premium domain | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
549 | Command Failed
552	| Object status does not allow for operation
555	| Object already renewed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EXPIRATIONDATE | 1 | 1 | The date until the domain is paid | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = PayDomainRenewal
DOMAIN = hexonet-domain.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = OK
PROPERTY[EXPIRATIONDATE][0] = 2018-09-26 14:53:20
EOF
```

----
