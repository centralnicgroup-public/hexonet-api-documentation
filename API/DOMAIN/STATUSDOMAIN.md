# StatusDomain

## DESCRIPTION
Query the status of a domain name.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
REFRESH | 0 | Trigger to refresh domains' properties when set to `1` | `0` or `1`
HOSTTYPE | 0 | Switch how hosts should be returned | `AUTO`, `ATTRIBUTE` or `OBJECT`
REPOSITORYCONTACT | 0 | Return repository contacts also | NULL or `*`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
541	| Invalid attribute value
545	| Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACCOUNTINGDATE | 1 | 1 | The domain's accounting date | DATETIME
ACCOUNTINGPERIOD | 1 | 1 | The domain's accounting period | TEXT
ADMINCONTACT | 1 | 3 | The Administrative Contact | CONTACT
AUTH | 0 | 1 | The Auth-Info Code | TEXT
BILLINGCONTACT | 1 | 3 | The Billing Contact | CONTACT
CLASS | 1 | 1 | Class of the object, returns `DOMAIN` in case of a domain | TEXT
CREATEDBY | 1 | 1 | Registrar that registered the domain | TEXT
CREATEDDATE | 1 | 1 | The creation date of the domain | DATETIME
DELETIONHOLDPERIOD | 1 | 1 | The domain's deletion hold period | TEXT
DELETIONRESTORABLEPERIOD | 1 | 1 | Period in which a deleted domain can still be restored at the registry | TEXT
DESCRIPTION | 1 | 1 | Description of the domain object, currently the domain is returned | TEXT
DOMAINUMLAUT | 1 | 1 | Umlautversion of the domain name in case of an IDN, otherwise, the domain itself is returned | TEXT
EXPIRATIONDATE | 1 | 1 | The expiration date of the domain name | DATETIME
FAILUREDATE | 1 | 1 | The domain's failure date | DATETIME
FAILUREPERIOD | 1 | 1 | The domain's failure period | TEXT
FINALIZATIONDATE | 1 | 1 | The domain's finalization date | DATETIME
FINALIZATIONPERIOD | 1 | 1 | The domain's finalization period | TEXT
HOST | 0 | N | The nameservers managed at the respective registry, if defined. When HOSTYPE is `ATTRIBUTE`, the namservers listed will contain the IPs | NULL or TEXT
HOSTTYPE | 1 | 1 | Returns how the respective registry manages nameservers | TEXT
ID | 1 | 1 | In case of a domain, the domain itself is returned | TEXT
INTERNALNAMESERVER | 0 | N | If internal nameservers are used, they are returned here | TEXT
NAMESERVER | 0 | 13 | The Nameserver hostnames | TEXT
NEXTACTION | 1 | 1 | Indicates what will happen to the domain next, e.g. `expire` when domain is set to AUTOEXPIRE | TEXT
NEXTACTIONDATE | 1 | 1 | The date when the next action will be taken | DATETIME
OWNERCONTACT | 1 | 1 | The Registrant/Owner | CONTACT
PAIDUNTILDATE | 1 | 1 | The date until the domain is paid in the HEXONET renewal system | DATETIME
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PREPAIDPERIOD | 1 | 1 | The domain's prepaid period | TEXT
REGISTRAR | 1 | 1 | Current sponsoring registrar | TEXT
REGISTRARTRANSFERDATE | 0 | 1 | The last transfer date | DATETIME
REGISTRARUPDATEDDATE | 0 | 1 | The date of the last update to the domain | DATETIME
REGISTRATIONEXPIRATIONDATE | 1 | 1 | The registration expiration date | DATETIME
REGISTRATIONGRACEPERIOD | 0 | 1 | Registration grace period of the respective domain | TEXT
RENEWALDATE | 1 | 1 | Date of next renewal | DATETIME
RENEWALMODE | 1 | 1 | Indicates how the domain will be renewed | TEXT
REPOSITORY | 1 | 1 | The domain's repository | TEXT
REPOSITORYADMINCONTACT | 0 | N | Repository contact of the administrative contact , only if REPOSITORYCONTACT is set to `*` | TEXT
REPOSITORYBILLINGCONTACT | 0 | N | Repository contact of the billing contact , only if REPOSITORYCONTACT is set to `*` | TEXT
REPOSITORYOWNERCONTACT | 0 | N | Repository contact of the owner, only if REPOSITORYCONTACT is set to `*` | TEXT
REPOSITORYTECHCONTACT | 0 | N | Repository contact of the technical contact , only if REPOSITORYCONTACT is set to `*` | TEXT
ROID | 0 | 1 | The domain's unique identifier, called ROID | TEXT
STATUS | 1 | N | The current registration status | TEXT
SUBCLASS | 1 | 1 | Subclass of the domain name, mostlikely the TLD is returned | TEXT
TECHCONTACT | 1 | 3 | The Technical Contact | CONTACT
TRADE-OWNERCONTACT[0..N] | 0 | N | The new registrant contact ID(s) after the trade is successful. This parameter signals that a trade is currently being processed | CONTACT
TRANSFERDATE | 1 | 1 | The date when the domain has been transferred last | DATETIME
TRANSFERLOCK | 1 | 1 | Indicates if the domain is locked for transfers | `0`, `1` or NULL
TRANSFERMODE | 1 | 1 | Indicates how the domain will be transferred | TEXT
UPDATEDBY | 1 | 1 | Registrar that updated the domain | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the domain | DATETIME
USER | 1 | 1 | The user that manages this domain | TEXT
X-ACCEPT-WHOISTRUSTEE-TAC | 1 | 1 | Indicates if a Whois Trustee is activated for this domain | `0`, `1` or NULL
X-ACCEPT-WHOISTRUSTEELITE-TAC | 1 | 1 | Indicates if a Whois Trustee  Lite is activated for this domain | `0`, `1` or NULL
X-REGISTRANT-VERIFICATION-EMAIL | 0 | 1 | The email address used for the registrant verification | TEXT
X-REGISTRANT-VERIFICATION-NAME | 0 | 1 | Name of the registrant to verify if a verification is PENDING | TEXT
X-REGISTRANT-VERIFICATION-REQUESTEDDATE | 0 | 1 | The date when the registrant verification has been requested | DATETIME
X-REGISTRANT-VERIFICATION-STATUS | 0 | 1 | The status of the registrant verification | TEXT
X-REGISTRANT-VERIFICATION-TAG | 0 | 1 | Verification TAG of a registrant verification if it is PENDING | TEXT
X-WDRP-RSP | 0 | 1 | Name of domain service provider to show in WDRP emails | TEXT
X-WHOIS-RSP | 0 | 1 | Name of the domain service provider to show in WHOIS | TEXT
X-WHOIS-URL | 0 | 1 | Website URL of the domain service provider to show in WHOIS | TEXT


