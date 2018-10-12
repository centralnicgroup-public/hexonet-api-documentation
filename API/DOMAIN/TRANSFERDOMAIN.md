# TransferDomain

## DESCRIPTION
Request, approve, deny or cancel a domain transfer.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `TransferDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
ORDER | 0 | Order action:<br>`CREATE` - create a transfer order<br>`REPLACE` - replace a transfer order<br>`UPDATE` - update a transfer order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | Application order ID. Will only be taken into consideration if parameter ORDER is set to `REPLACE` or `UPDATE`. If parameter is not stated and order is `REPLACE` or `UPDATE` an auto detection will be carried out to detect the right order | INT
AUTH | 0 | Auth-Info code, required for some TLDs. | TEXT or NULL
ACTION | 0 | Action, may be one of the following (default value is `REQUEST`):<br>`REQUEST`: Request a transfer-in from another registrar<br>`USERTRANSFER`: Request a usertransfer (internal transfer)<br>`CANCEL`: Cancel a requested transfer-in<br>`APPROVE`: Approve a requested transfer-out<br>`DENY`: Deny a requested transfer-out| `REQUEST`, `APPROVE`, `DENY`, `CANCEL` or `USERTRANSFER`
DOMAINAUTH | 0 | Domain name and authorization code provided as one parameter; must have the form "DOMAIN AUTH" | TEXT
CLASS | 0 | The class of the domain name if it is a premium domain | TEXT
EMAILLANGUAGE | 0 | For some registries/TLDs an email is sent during the domain transfer process. This parameter specifies the language of this email.<br> If the desired language is not available, the English version of the email will be sent. Currently the following languages are available for gTLD transfers:<br>en_US: English<br>de_DE: German and English<br>sv_SE: Swedish and English<br><br> The default value comes from the environment key "\_system/gtld/transfer/emaillanguage". | TEXT
EMAILURL | 0 | For some registries/TLDs an email is sent during the domain transfer process. This email can include a confirmation link allowing the recipient to confirm the domain transfer. The URL for this link can be specified by this parameter. You can use the following place holders which will be replaced accordingly:<br>{ACTION}: transfer operation<br>{DOMAIN}: domain that is supposed to get transferred<br>{TRIGGER}: trigger code through which the email recipient is validated<br>{LANGUAGE}: the language of the confirmation page (Same value as EMAILLANGUAGE)<br><br>The default value comes from the environment key "\_system/gtld/transfer/url"<br><br>If this parameter is not specified and the respective environment key does not exists for the user account the following URL will be taken which leads to our whitelabel confirmation page:<br> http<nolink>://icann-transfers.info/?domain={DOMAIN}&action={ACTION}&trigger={TRIGGER}&form_language={LANGUAGE} | TEXT
EMAILTAC | 0 | For some registries/TLDs an email is sent during the domain transfer process. This email can contain a link to the Terms and Conditions of the new registrar/reseller. The link to those Terms and Conditions can be specified with this parameter. <br><br>The default value comes from the environment key "\_system/gtld/transfer/tac" | TEXT
EMAILSENDER | 0 | For some registries/TLDs an email is sent during the domain transfer process. Since an email with a foreign sender address is much more likely to be considered spam, only the reply-to address of the email may be specified using this parameter. <br><br>The default value comes from the environment key "\_system/gtld/transfer/emailsender" | TEXT or NULL
EMAILSUBJECT | 0 | For some registries/TLDs an email is sent during the domain transfer process. The subject of this email can be specified by this parameter. It may contain the following place holders which will be replaced accordingly:<br>{ACTION}: transfer operation<br>{DOMAIN}: domain that is supposed to get transferred<br>{TRIGGER}: trigger code through which the email recipient is validated<br><br>The default value comes from the environment key "\_system/gtld/transfer/emailsubject" | TEXT or NULL
EMAILTO | 0 | For some registries/TLDs an email is sent during the domain transfer process. <br>When this parameter is used, the system checks if the provided email address matches one of those email addresses to which the email will be sent. If it does not, the command will fail.| EMAIL or NULL
REQUESTENTITY | 0 | Organization requesting the transfer. <br>The default value comes from the environment key  "user-info/contact/company/organization". | TEXT
NAMESERVER[0..N] | 0 | Nameservers assigned to the domain after the transfer is finished | TEXT or NULL
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
SUBUSER | 0 | The account in which the domain will be located after the transfer is finished | TEXT or NULL
PERIOD | 0 | Period the domain will be renewed during the transfer process. If not stated a default period will be queried. | PERIOD
OWNERCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
ADMINCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
TECHCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
BILLINGCONTACT0 | 0 | Contact Handle ID | CONTACT or NULL
TRANSFERLOCK | 0 | If set to 1, a transfer lock will be set for the domain upon successful transfer. If set to 0, the domain will remain unlocked after the transfer. By default this value is set to 1 for all TLDs. | `0`, `1` or NULL
INTERNALDNS | 0 | Creates the necessary dns zone before submitting application to the registry. | `0`, `1` or NULL
REPOSITORY | 0 | Repository in which the domain will be located after the transfer is finished | NULL or TEXT
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
X-FI-IDNUMBER | 0 | Registrant's personal or organizational identification number; only relevant for .FI domains | TEXT or NULL
X-FI-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-FI-DOMAIN-NAME-HOLDER-COMPANY-TYPE | 0 | Type of company applying for an .FI domain; possible values:<br>`0`: Private person<br>`1`: Company (default)<br>`2`: Association<br>`3`: Foundation<br>`4`: Municipality<br>`5`: Political party<br>`6`: State<br>`7`: Public corporation | INT or NULL
X-FI-BASED-ON-PERSON-NAME | 0 | Set to `1` in order to indicate that the domain name is based on the personal or company name of the registrant; only relevant for .FI domains | TEXT or NULL
X-FI-PERSON-NAME-REGISTRATION-ID | 0 | The register where the company name on which the domain name is based has been registered; only relevant for .FI domains | INT or NULL
X-FI-PERSON-NAME-REGISTRATION-NUMBER | 0 | The registration number of the registered company name on which the domain name is based; only relevant for .FI domains | TEXT or NULL
X-FR-ACCEPT-TRANSFER-TAC | 0 | Set to `1` to accept the .FR transfer terms and conditions | `0`, `1` or NULL
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
X-MY-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | Document submitted as a proof of the registrant's identity  | LONGTEXT
X-PT-ROID | 0 | The ROID of the domain | TEXT or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SG-RCBID | 0 | The company registration number has to be provided with this parameter if the registrant is a organization from Singapore | TEXT or NULL
X-SK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TO-CUSTOMER-HANDLE | 0 | Customer handle; only relevant for .TO domains | TEXT or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL
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

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 |Service temporarily locked; usage exceeded
500	| Invalid command name
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
506	| Invalid option value
507	| Invalid command format
521	| Too many sessions open. Server closing connection
530 | Authentication failed
531	| Authorization failed
532	| Domain names linked with name server
534	| Object has not been flagged for transfer
536	| Object already flagged for transfer
540	| Attribute value is not unique
541	| Invalid attribute value
545	| Object not found
546	| Credit limit exceeded
547	| Invalid command sequence
548	| Object is not up for renewal
549 | Command Failed
552	| Object status does not allow for operation

No properties are returned.

NOTE: The response might include the parameter 'PENDING = 1'. It indicates that the transfer has been requested and that an event will be provided at a later point in time to notify about the outcome of the operation.

----
## Example

### Command

```
[COMMAND]
COMMAND = TransferDomain
AUTH = Ro1Mt/z1Ge1F
DOMAIN = hexonet-transfer.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; domain transfer initiated
PENDING = 1
EOF
```

----
## NOTES

* Your account must have the relation PRICE_CLASS_DOMAIN_DOMAINCLASS_TRANSFER for the corresponding domain class if you want to request a domain transfer.
