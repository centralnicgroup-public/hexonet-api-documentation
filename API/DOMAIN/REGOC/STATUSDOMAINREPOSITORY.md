# StatusDomainRepository

## DESCRIPTION
Returns properties and statistics for a dedicated repository.

## AVAILABILITY
Only for registrars using our RegistrarOC system.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainRepository` | COMMAND
REPOSITORY | 1 | The domain repository | TEXT
WIDE | 0 | If set to `1`: verbose output (more parameters) | `0`, `1` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
506	| Invalid option value
530 | Authentication failed
541	| Invalid attribute value
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAINCLASS[0..N] | 0 | N | The domain classes of the repository | TEXT
RDE_LAST_TRANSMISSION_DATE | 0 | 1 | Only stated if wide is set to `1`: Last transmission date of the ICANN Registrar Data Escrow Agreement  | DATETIME
STATUS | 1 | 1 | The status of the repository | TEXT
STATUS\_ACCOUNT\_AVAILABLE | 1 | 1 | Indicates if a StatusAccount command is possible for the repository | INT
SUM\_ACTIVE\_DOMAINS | 1 | 1 | Total number of domains with status "ACTIVE" | INT
SUM\_CONTACTS | 1 | 1 | Total number of the repository's contact handles | INT
SUM\_DOMAINS | 1 | 1 | Total number of domains on this repository | INT
SUM\_DOMAINS\_&lt;ZONE&gt; | 0 | N | Only stated if wide is set to `1`: Total number of domains listed for each zone of the repository | INT
SUM\_INCOMING\_TRANSFERS | 1 | 1 | Total number of pending incoming transfers for this repository | INT
SUM\_INCOMING\_TRANSFERS\_&lt;ZONE&gt; | 0 | N | Only stated if wide is set to `1`: Total number of pending incoming transfers listed for each zone of the repository | INT
SUM\_NAMESERVERS | 1 | 1 | Total number of nameserver objects for this repository | INT
SUM\_OUTGOING\_TRANSFERS | 1 | 1 | Total number of pending outgoing transfers for this repository | INT
SUM\_OUTGOING\_TRANSFERS\_&lt;ZONE&gt; | 0 | N | Only stated if wide is set to `1`: Total number of pending outgoing transfers for each zone of the repository | INT
SUM\_PENDING\_DOMAINS | 1 | 1 | Total number of domains on this repository with a "pending" status | INT
SUM\_PENDING\_DOMAINS\_&lt;ZONE&gt; | 0 | N | Only stated if wide is set to `1`: Total number of domains with a "pending" status listed for each zone of the repository  | INT
SUM\_PROCESSING\_DOMAINS | 1 | 1 | Total number of domains of this repository with status "PROCESSING" | INT
SUM\_REQUESTED\_DOMAINS | 1 | 1 | Total number of domains of this repository with status "REQUESTED" | INT
SUM\_TRADES | 1 | 1 | Total Number of pending trades for this repository | INT
SUM\_TRADES\_&lt;ZONE&gt; | 0 | N | Only stated if wide is set to `1`: Total Number of pending trades listed for each zone of the repository  | INT
SUM\_WHOIS\_QUERIES | 1 | 1 | Total number of Whois log entries for this repository | INT
ZONE [0..N] | 0 | N | Only stated if wide is set to `1`: The individual zones of the repository| TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainRepository
REPOSITORY = SE-OTE-1API1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUS_ACCOUNT_AVAILABLE][0] = 0
PROPERTY[SUM_ACTIVE_DOMAINS][0] = 856
PROPERTY[SUM_CONTACTS][0] = 1047
PROPERTY[SUM_DOMAINS][0] = 971
PROPERTY[SUM_INCOMING_TRANSFERS][0] = 0
PROPERTY[SUM_NAMESERVERS][0] = 167
PROPERTY[SUM_OUTGOING_TRANSFERS][0] = 0
PROPERTY[SUM_PENDING_DOMAINS][0] = 0
PROPERTY[SUM_PROCESSING_DOMAINS][0] = 0
PROPERTY[SUM_REQUESTED_DOMAINS][0] = 0
PROPERTY[SUM_TRADES][0] = 0
PROPERTY[SUM_WHOIS_QUERIES][0] = 0
EOF
```

----
