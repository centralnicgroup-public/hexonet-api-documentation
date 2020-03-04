# ModifyDomainApplication

## DESCRIPTION
With this command dedicated parameters of an existing domain application can be modified.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyDomainApplication` | COMMAND
ADMINCONTACT[0..2] | 0 | Contact Handle ID | CONTACT or NULL
APPLICATION | 1 | The application ID | INT or NULL
AUTH | 0 | The domain's authorization code | TEXT or NULL
BILLINGCONTACT[0..2] | 0 | Contact Handle ID | CONTACT or NULL
CLASS | 0 | The class of the application | TEXT or NULL
INCOMPLETE | 0 | If set to `1` the modification request will be accepted even if not all required parameters are set for the application | INT or NULL
NAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME or NULL
NOTICE-POA-ACCEPT-HASH | 0 | By submitting this parameter the registrant confirms that he is aware that the domain name matches a trademark registered in the Clearinghouse. This parameter can be obtained by querying a StatusTMDBClaim command for the respective claim key | TEXT or NULL
OWNERCONTACT[0..4] | 0 | Contact Handle ID | CONTACT or NULL
PERIOD | 0 | The registration period in years | PERIOD or NULL
TECHCONTACT[0..2] | 0 | Contact Handle ID | CONTACT or NULL
X-ABOGADO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service  | `0`, `1` or NULL
X-ASIA-CED-IDENTNUMBER | 0 | Identification Number / Code of Reference (e.g. Passport number, Business Certificate number, Act or Legislation number/code, etc.) | TEXT or NULL
X-ASIA-CED-OTHERIDENTFORM | 0 | If the legal entity type or form of identification is "other", please enter the appropriate information to support the claim | TEXT or NULL
X-ASIA-CED-OTHERLETYPE | 0 | Other legal entity type | TEXT or NULL
X-ASIA-IPR-APPDATE | 0 | Trademark application date | TEXT or NULL
X-ASIA-IPR-CCLOCALITY | 0 | ISO-3166 Country Code | COUNTRY, `EM`, `BX` or NULL
X-ASIA-IPR-NAME | 0 | Trademark name | TEXT or NULL
X-ASIA-IPR-NUMBER | 0 | Trademark number | TEXT or NULL
X-ASIA-IPR-REGDATE | 0 |  Trademark registration date  | TEXT or NULL
X-ASIA-MAINTAINERURL | 0 | This parameter can be used to display information about the maintainer, e.g. the provider of the domain, in the .ASIA whois | TEXT or NULL
X-ASIA-NOTF-CONTACT | 0 |  With this parameter you can specify an Operations and Notifications Contact (OPN/NOTF Contact) to designate the point of contact to whom documentary evidence requests, auction invitations, and reminders are to be sent | CONTACT or NULL
X-ASIA-REGAGENT-CONTACT | 0 |  With this parameter, a contact handle can be used to display the provider or reseller through whose system the .ASIA domain has been registered | CONTACT or NULL
X-ATTORNEY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-BAYERN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BERLIN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BROKER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CA-DISCLOSE | 0 | Set to `1` to disclose the registrant contact details | `0`, `1` or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CAT-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CFD-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CORE-INTENDED-USE | 0 | Paremeter describing the intended use for the domain name | TEXT or NULL
X-DE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-DENTIST-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-DISCLOSE | 0 | Set to `1` to disclose the domain's details | `0`, `1` or NULL
X-FOREX-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-REGISTRANT-BIRTH-DATE | 0 | Birth date of the registrant | TEXT or NULL
X-FR-REGISTRANT-BIRTH-PLACE | 0 | Birth place of the registrant | TEXT or NULL
X-FR-REGISTRANT-DISCLOSE | 0 | Setting this parameter to `1` discloses the registrant's details | TEXT or NULL
X-FR-REGISTRANT-DUNS-NUMBER | 0 | The DUNS number is a nine-digit number, issued by Dun & Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this parameter | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | Date of the declaration of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 |  Publication date of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-JO-NUMBER | 0 | Trademark registration journal number | TEXT or NULL
X-FR-REGISTRANT-JO-PAGE | 0 | Trademark registration journal page | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM | 0 | Legal form of the entity (in case registrant is not a natural person) | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | Other form than the possible values of the above parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-ID | 0 | ID of the registrant | TEXT or NULL
X-FR-REGISTRANT-LOCAL-ID | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | Companies with a European trademark can additionally add their trademark number using this parameter | TEXT or NULL
X-GAY-ACCEPT-REQUIREMENTS | 0 | Set to `1` to accept the policy and enforcement terms | `0`, `1` or NULL
X-HAMBURG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-HEALTH-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1`
X-IT-PIN | 0 | Taxpayer number for .IT domain registrations | TEXT or NULL
X-IT-ACCEPT-LIABILITY-TAC | 0 | Accepts "Section 3 - Declarations and assumptions of liability" | `0`, `1` or NULL
X-IT-ACCEPT-REGISTRATION-TAC | 0 | Accepts "Section 5 - Consent to the processing of personal data for registration" | `0`, `1` or NULL
X-IT-ACCEPT-EXPLICIT-TAC | 0 | Accepts "Section 7 - Explicit acceptance of the following points" | `0`, `1` or NULL
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | Accepts - "Section 6 - Consent to the processing of personal data for diffusion and accessibility via the internet" | `0`, `1` or NULL
X-IDNUMBER | 0 | Domain contacts' personal or organizational identification number | TEXT or NULL
X-LAW-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-LAWYER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-MARKETS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-NICSE-DISCLOSE | 0 | If set to `1` the registrant's details get disclosed | `0`, `1` or NULL
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-NU-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .NU domains | `0`, `1` or NULL
X-NYC-REGISTRANT-NEXUS-CATEGORY | 0 | The value of this parameter has to be either <br>`1` for a natural person whose primary place of domicile is a valid physical address in the City of New York or <br> `2` for an entity or organization that has a physical street address in the City of New York | `1`, `2` or NULL
X-PM-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-REGISTRANT-IDNUMBER | 0 | The registrant's ID number | TEXT or NULL
X-RUHR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .SE domains | `0`, `1` or NULL
X-SPREADBETTING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-SWISS-REGISTRANT-ENTERPRISE-ID | 0 |  The enterprise ID, in the specific context of .swiss based on current rules, is the Swiss UID/IDE/IDI | TEXT
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-TEL-PUBLISH | 0 | If set to `N`, the registrant's contact data will not be shown in the WHOIS | `Y`, `N` or NULL
X-TEL-WHOISTYPE | 0 | With this parameter the way the domain will be displayed in the WHOIS can be selected  | `Legal`, `Natural` or NULL
X-TF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service  | `0`, `1` or NULL
X-TRADING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL
X-MAKEUP-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-BIBLE-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ECO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-HOMES-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-VATID | 0 |  Domain contacts' VAT-ID | TEXT or NULL
X-WF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service  | `0`, `1` or NULL
X-XXX-ACCEPT-REGISTRATION-TAC | 0 |  Set to `1` to accept the terms and conditions of the registration | NULL, `1` or `0`
X-XXX-MEMBERSHIP-CONTACT | 0 | Contact Handle ID | CONTACT or NULL
X-XXX-NON-RESOLVING | 0 | Set to `1` if the domain should not resolve | `0`, `1` or NULL
X-YT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service  | `0`, `1` or NULL

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
531	| Authorization failed
540	| Attribute value is not unique
541	| Invalid attribute value
549 | Command Failed
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
COMMAND = ModifyDomainApplication
APPLICATION = 12293
NAMESERVER0 = ns1.hexonet.net
NAMESERVER1 = ns2.hexonet.net
NAMESERVER2 = ns3.hexonet.net
TECHCONTACT0 = P-TCN1378880
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[APPLICATION][0] = 12293
PROPERTY[AUTH][0] = 84yeSvrqW:ax
PROPERTY[CLASS][0] = COM_BACKORDER
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2017-11-08 11:47:54
PROPERTY[DOMAIN][0] = 1test12.com
PROPERTY[DOMAINUMLAUT][0] = 1test12.com
PROPERTY[NAMESERVER][0] = ns1.hexonet.net
PROPERTY[NAMESERVER][1] = ns2.hexonet.net
PROPERTY[NAMESERVER][2] = ns3.hexonet.net
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[PEERUSER][0] =
PROPERTY[PERIOD][0] = 1
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[SMD][0] =
PROPERTY[STATUS][0] = REQUESTED
PROPERTY[SUBCLASS][0] = COM_BACKORDER
PROPERTY[TECHCONTACT][0] = P-TCN1378880
PROPERTY[UPDATEBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2017-11-08 11:51:16
PROPERTY[USER][0] = test.user
EOF
```

----
## NOTES

* It is not possible to convert an EOI into an application by executing this command.
