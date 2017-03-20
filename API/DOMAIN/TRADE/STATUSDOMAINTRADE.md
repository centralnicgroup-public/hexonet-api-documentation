# StatusDomainTrade

## DESCRIPTION
Query status of a domain trade in progress.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainTrade` | COMMAND
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
531 | Authorization failed
540 | Attribute value is not unique
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT[0..N] | 0 | N | New administrative contact | CONTACT
BILLINGCONTACT[0..N] | 0 | N | New billing contact | CONTACT
HOST[0..N] | 0 | N | Domain host | TEXT
NAMESERVER[0..N] | 0 | N | Domain nameserver | TEXT
OLD-ADMINCONTACT[0..N] | 0 | N | Old administrative contact | CONTACT
OLD-BILLINGCONTACT[0..N] | 0 | N | Old billing contact | CONTACT
OLD-OWNERCONTACT[0..N] | 1 | N | Old registrant contact | CONTACT
OLD-REGISTRAR | 1 | 1 | Old registrar | TEXT
OLD-TECHCONTACT[0..N] | 0 | N | Old technical contact | CONTACT
OWNERCONTACT[0..N] | 1 | N | New registrant contact | CONTACT
OWNERCONTACT0ENTITYTYPE | 0 | 1 | Entity type of the new registrant contact | TEXT
REPOSITORY | 1 | 1 | Domain repository | TEXT
REPOSITORYADMINCONTACT[0..N] | 0 | N | New repository administrative contact | CONTACT
REPOSITORYBILLINGCONTACT[0..N] | 0 | N | New repository billing contact | CONTACT
REPOSITORYOLD-ADMINCONTACT[0..N] | 0 | N | Old repository administrative contact | CONTACT
REPOSITORYOLD-BILLINGCONTACT[0..N] | 0 | N | Old repository billing contact | CONTACT
REPOSITORYOLD-OWNERCONTACT[0..N] | 1 | N | Old repository registrant contact | CONTACT
REPOSITORYOLD-TECHCONTACT[0..N] | 0 | N | Old repository technical contact | CONTACT
REPOSITORYOWNERCONTACT[0..N] | 1 | N | New repository registrant contact | CONTACT
REPOSITORYTECHCONTACT[0..N] | 0 | N | New repository technical contact | CONTACT
TECHCONTACT[0..N] | 0 | N | New technical contact | CONTACT
TRANSFERLOG[0..N] | 1 | N | Transfer/Trade log entries | TEXT
TRANSFERSTATUS | 1 | 1 | Transfer/Trade status; can be `INITIATED`, `REQUESTED`, `PENDING`, `SUCCESSFUL`, `FAILED` | TEXT
TRANSFERTYPE | 1 | 1 | Transfer/Trade type; can be `INCOMING`, `OUTGOING`, `TRADE` | TEXT
X-NICSE-IDNUMBER | 0 | 1 | Swedish personal or organizational number; only relevant for .SE and .NU domains | TEXT
X-NICSE-VATID | 0 | 1 | VAT-ID; only relevant for .SE and .NU domains | TEXT
X-NO-REGISTRANT-IDENTITY | 0 | 1 | Norwegian organization number; only relevant for .NO domains | TEXT
X-PT-REGISTRANT-VATID | 0 | 1 | VAT-ID; only relevant for .PT domains | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainTrade
DOMAIN = test-trade3.org
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ADMINCONTACT][0] = USER
PROPERTY[BILLINGCONTACT][0] = USER
PROPERTY[NAMESERVER][0] = ns1.ispapi.net
PROPERTY[NAMESERVER][1] = ns2.ispapi.net
PROPERTY[OLD-ADMINCONTACT][0] = P-TUH1260830
PROPERTY[OLD-BILLINGCONTACT][0] = P-TUH1260830
PROPERTY[OLD-OWNERCONTACT][0] = P-TUH1384046
PROPERTY[OLD-REGISTRAR][0] = hexonet
PROPERTY[OLD-TECHCONTACT][0] = P-TUH1260830
PROPERTY[OWNERCONTACT][0] = P-TUH1384050
PROPERTY[REPOSITORY][0] = ORG-OTE-1API1
PROPERTY[REPOSITORYADMINCONTACT][0] = TUH1260830-JKDP
PROPERTY[REPOSITORYBILLINGCONTACT][0] = TUH1260830-JKDP
PROPERTY[REPOSITORYOLD-ADMINCONTACT][0] = TUH1260830-JKDP
PROPERTY[REPOSITORYOLD-BILLINGCONTACT][0] = TUH1260830-JKDP
PROPERTY[REPOSITORYOLD-OWNERCONTACT][0] = TUH1384046-AWOK
PROPERTY[REPOSITORYOLD-TECHCONTACT][0] = TUH1260830-JKDP
PROPERTY[REPOSITORYOWNERCONTACT][0] = TUH1384050-EERN
PROPERTY[REPOSITORYTECHCONTACT][0] = TUH1260830-JKDP
PROPERTY[TECHCONTACT][0] = USER
PROPERTY[TRANSFERLOG][0] = 2016-11-14 13:33:08 [REQUESTED] domain trade initiated
PROPERTY[TRANSFERLOG][1] = 2016-11-14 13:33:08 [UNCONFIRMED] created APPROVE confirmation email for "Test User" <info@hexonet.net>
PROPERTY[TRANSFERSTATUS][0] = REQUESTED
PROPERTY[TRANSFERTYPE][0] = TRADE
EOF
```

----
