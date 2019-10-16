# CheckDomainTransfer

## DESCRIPTION
Check, if a domain transfer is applicable. The command also gives you back further information on the requested domain name.

## AVAILABILITY
All users have access to this command. The command is not available for all TLD's.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckDomainTransfer` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
AUTH | 0 | The domain's authorization code | TEXT
X-AE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions of the .AE registry | `0`, `1` or NULL
X-EU-REGISTRANT-CITIZENSHIP | 0 | Citizenship of the registrant. Only relevant for natural persons with an European citizenship residing outside of the EU | `at`, `be`, `bg`, `cz`, `cy`, `de`, `dk`, `es`, `ee`, `fi`, `fr`, `gr`, `hu`, `ie`, `it`, `lt`, `lu`, `lv`, `mt`, `nl`, `pl`, `pt`, `ro`, `se`, `sk`, `si` or `hr`
X-LT-REGISTRANT-LEGAL-ID | 0 | Legal entity identification code of the registrant of a .LT domain. Required as of December 1, 2018 if the registrant is a legal entity. | TEXT or NULL
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must match one of the following 3 criteria which can be stated here:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must match one of the following 3 criteria which can be stated here:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-TO-CUSTOMER-HANDLE | 0 | Customer handle; only relevant for .TO domains | TEXT or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
218 | Request is available
219 | Request is not available
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
500 | Invalid command name
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
507 | Invalid command format
521 | Too many sessions open. Server closing connection
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid Attribute value
545 | Object not found
547 | Invalid command sequence
549 | Command Failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT0NAME | 0 | 1 | Name of the administrative contact of the domain | TEXT
AGEINDAYS | 0 | 1 | Age of the domain in days | INT
AUTHISVALID | 1 | 1 | Indicates if the given authcode is valid | `1` or `0`
AUTHREQUIRED | 1 | 1 | Indicates if an authcode is required to initiate the transfer | `1` or `0`
CREATEDDATE | 0 | 1 | Creation date of the domain name | DATETIME
CLASS | 0 | 1 | Class of the domain | TEXT
EXPIRATIONDATE | 0 | 1 | Expiration date of the domain name | DATETIME
NAMESERVER[0..N] | 0 | N | Nameservers currently assigned to the domain | TEXT
OWNERCONTACT0NAME | 0 | 1 | Name of the owner contact of the domain | TEXT
PERIOD[0..N] | 1 | N | Period by which the domain can be renewed during the transfer | TEXT
PERIODRESET | 0 | 1 | Indicates if the expiration date will be reset during the transfer | `0` or `1`
REGISTRAR | 0 | 1 | Registrar the domain is currently registered with | TEXT
REGISTRARID | 0 | 1 | ID of the registrar the domain is currently registered with | TEXT
REGISTRARURL | 0 | 1 | URL of the registrar the domain is currently registered with | TEXT
REPOSITORY | 1 | 1 | Domain repository in which the domain name will be located after the transfer is completed | TEXT
SECDNS-DS | 0 | 1 | Indicates if SEC-DNS is available for the domain name DS data based | TEXT
SECDNS-KEY | 0 | 1 | Indicates if SEC-DNS is available for the domain name DNS KEY data based| TEXT
STATUS | 1 | 1 | Status of the domain name | TEXT
TRANSFERLOCK | 0 | 1 | Indicates if the domain is locked for transfers | `0` or `1`
UPDATEDDATE | 0 | 1 | Updated date of the domain name | DATETIME
USERTRANSFERREQUIRED | 1 | 1 | Indicates if a usertransfer (inter registrar transfer) is required for the domain name | `0` or `1`
WHOISDATE | 0 | 1 | Date of the whois query | DATETIME
WHOISQUERY | 0 | 1 | Query that was sent to the whois server | TEXT
WHOISSERVER[0..N] | 0 | N | Whois servers to query was sent to | TEXT
X-PRICE-CLASS | 0 | 1 | Price class of the domain name | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckDomainTransfer
DOMAIN = example.com
EOF
```
### Response

```
[RESPONSE]
CODE = 219
DESCRIPTION = Request is not available; DOMAIN TRANSFER IS PROHIBITED BY STATUS
PROPERTY[ADMINCONTACT0NAME][0] = % IANA WHOIS server
PROPERTY[AGEINDAYS][0] = 7779
PROPERTY[AUTHISVALID][0] = UNKNOWN
PROPERTY[AUTHREQUIRED][0] = 1
PROPERTY[CREATEDDATE][0] = 1995-08-14 12:00:00
PROPERTY[EXPIRATIONDATE][0] = 2017-08-13 12:00:00
PROPERTY[NAMESERVER][0] = a.iana-servers.net
PROPERTY[NAMESERVER][1] = b.iana-servers.net
PROPERTY[OWNERCONTACT0NAME][0] =
PROPERTY[PERIOD][0] = 1Y
PROPERTY[PERIOD][1] = 2Y
PROPERTY[PERIOD][2] = 3Y
PROPERTY[PERIOD][3] = 4Y
PROPERTY[PERIOD][4] = 5Y
PROPERTY[PERIOD][5] = 6Y
PROPERTY[PERIOD][6] = 7Y
PROPERTY[PERIOD][7] = 8Y
PROPERTY[PERIOD][8] = 9Y
PROPERTY[PERIOD][9] = 10Y
PROPERTY[REGISTRAR][0] = RESERVED-INTERNET ASSIGNED NUMBERS AUTHORITY
PROPERTY[REGISTRARID][0] = 376
PROPERTY[REGISTRARURL][0] = http://res-dom.iana.org
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[STATUS][0] = clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited
PROPERTY[STATUS][1] = clientTransferProhibited https://icann.org/epp#clientTransferProhibited
PROPERTY[STATUS][2] = clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited
PROPERTY[TRANSFERLOCK][0] = 1
PROPERTY[UPDATEDDATE][0] = 2016-08-14 12:00:00
PROPERTY[USERTRANSFERREQUIRED][0] = 0
PROPERTY[WHOISDATE][0] = 2016-12-01 07:25:15
PROPERTY[WHOISDATE][1] = 2016-12-01 07:25:15
PROPERTY[WHOISQUERY][0] = domain example.com
PROPERTY[WHOISQUERY][1] = example.com
PROPERTY[WHOISSERVER][0] = whois.verisign-grs.com
PROPERTY[WHOISSERVER][1] = whois.iana.org
EOF
```

----
