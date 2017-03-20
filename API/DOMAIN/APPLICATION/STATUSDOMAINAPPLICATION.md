# StatusDomainApplication

## DESCRIPTION
Query information on a domain application.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainApplication` | COMMAND
APPLICATION | 1 | Application ID | TEXT

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
530	| Authentication failed
531	| Authorization failed
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
549	| Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT | 0 | 1 | The Administrative Contact | TEXT
APPLICATION | 1 | 1 | The application ID | TEXT
AUTH | 1 | 1 | Auth-Code | TEXT
BILLINGCONTACT | 0 | 1 | The Billing Contact | TEXT
CLASS | 1 | 1 | The class of the application e.g. `COM_BACKORDER` | TEXT
CREATEDBY | 1 | 1 | Registrar which has created the application, `SYSTEM` in the meantime | TEXT
CREATEDDATE | 1 | 1 | The creating date of the application | DATETIME
DOMAIN | 1 | 1 | Domain name | TEXT
DOMAINUMLAUT | 1 | 1 | Umlautversion of DOMAIN if IDN Application | TEXT
NAMESERVER[0..N] | 0| N | Nameserver(s) used for the activation of the domain | TEXT
OWNERCONTACT | 0 | 1 | The Registrant/Owner | TEXT
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PERIOD | 1 | 1 | Registration period in years | INT
SMD | 1 | 1 | Returns the SMD file stored with the application | TEXT or NULL
STATUS | 1 | 1 | Current status of the application | TEXT
SUBCLASS | 1 | 1 | The subclass of the application e.g. `COM_BACKORDER` | TEXT
TECHCONTACT | 0 | 1 | The Technical Contact | TEXT
UPDATEDBY | 1 | 1 | Registrar which has last updated the application, `SYSTEM` in the meantime | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the application | DATETIME
USER | 1 | 1 | The user ID to which the application belongs | TEXT
X-EU-REGISTRANT-LANG | 1 | 1 | For .EU domain applications: Language of the domain registrant (used for registry emails) | TEXT
X-DOMAIN-ROID | 0 | 1 | Unique identifier of the application at the registry | TEXT
AUCTION-URL | 0 | 1 | URL to the auction page | TEXT
AUCTION-BIDDERSTATUS | 0 | 1 | Current bidderstatus | TEXT
AUCTION-NUMBEROFBIDS | 0 | 1 | Total number of bids | TEXT
AUCTION-NUMBEROFBIDDERS | 0 | 1 | Total number of bidders | TEXT
AUCTION-STARTDATE | 0 | 1 | Startdate of auction | DATETIME
AUCTION-ENDDATE | 0 | 1 | Endate of auction | DATETIME
AUCTION-STATUS | 0 | 1 | Status of the running auction | TEXT
AUCTION-CURRENCY | 0 | 1 | Auction currency | TEXT
AUCTION-MINIMUMBID | 0 | 1 | Minimum bid | TEXT
AUCTION-MINIMUMNEXTBID | 0 | 1 | Minimum bid to submit next | TEXT
AUCTION-BESTBID | 0 | 1 | Best bid of auction | TEXT
AUCTION-PRICE | 0 | 1 | Final price if AUCTION-STATUS is `AUCTION-WON` | TEXT
AUCTION-VAT | 0 | 1 | VAT of AUCTION-PRICE if AUCTION-STATUS is `AUCTION-WON` | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainApplication
APPLICATION = 10699
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[APPLICATION][0] = 10699
PROPERTY[AUTH][0] = X::xiG-zM3T2
PROPERTY[CLASS][0] = COM_BACKORDER
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-10-06 12:38:17
PROPERTY[DOMAIN][0] = hexonet-application.com
PROPERTY[DOMAINUMLAUT][0] = hexonet-application.com
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[PEERUSER][0] =
PROPERTY[PERIOD][0] = 1
PROPERTY[SMD][0] =
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[SUBCLASS][0] = COM_BACKORDER
PROPERTY[UPDATEBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-10-06 12:38:17
PROPERTY[USER][0] = test.user
EOF
```

----
