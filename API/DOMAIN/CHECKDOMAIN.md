# CheckDomain

## DESCRIPTION
Check a domain name for availability.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckDomain` | COMMAND
DOMAIN | 1 | Name of the domain  | DOMAIN
X-IDN-LANGUAGE | 0 | If the domain is a IDN domain, you have to submit the IDN language tag with this parameter (e.g. DE for German IDN domains) | TEXT or NULL
PHASE | 0 | When stating `claims` in this parameter the command will return if there are claims for this domain. | `claims`, `sunrise` or NULL

----
## RESPONSE

Code | Description
---- | ----
200	| Command completed successfully
210	| Domain name available
211	| Domain name not available
420	| Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425	| Service temporarily locked; usage exceeded
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505	| Invalid attribute value syntax
507	| Invalid command format
520	| Server closing connection. Client should try opening new connection
521	| Too many sessions open. Server closing connection
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
547	| Invalid command sequence
549	| Command failed
552	| Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
REASON | 0 | 1 | The reason for the availability/unavailability of the domain name | REASON
CLAIMKEY | 0 | 1 | If there is a claim for the domain the claim key gets returned via this parameter | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckDomain
DOMAIN = hexonet.net
EOF

```
### Response

```
[RESPONSE]
CODE = 211
DESCRIPTION = Domain name not available
EOF
```

----
