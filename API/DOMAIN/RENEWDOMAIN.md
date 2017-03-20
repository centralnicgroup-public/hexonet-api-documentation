# RenewDomain

## DESCRIPTION
RenewDomain explicitly renews a domain at the registry, if the registry supports this function.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RenewDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
ORDER | 0 | Order action:<br>`CREATE` - create a renew order<br>`REPLACE` - replace a renew order<br>`UPDATE` - update a renew order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | Renew order ID. Will only be considered if the parameter ORDER is set to `REPLACE` or `UPDATE`. If the parameter is not stated and the parameter ORDER is set to `REPLACE` or `UPDATE` then an auto detection of the order ID will be done. | INT
PERIOD | 0 | Renewal period in years, default = 1 | PERIOD
EXPIRATION | 0 | Year of expiration of the domain | INT
EXPIRATIONDATE | 0 | The current expiration date | TEXT
CLASS | 0 | The class of the domain name in case it is a premium domain | TEXT
X-TRAVEL-UIN | 0 | Only necessary for .TRAVEL domains | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500 | Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505	| Invalid attribute value syntax
510	| Command not supported for this class
530	| Authentication failed
531	| Authorization failed
536	| Object already flagged for transfer
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
547	| Invalid command sequence
548	| Object is not up for renewal
549 | Command Failed
552	| Object status does not allow for operation
555	| Object already renewed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAIN | 1 | 1 | The domain name | DOMAIN
EXPIRATIONDATE | 1 | 1 | New expiration date of the domain | DATETIME
REGISTRATIONEXPIRATIONDATE | 0 | 1 | Deprecated: New expiration date of the domain | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = RenewDomain
DOMAIN = hexonet-domain.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[DOMAIN][0] = hexonet-domain.com
PROPERTY[EXPIRATIONDATE][0] = 2018-09-26 14:53:20
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2018-09-26 14:53:20
EOF
```

----
