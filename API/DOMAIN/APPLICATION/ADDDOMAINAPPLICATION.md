# AddDomainApplication

## DESCRIPTION
Add a new domain application.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AddDomainApplication` | COMMAND
ADMINCONTACT[0..2] | 0 | The Administrative Contact Handle IDs | CONTACT or NULL
AUTH | 0 | The domain's authorization code | TEXT or NULL
BILLINGCONTACT[0..2] | 0 | The Billing Contact Handle IDs | CONTACT or NULL
CLASS | 1 | Application class (see domain feature management commands) | TEXT
CURRENCY | 0 | For premium domain applications the currency has to be stated here | `/^[A-Z][A-Z][A-Z]$/`
DOMAIN | 1 | Domain name | DOMAIN
EOI | 0 | If you have created an EOI (Expression of interest) for the domain name it can be converted into an application by stating the respective EOI ID here | INT or NULL
INCOMPLETE | 0 |  If set to `1` the application creation request will be accepted even if not all required parameters are given for the application | INT or NULL
LAUNCH-MARK-CODE | 0 | Special allocation token provided by the registry | TEXT or NULL
NAMESERVER[0..12] | 0 | Nameserver hosts | HOSTNAME or NULL
NEW | 0 | Force to create a new application even if an application with the same data exists | `0`, `1` or NULL
NOTICE-POA-ACCEPT-HASH | 0 | By submitting this parameter the registrant confirms that he is aware that the domain name matches a trademark registered in the Clearinghouse. This parameter can be obtained by querying a StatusTMDBClaim command on the respective claim key | TEXT or NULL
ORDER | 0 | Order action:<br>`CREATE` - create an application order<br>`REPLACE` - replace an application order<br>`UPDATE` - update an application order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | Domain application order ID. Will only be considered if the parameter ORDER is set to REPLACE or UPDATE. If the parameter is not stated and the parameter ORDER is set to REPLACE or UPDATE then an auto detection of the order ID will be done. | INT
OWNERCONTACT[0..4] | 0 | Owner/Registrant Contact Handle IDs | CONTACT or NULL
OFFER | 0 | Aftermarket application offer | INT or NULL
PERIOD | 1 | Registration period in years | PERIOD
PRICE | 0 | For premium domain applications the price has to be stated here | `/^[0-9]+(\.[0-9]+)?$/`
SMD[0..N] | 0 | The respective SMD file | LONGTEXT or NULL
SMD | 0 | The respective SMD file | LONGTEXT or NULL
TECHCONTACT[0..2] | 1 |The Technical Contact Handle IDs | CONTACT or NULL
X-ABOGADO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-ALLOCATIONTOKEN | 0 | Allocation token or code for allocating an object like a domain name to the client | TEXT
X-ASIA-CED-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0` or `1`
X-ASIA-CED-CCLOCALITY | 0 | Location or domicile of the Entity (based on the corresponding ISO3166 code) | COUNTRY or NULL
X-ASIA-CED-CONTACT | 0 | Indicates which contact should be used as CED. Must be `registrant`, `admin`, `tech` or `billing` | `registrant`, `admin`, `tech` or `billing`
X-ASIA-CED-IDENTFORM | 0 | Must be one of the following: <br>`passport`<br>`certificate`<br>`legislation`<br>`societyRegistry`<br>`politicalPartyRegistry`<br>`other` | `passport`, `certificate`, `legislation`, `societyRegistry`, `politicalPartyRegistry` or `other`
X-ASIA-CED-IDENTNUMBER | 0 | Identification Number / Code of Reference (e.g. Passport number, Business Certificate number, Act or Legislation number/code, etc.) | TEXT or NULL
X-ASIA-CED-LEGALENTITYTYPE | 0 | Must be one of the following: <br>`naturalPerson`<br>`corporation`<br>`cooperative`<br>`partnership`<br>`government`<br>`politicalParty`<br>`society`<br>`institution`<br>`other Type of Entity` | `naturalPerson`, `corporation`, `cooperative`, `partnership`, `government`, `politicalParty`, `society`, `institution` or `other`
X-ASIA-CED-LOCALITYCITY | 0 | City of establishment of the CED | TEXT or NULL
X-ASIA-CED-LOCALITYSP | 0 | Province of establishment of the CED| TEXT or NULL
X-ASIA-CED-OTHERIDENTFORM | 0 | If the legal entity type or form of identification is "other", please enter the appropriate information to support the claim | TEXT or NULL
X-ASIA-CED-OTHERLETYPE | 0 | Other legal entity type | TEXT or NULL
X-ASIA-IPR-APPDATE | 0 | Trademark application date | TEXT or NULL
X-ASIA-IPR-CCLOCALITY | 0 | ISO-3166 Country Code | COUNTRY, `EM`, `BX` or NULL
X-ASIA-IPR-NAME | 0 | Trademark name | TEXT or NULL
X-ASIA-IPR-NUMBER | 0 | Trademark number | TEXT or NULL
X-ASIA-IPR-REGDATE | 0 | Trademark registration date | TEXT or NULL
X-ASIA-MAINTAINERURL | 0 | This parameter can be used to display information about the maintainer, e.g. the provider of the domain, in the .ASIA whois | TEXT or NULL
X-ASIA-NOTF-CONTACT | 0 | With this parameter you can specify an Operations and Notifications Contact (OPN/NOTF Contact) to designate the point of contact to whom documentary evidence requests, auction invitations, and reminders are to be sent | CONTACT or NULL
X-ASIA-REGAGENT-CONTACT | 0 | With this parameter, a contact handle can be used to display the provider or reseller through whose system the .ASIA domain has been registered | CONTACT or NULL
X-ASSOCIATION-AUTH | 0 | Verification Code for eligible registrants of .LOTTO domains | TEXT or NULL
X-ASSOCIATION-ID | 0 | Membership Contact ID for eligible registrants of .LOTTO domains | TEXT or NULL
X-ATTORNEY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-BACKORDER-LITE | 0 | Set to `1` to create Backorder-Lite | `1`, `0` or NULL
X-BAYERN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BERLIN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BROKER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CFD-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CORE-INTENDED-USE | 0 | Paremeter describing the intended use for the domain name | TEXT or NULL
X-DE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-DENTIST-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-FOREX-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-REGISTRANT-BIRTH-DATE | 0 | Birth date of the registrant | TEXT or NULL
X-FR-REGISTRANT-BIRTH-PLACE | 0 | Birth date of the place | TEXT or NULL
X-FR-REGISTRANT-DISCLOSE | 0 | Setting this parameter to `1` discloses the registrant's details | TEXT or NULL
X-FR-REGISTRANT-DUNS-NUMBER | 0 | The DUNS number is a nine-digit number, issued by Dun & Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this parameter | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | Date of the declaration of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | Publication date of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-JO-NUMBER | 0 | Trademark registration journal number | TEXT or NULL
X-FR-REGISTRANT-JO-PAGE | 0 | Trademark registration journal page | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM | 0 | Legal form of the entity (in case registrant is not a natural person) | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | Other form than the possible values of the above parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-ID | 0 | ID of the registrant | TEXT or NULL
X-FR-REGISTRANT-LOCAL-ID | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | Companies with a European trademark can additionally add their trademark number using this parameter | TEXT or NULL
X-HAMBURG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-IDN-LANGUAGE | 0 |  If the domain is an IDN domain, an IDN language tag is needed which by default gets auto-detected by the system. You can however override the default auto-detection by stating an explicit language tag here.  | TEXT or NULL
X-LAW-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-LAWYER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-MARKETS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-FILM-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-MAKEUP-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-NICSE-DISCLOSE | 0 | If set to `1` the registrant's details get disclosed | `0`, `1` or NULL
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-NYC-REGISTRANT-NEXUS-CATEGORY | 0 |  The value of this parameter has to be either <br>`1` for a natural person whose primary place of domicile is a valid physical address in the City of New York or <br> `2` for an entity or organization that has a physical street address in the City of New York | `1`, `2` or NULL
X-PM-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-BODY | 0 | The body of the accreditation | TEXT or NULL
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-ID | 0 | The ID of the accreditation | TEXT or NULL
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-YEAR | 0 | The year of the accreditation | INT or NULL
X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-CC | 0 | ISO-3166 Country Code | COUNTRY or NULL
X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-STATE | 0 | The state the jurisdiction is located in | TEXT or NULL
X-RUHR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SPREADBETTING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-SWISS-REGISTRANT-ENTERPRISE-ID | 0 | The enterprise ID, in the specific context of .swiss based on current rules, is the Swiss UID/IDE/IDI | TEXT
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-TEL-PUBLISH | 0 | If set to `N`, the registrant's contact data will not be shown in the WHOIS | `Y`, `N` or NULL
X-TEL-WHOISTYPE | 0 | With this parameter the way the domain will be displayed in the WHOIS can be selected | `Legal`, `Natural` or NULL
X-TF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TRADING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-BABY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-BIBLE-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ECO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL
X-UK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-WF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-XXX-ACCEPT-REGISTRATION-TAC | 0 |  Set to `1` to accept the terms and conditions of the registration | NULL, `1` or `0`
X-XXX-MEMBERSHIP-CONTACT | 0 | Contact Handle ID | CONTACT or NULL
X-XXX-NON-RESOLVING | 0 | Set to `1` if the domain should not resolve  | `0`, `1` or NULL
X-YT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
507	| Invalid command format
510	| Command not supported for this class
530 | Authentication failed
531	| Authorization failed
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
547	| Invalid command sequence
549	| Command failed
552	| Object status does not allow for operation


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT | 1 | 1 | The Administrative Contact | TEXT
APPLICATION | 1 | 1 | The application ID | INT
AUTH | 1 | 1 | Auth-Code | TEXT
BILLINGCONTACT | 1 | 1 | The Billing Contact | TEXT
CLASS | 1 | 1 | The class of the application e.g. `COM_BACKORDER` | TEXT
CREATEDBY | 1 | 1 | Entity that created the application | TEXT
CREATEDDATE | 1 | 1 | The creating date of the application | DATETIME
DOMAIN | 1 | 1 | Domain name | TEXT
DOMAINUMLAUT | 1 | 1 | Domain Name displayed as an IDN | TEXT
NAMESERVER[0..N] | 0 | N | Nameservers assigned to the application | TEXT
OWNERCONTACT | 1 | 1 | The Owner/Registrant | TEXT
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PERIOD | 1 | 1 | The registration period | TEXT
SMD | 1 | 1 | Content of the respective SMD file | TEXT or NULL
STATUS | 1 | 1 | Current status of the application | TEXT
SUBCLASS | 1 | 1 | The subclass of the application | TEXT
TECHCONTACT | 1 | 1 | The Technical Contact | TEXT
UPDATEBY | 1 | 1 | Entity that updated the application | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the application | DATETIME
USER | 1 | 1 | The user ID to which the application belongs | TEXT
X-EU-REGISTRANT-LANG | 1 | 1 | For .EU domain applications: Language of the domain registrant (used for registry emails) | TEXT

