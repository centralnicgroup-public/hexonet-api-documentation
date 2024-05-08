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
DOMAINAUTH | 0 | Domain name and authorization code provided as one parameter; must have the form "DOMAIN AUTH" | TEXT
AUTH | 0 | The domain's authorization code | TEXT
EMAILLANGUAGE | 0 | For some registries/TLDs an email is sent during the domain transfer process. This parameter specifies the language of this email.<br> If the desired language is not available, the English version of the email will be sent. Currently the following languages are available for gTLD transfers:<br>en_US: English<br>de_DE: German and English<br>sv_SE: Swedish and English<br><br> The default value comes from the environment key "\_system/gtld/transfer/emaillanguage". | TEXT
EMAILURL | 0 | For some registries/TLDs an email is sent during the domain transfer process. This email can include a confirmation link allowing the recipient to confirm the domain transfer. The URL for this link can be specified by this parameter. You can use the following place holders which will be replaced accordingly:<br>{ACTION}: transfer operation<br>{DOMAIN}: domain that is supposed to get transferred<br>{TRIGGER}: trigger code through which the email recipient is validated<br>{LANGUAGE}: the language of the confirmation page (Same value as EMAILLANGUAGE)<br><br>The default value comes from the environment key "\_system/gtld/transfer/url"<br><br>If this parameter is not specified and the respective environment key does not exists for the user account the following URL will be taken which leads to our whitelabel confirmation page:<br> http<nolink>://icann-transfers.info/?domain={DOMAIN}&action={ACTION}&trigger={TRIGGER}&form_language={LANGUAGE} | TEXT
EMAILTAC | 0 | For some registries/TLDs an email is sent during the domain transfer process. This email can contain a link to the Terms and Conditions of the new registrar/reseller. The link to those Terms and Conditions can be specified with this parameter. <br><br>The default value comes from the environment key "\_system/gtld/transfer/tac" | TEXT
EMAILSENDER | 0 | For some registries/TLDs an email is sent during the domain transfer process. Since an email with a foreign sender address is much more likely to be considered spam, only the reply-to address of the email may be specified using this parameter. <br><br>The default value comes from the environment key "\_system/gtld/transfer/emailsender" | TEXT or NULL
EMAILSUBJECT | 0 | For some registries/TLDs an email is sent during the domain transfer process. The subject of this email can be specified by this parameter. It may contain the following place holders which will be replaced accordingly:<br>{ACTION}: transfer operation<br>{DOMAIN}: domain that is supposed to get transferred<br>{TRIGGER}: trigger code through which the email recipient is validated<br><br>The default value comes from the environment key "\_system/gtld/transfer/emailsubject" | TEXT or NULL
EMAILTO | 0 | For some registries/TLDs an email is sent during the domain transfer process. <br>When this parameter is used, the system checks if the provided email address matches one of those email addresses to which the email will be sent. If it does not, the command will fail.| EMAIL or NULL
REQUESTENTITY | 0 | Organization requesting the transfer. <br>The default value comes from the environment key  "user-info/contact/company/organization". | TEXT
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
OWNERCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
ADMINCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
TECHCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
BILLINGCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
X-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions of the registration | `0`, `1` or NULL
X-REGISTRANT-BIRTHDATE | 0 | The registrant's birthdate | TEXT or NULL
X-ADMIN-BIRTHDATE | 0 | The admin's birthdate | TEXT or NULL
X-TECH-BIRTHDATE | 0 | The technical contact's birthdate | TEXT or NULL
X-BILLING-BIRTHDATE | 0 | The billing contact's birthdate | TEXT or NULL
X-REGISTRANT-BIRTHPLACE | 0 | The registrant's birthplace | TEXT or NULL
X-ADMIN-BIRTHPLACE | 0 | The admin's birthplace | TEXT or NULL
X-TECH-BIRTHPLACE | 0 | The technical contact's birthplace | TEXT or NULL
X-BILLING-BIRTHPLACE | 0 | The billing contact's birthplace | TEXT or NULL
X-VATID | 0 | Domain contact's VAT-ID | TEXT or NULL
X-REGISTRANT-VATID | 0 | The registrant's VAT-ID | TEXT or NULL
X-ADMIN-VATID | 0 | The admin's VAT-ID | TEXT or NULL
X-TECH-VATID | 0 | The technical contact's VAT-ID | TEXT or NULL
X-BILLING-VATID | 0 | The billing contact's VAT-ID | TEXT or NULL
X-IDNUMBER | 0 | Domain contacts' ID number | TEXT or NULL
X-REGISTRANT-IDNUMBER | 0 | The registrant's ID number | TEXT or NULL
X-ADMIN-IDNUMBER | 0 | The admin's ID number | TEXT or NULL
X-TECH-IDNUMBER | 0 | The technical contact's ID number | TEXT or NULL
X-BILLING-IDNUMBER | 0 | The billing contact's ID number | TEXT or NULL
X-IDAUTHORITY | 0 | Authority that has issued the domain contacts' personal or organizational identification number | TEXT or NULL
X-REGISTRANT-IDAUTHORITY | 0 | Authority that has issued the registrant's ID number | TEXT or NULL
X-ADMIN-IDAUTHORITY | 0 | Authority that has issued the admin's ID number | TEXT or NULL
X-TECH-IDAUTHORITY | 0 | Authority that has issued the technical contact's ID number | TEXT or NULL
X-BILLING-IDAUTHORITY | 0 | Authority that has issued the billing contact's ID number | TEXT or NULL
X-IPR-NUMBER | 0 | Trademark number | TEXT or NULL
X-IPR-NAME | 0 | Trademark name | TEXT or NULL
X-AE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions of the registration | `0`, `1` or NULL
X-BR-ACCEPT-TRUSTEE-TAC | 0 | Set to `1` to accept the terms and conditions of the registration | `0`, `1` or NULL
X-CA-ACCEPT-AGREEMENT-VERSION | 0 | Version of the registrant agreement that is being accepted | TEXT or NULL
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CL-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-DE-ACCEPT-TRUSTEE-TAC | 0 | Activate the trustee service for a .DE domain | `0`, `1` or NULL
X-DE-ABUSE-CONTACT | 0 | Abuse contact information for the domain that will be displayed by the registry. Value must consist of a valid URI template string, either a mailto link (e.g. `mailto:contact@example.com` ) or a valid http/https URL (e.g. `https://mycontactform.example`). If not given the domain will keep the currently set Abuse contact | TEXT or NULL
X-DE-GENERAL-REQUEST | 0 | General request contact information for the domain that will be displayed by the registry. Value must consist of a valid URI template string, either a mailto link (e.g. `mailto:contact@example.com` ) or a valid http/https URL (e.g. `https://mycontactform.example`). If not given the domain will keep the currently set General request contact| TEXT or NULL
X-EU-ACCEPT-TRUSTEE-TAC | 0 | Activate the trustee service for a .EU domain | `0`, `1` or NULL
X-EU-REGISTRANT-CITIZENSHIP | 0 | Citizenship of the registrant. Only relevant for natural persons with an European citizenship residing outside of the EU | `at`, `be`, `bg`, `cz`, `cy`, `de`, `dk`, `es`, `ee`, `fi`, `fr`, `gr`, `hu`, `ie`, `it`, `lt`, `lu`, `lv`, `mt`, `nl`, `pl`, `pt`, `ro`, `se`, `sk`, `si` or `hr`
X-FI-IDNUMBER | 0 | Registrant's personal or organizational identification number; only relevant for .FI domains | TEXT or NULL
X-FI-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-FI-DOMAIN-NAME-HOLDER-COMPANY-TYPE | 0 | Type of company applying for an .FI domain; possible values:<br>`0`: Private person<br>`1`: Company (default)<br>`2`: Association<br>`3`: Foundation<br>`4`: Municipality<br>`5`: Political party<br>`6`: State<br>`7`: Public corporation | INT or NULL
X-FI-BASED-ON-PERSON-NAME | 0 | Set to `1` in order to indicate that the domain name is based on the personal or company name of the registrant; only relevant for .FI domains | TEXT or NULL
X-FI-PERSON-NAME-REGISTRATION-ID | 0 | The register where the company name on which the domain name is based has been registered; only relevant for .FI domains | INT or NULL
X-FI-PERSON-NAME-REGISTRATION-NUMBER | 0 | The registration number of the registered company name on which the domain name is based; only relevant for .FI domains | TEXT or NULL
X-FR-ACCEPT-TRANSFER-TAC | 0 | Set to `1` to accept the .FR transfer terms and conditions | `0`, `1` or NULL
X-FR-ADMIN-DISCLOSE | 0 | Set to `1` to disclose the administrators's details | TEXT or NULL
X-FR-REGISTRANT-DISCLOSE | 0 | Setting this parameter to `1` discloses the registrant's details | TEXT or NULL
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | Companies with a European trademark can additionally add their trademark number using this parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM | 0 | Legal form of the entity (in case registrant is not a natural person) | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | Other form than the possible values of the above parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-ID | 0 | Companies having their head office in the territory of the European Union must provide their VAT-ID with this parameter| TEXT or NULL
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | The date of declaration of the association | TEXT or NULL
X-FR-REGISTRANT-JO-NUMBER | 0 | The number of the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-JO-PAGE | 0 | The page of the announcement in the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | The date of publication in the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-DUNS-NUMBER | 0 | The DUNS number is a nine-digit number, issued by Dun & Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this parameter | TEXT or NULL
X-FR-REGISTRANT-LOCAL-ID | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-HU-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-IT-PIN | 0 | If the registrant is an individual the PIN has to be either the registrant's fiscal code or the number of an idenity document. <br>For organizations the PIN has to be the company's fiscal code or the company's VAT-ID | TEXT or NULL
X-IT-ACCEPT-TRUSTEE-TAC | 0 | Activate the trustee service for a .IT domain | `0`, `1` or NULL
X-IT-REGISTRANT-ENTITY-TYPE | 0 | In some special cases you need to specify the exact entity type of the registrant:<br>`1`: Italian and foreign natural persons<br>`2`: Italian Companies / one man companies<br>`3`:  freelance workers / professionals <br>`4`: non-profit organizations<br>`5`: public organizations<br>`6`: other subjects<br>`7`: foreigners who match 2 - 6 | TEXT or NULL
X-IT-CONSENTFORPUBLISHING | 0 | State if you agree to the .IT Consent for Publishing | `0`, `1` or NULL
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | Accepts - "Section 6 - Consent to the processing of personal data for diffusion and accessibility via the internet" | `0`, `1` or NULL
X-IT-NATIONALITY | 0 | The nationality of the registrant contact if it deviates from the country code | TEXT or NULL
X-JP-ORGANIZATION | 0 | Organization name | TEXT or NULL
X-JP-KANA-ORGANIZATION | 0 | Organization name in Japanese | TEXT or NULL
X-JP-ADDRESS | 0 | Organization address | TEXT or NULL
X-JP-TITLE | 0 | Representative title | TEXT or NULL
X-JP-REGISTRATION-DATE | 0 | Organization registration date | TEXT or NULL
X-JP-REGISTRATION-ADDRESS | 0 |  Organization registration address | TEXT or NULL
X-JP-NAME | 0 | Representative name | TEXT or NULL
X-JP-TYPE | 0 | Representative title | TEXT or NULL
X-JP-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-KR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-LT-REGISTRANT-LEGAL-ID | 0 | Legal entity identification code of the registrant of a .LT domain. Required as of December 1, 2018 if the registrant is a legal entity. | TEXT or NULL
X-MY-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
INTERNALDNS | 0 | Creates the necessary dns zone before submitting application to the registry. | `0`, `1` or NULL
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must match one of the following 3 criteria which can be stated here:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | Document submitted as a proof of the registrant's identity  | LONGTEXT
X-PT-ROID | 0 | The ROID of the domain | TEXT or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SG-RCBID | 0 | The company registration number has to be provided with this parameter if the registrant is a organization from Singapore | TEXT or NULL
X-SK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TRAVEL-UIN | 0 | The "Unique Identification Number" which entitles the owner to be a registrant of a .TRAVEL domain | TEXT or NULL
X-WDRP-RSP | 0 | Name of the RSP appearing in the WDRP email | TEXT or NULL
X-WDRP-URL | 0 | URL of the RSP appearing in the WDRP email | TEXT or NULL
X-WDRP-SIGNATURE[0..3] | 0 | Signature appearing at the end of the WDRP email | TEXT or NULL
X-WDRP-MAILFROM | 0 | Name of the sender used for the WDRP email | TEXT or NULL
X-ERRP-RSP | 0 | Name of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-URL | 0 | URL of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-EMAIL | 0 | Email address of the RSP appearing in the ERRP email | EMAIL or NULL
X-ERRP-PHONE | 0 | Phone number of the RSP appearing in the ERRP email | PHONE or NULL
X-ERRP-TAC-URL | 0 | Terms and Conditions URL of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-SIGNATURE[0..3] | 0 | Signature appearing at the end of the ERRP email | TEXT or NULL
X-WHOIS-URL | 0 | URL to display in our whois | TEXT or NULL
X-WHOIS-RSP | 0 | RSP name to display in our whois | TEXT or NULL
X-WHOIS-BANNER[0..2] | 0 | Text to display in our whois (e.g. Advertising campaign) | TEXT or NULL
X-DOMAINBLOCK | 0 | The ROID of the domainblock | TEXT or NULL
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