EOF

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomain
DOMAIN = hexonet-domain.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACCOUNTINGDATE][0] = 2018-09-21 14:53:20
PROPERTY[ACCOUNTINGPERIOD][0] = -5d
PROPERTY[ADMINCONTACT][0] = P-TUE1378025
PROPERTY[AUTH][0] = *OkHRSf/3-xs
PROPERTY[BILLINGCONTACT][0] = P-TUE1378025
PROPERTY[CLASS][0] = DOMAIN
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-09-26 14:53:20
PROPERTY[DELETIONHOLDPERIOD][0] = 5d
PROPERTY[DELETIONRESTORABLEPERIOD][0] = 30d
PROPERTY[DESCRIPTION][0] = hexonet-domain.com
PROPERTY[DOMAINUMLAUT][0] = hexonet-domain.com
PROPERTY[EXPIRATIONDATE][0] = 2017-09-26 14:53:20
PROPERTY[FAILUREDATE][0] = 2018-11-09 14:53:20
PROPERTY[FAILUREPERIOD][0] = 44d
PROPERTY[FINALIZATIONDATE][0] = 2017-09-27 14:53:20
PROPERTY[FINALIZATIONPERIOD][0] = 1d
PROPERTY[HOSTTYPE][0] = OBJECT
PROPERTY[ID][0] = hexonet-domain.com
PROPERTY[INTERNALNAMESERVER][0] = ns1.hexonet.net 194.50.187.20
PROPERTY[INTERNALNAMESERVER][1] = ns1.hexonet.net 194.50.187.30
PROPERTY[INTERNALNAMESERVER][2] = ns1.hexonet.net 194.50.187.135
PROPERTY[INTERNALNAMESERVER][3] = ns2.hexonet.net 194.0.182.1
PROPERTY[NAMESERVER][0] = ns1.hexonet.net
PROPERTY[NAMESERVER][1] = ns2.hexonet.net
PROPERTY[NEXTACTION][0] = finalize
PROPERTY[NEXTACTIONDATE][0] = 2017-09-27 14:53:20
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[PAIDUNTILDATE][0] = 2018-09-26 14:53:20
PROPERTY[PEERUSER][0] =
PROPERTY[PREPAIDPERIOD][0] = 1Y
PROPERTY[REGISTRAR][0] = SYSTEM
PROPERTY[REGISTRARTRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[REGISTRARUPDATEDDATE][0] = 2016-09-26 14:53:20
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-09-26 14:53:20
PROPERTY[REGISTRATIONGRACEPERIOD][0] = 0
PROPERTY[RENEWALMODE][0] = AUTORENEW
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[ROID][0] = 101827933_DOMAIN_COM-VRSN
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[SUBCLASS][0] = COM
PROPERTY[TECHCONTACT][0] = P-TUE1378025
PROPERTY[TRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[TRANSFERLOCK][0] = 0
PROPERTY[UPDATEDBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-09-26 14:53:20
PROPERTY[USER][0] = test.user
PROPERTY[X-ACCEPT-WHOISTRUSTEE-TAC][0] = 0
PROPERTY[X-ACCEPT-WHOISTRUSTEELITE-TAC][0] = 0
PROPERTY[X-REGISTRANT-VERIFICATION-EMAIL][0] = noreply@example.com
PROPERTY[X-REGISTRANT-VERIFICATION-NAME][0] = Test User
PROPERTY[X-REGISTRANT-VERIFICATION-REQUESTEDDATE][0] = 2016-09-26 14:53:20
PROPERTY[X-REGISTRANT-VERIFICATION-STATUS][0] = PENDING
PROPERTY[X-REGISTRANT-VERIFICATION-TAG][0] = 3471E0B25DAD9CCA3145B8AFC8C61193
PROPERTY[X-WDRP-RSP][0] = Test GmbH
PROPERTY[X-WHOIS-RSP][0] = ABC-123
PROPERTY[X-WHOIS-URL][0] = http://cp-ote.hexonet.net
EOF
```

----
