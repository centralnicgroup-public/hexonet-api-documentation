# QueryDomainApplicationList

## DESCRIPTION
Query a list of domain applications.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryDomainApplicationList` | COMMAND
WIDE | 0 | If set to `1`: verbose output (more parameters) | `1` or `0`
FIRST | 0 |  Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned. The system has a default value for performance purposes | INT
ORDERBY | 0 | Parameter by which the output will be sorted.<br>Must be one of the following:<br>`CLASS`, `CLASSDESC`, `DOMAIN`, `DOMAINDESC`, `USER`, `USERDESC`, `CREATEDDATE`, `CREATEDDATEDESC`, `UPDATEDDATE`, `UPDATEDDATEDESC`, `REGISTRATIONEXPIRATIONDATE`, `REGISTRATIONEXPIRATIONDATEDESC`, `REGISTRAR`, `REGISTRARDESC` | TEXT
USERDEPTH | 0 | Depth of the list, may be: `SELF`, `SUBUSER` or `ALL`. Default is `ALL` | `SELF`, `SUBUSER` or `ALL`
CLASS | 0 | Search for: Class (see domain feature management commands) | PATTERN
CLASS[0..N] | 0 | Search for several classes at once | PATTERN
STATUS | 0 | Search for: Status | PATTERN
DOMAIN | 0 | Search for: Domain | PATTERN
DOMAIN[0..N] | 0 | Search for several domains at once | DOMAIN
DOMAINREGEX | 0 | Only list applications for domains which match the regular expression stated here, e.g. `^te.*\.com` would match only .com domains that start with "te" | TEXT or NULL
OWNERCONTACT | 0 | Search for: Owner/Registrant Contact Handle ID | CONTACT or NULL

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | INT
FIRST | 1 | 1 | The index of the first entry | INT
LAST | 1 | 1 | The index of the last entry | INT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | INT
TOTAL | 1 | 1 | The total number of entries found | INT
ADMINCONTACT[0..N] | 0 | N | The Administrative Contact | TEXT
APPLICATION[0..N] | 0 | N | The Application ID | INT
BILLINGCONTACT[0..N] | 0 | N | The Billing Contact | TEXT
CLAIMKEY[0..N] | 0 | N | The unique notice identifier of a Trademark Claim | TEXT
CLASS[0..N] | 0 | N | The class of the domain application | TEXT
CREATEDDATE[0..N] | 0 | N | Creation date of the application | DATETIME
DOMAIN[0..N] | 0 | N | Domain name | TEXT
DOMAINUMLAUT[0..N] | 0 | N | Domain name displayed as an IDN | TEXT
EXPIRATIONDATE[0..N] | 0 | N | The expiration date of the domain, if available | DATETIME
INVALIDPARAMETER[0..N] | 0 | N | List of parameter which are not valid and need to be corrected for the application | TEXT
MISSINGPARAMETER[0..N] | 0 | N | List of missing parameters which still need to be added to the application | TEXT
NAMESERVER[0..N] | 0 | N | The nameservers to be set | TEXT
OWNERCONTACT[0..N] | 0 | N | The Registrant/Owner | TEXT
PARENTUSER[0..N] | 0 | N | The parent user ID | TEXT
STATUS[0..N] | 0 | N | Current status of the application | TEXT
TECHCONTACT[0..N] | 0 | N | The Technical Contact | TEXT
UPDATEDDATE[0..N] | 0 | N | Last modification date of the application | UPDATEDDATE
USER[0..N] | 0 | N | The user ID to which the application belongs | TEXT
X-DOMAIN-ROID[0..N] | 0 | N | The ROID (unique identifier) for the application | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryDomainApplicationList
DOMAIN = hexonet-application.*
LIMIT = 2
WIDE = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 2
PROPERTY[LIMIT][0] = 2
PROPERTY[ADMINCONTACT][0] =
PROPERTY[ADMINCONTACT][1] =
PROPERTY[APPLICATION][0] = 10698
PROPERTY[APPLICATION][1] = 10699
PROPERTY[BILLINGCONTACT][0] =
PROPERTY[BILLINGCONTACT][1] =
PROPERTY[CLAIMKEY][0] =
PROPERTY[CLAIMKEY][1] =
PROPERTY[CLASS][0] = ASIA_BACKORDER
PROPERTY[CLASS][1] = COM_BACKORDER
PROPERTY[CREATEDDATE][0] = 2016-10-06 12:37:15
PROPERTY[CREATEDDATE][1] = 2016-10-06 12:38:17
PROPERTY[DOMAIN][0] = hexonet-application.asia
PROPERTY[DOMAIN][1] = hexonet-application.com
PROPERTY[DOMAINUMLAUT][0] = hexonet-application.asia
PROPERTY[DOMAINUMLAUT][1] = hexonet-application.com
PROPERTY[EXPIRATIONDATE][0] =
PROPERTY[EXPIRATIONDATE][1] =
PROPERTY[INVALIDPARAMETER][0] =
PROPERTY[INVALIDPARAMETER][1] =
PROPERTY[MISSINGPARAMETER][0] =
PROPERTY[MISSINGPARAMETER][1] =
PROPERTY[NAMESERVER][0] =
PROPERTY[NAMESERVER][1] =
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[OWNERCONTACT][1] = P-TUE1378025
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[PARENTUSER][1] = demo.hexonet.net
PROPERTY[PEERUSER][0] =
PROPERTY[PEERUSER][1] =
PROPERTY[STATUS][0] = REQUESTED
PROPERTY[STATUS][1] = ACTIVE
PROPERTY[TECHCONTACT][0] =
PROPERTY[TECHCONTACT][1] =
PROPERTY[UPDATEDDATE][0] = 2016-10-06 12:37:15
PROPERTY[UPDATEDDATE][1] = 2016-10-06 12:38:17
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
PROPERTY[X-DOMAIN-ROID][0] =
PROPERTY[X-DOMAIN-ROID][1] =
EOF
```

----