----
## Example
### Command


```
[COMMAND]
COMMAND = AddDomainApplication
CLASS = backorder
DOMAIN = hexonet-application.com
NAMESERVER0 = ns1.ispapi.net
NAMESERVER1 = ns2.ispapi.net
NAMESERVER2 = ns3.ispapi.net
OWNERCONTACT0 = P-TUE1378025
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[APPLICATION][0] = 10700
PROPERTY[AUTH][0] = ew1,2*YGvEV1
PROPERTY[CLASS][0] = COM_BACKORDER
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-10-06 13:25:53
PROPERTY[DOMAIN][0] = hexonet-application.com
PROPERTY[DOMAINUMLAUT][0] = hexonet-application.com
PROPERTY[NAMESERVER][0] = ns1.ispapi.net
PROPERTY[NAMESERVER][1] = ns2.ispapi.net
PROPERTY[NAMESERVER][2] = ns3.ispapi.net
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[PEERUSER][0] =
PROPERTY[PERIOD][0] = 1
PROPERTY[SMD][0] =
PROPERTY[STATUS][0] = REQUESTED
PROPERTY[SUBCLASS][0] = COM_BACKORDER
PROPERTY[UPDATEBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-10-06 13:25:53
PROPERTY[USER][0] = test.user
EOF
```

----
