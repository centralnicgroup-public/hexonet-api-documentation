# CheckDomainTrade

## DESCRIPTION
Check if a domain trade requested by a respective TradeDomain command would work.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckDomainTrade` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
AUTH | 0 | Auhorization code | TEXT
MODE | 0 | If set to `PRECHECK` certain trade policy checks are skipped | `PRECHECK`, `FULL` or NULL
OWNERCONTACT0 | 0 | Contact Handle ID | CONTACT
ADMINCONTACT0 | 0 | Contact Handle ID | CONTACT
TECHCONTACT0 | 0 | Contact Handle ID | CONTACT
NAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME or NULL
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
X-CAT-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CONFIRM-DA-NEW-REGISTRANT | 0 | IRTP parameter: By setting this to `1` you confirm that you are the current registrant or the respective Designated Agent (DA) and that you authorize the change of the registrant | `0`, `1` or NULL
X-CONFIRM-DA-OLD-REGISTRANT | 0 | IRTP parameter: By setting this to `1` you confirm that you are the new registrant or the respective Designated Agent (DA) and that you authorize the change of the registrant  | `0`, `1` or NULL
X-HEALTH-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1`
X-REQUEST-OPT-OUT-TRANSFERLOCK | 0 | IRTP parameter: By setting this to `1` you can disable the 60 day transfer lock upon a successful registrant change | `0`, `1` or NULL
X-AE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .AE domains | `0`, `1` or NULL
X-AE-REGISTRANT-NAME | 0 | Registrant's name; only relevant for .AE domains | TEXT or NULL
X-AE-REGISTRANT-ID-TYPE | 0 | Registrant's ID type; only relevant for .AE domains | TEXT or NULL
X-AE-REGISTRANT-ID-NUMBER | 0 | Registrant's ID number; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-TYPE | 0 | Registration eligibility type; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-NAME | 0 | Registration eligibility name; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-ID-TYPE | 0 | Registration eligibility ID type; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-ID-NUMBER | 0 | Registration eligibility ID number; only relevant for .AE domains | TEXT or NULL
X-AE-POLICY-REASON | 0 | Registration reason; only relevant for .AE domains | TEXT or NULL
X-AU-REGISTRANT-ID-NUMBER | 0 | The respective ID number used as a eligibility proof for a .AU domain. The type of the number has to be specified with the X-AU-REGISTRANT-ID-TYPE parameter | TEXT or NULL
X-AU-REGISTRANT-ID-TYPE | 0 | The respective type of the ID number used as the eligibility proof for a .AU domain. <br> Can be `ABN` (Australian Business Number), `ACN` (Australian Company Number) or `TM` (Trademark Number)| `ABN`, `ACN` or `TM`
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CORE-INTENDED-USE | 0 | Parameter describing the intended use for the domain name | TEXT or NULL
X-DISCLOSE | 0 | Set to `1` to disclose the domain's details | `0`, `1` or NULL
X-ES-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Set `1` to accept the terms and condition of a individual registration, mandatory if the registrant is an individual | `0`, `1` or NULL
X-ES-REGISTRANT-FORM-JURIDICA | 0 | Registrant's legal form | `1`, `39`, `47`, `59`, `68`, `124`, `150`, `152`, `164`, `181`, `197`, `203`, `229`, `269`, `286`, `365`, `434`, `436`, `439`, `476`, `510`, `524`, `525`, `554`, `560`, `562`, `566`, `608`, `612`, `713`, `717`, `744`, `745`, `746`, `747`, `877`, `878` or `879`
X-ES-REGISTRANT-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-REGISTRANT-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-ADMIN-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-TECH-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-TECH-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-BILLING-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-BILLING-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-EU-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Trustee Contact Service for the Owner-C, if you can't provide a local presence in the EU | `0`, `1` or NULL
X-FI-IDNUMBER | 0 | Registrant's personal or organizational identification number; only relevant for .FI domains | TEXT or NULL
X-FI-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date; only relevant for .FI domains<br>Mandatory for non-finish private persons | TEXT or NULL
X-FI-REGISTRANT-IDNUMBER | 0 | The registrant's ID number; only relevant for .FI domains | TEXT or NULL
X-FR-ACCEPT-TRANSFER-TAC | 0 | Set to `1` to accept the .FR TRANSFER terms and conditions | `0`, `1` or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-PM-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-WF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-YT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-REGISTRANT-BIRTH-DATE | 0 | The registrant's date of birth in the form YYYY-MM-DD | TEXT or NULL
X-FR-REGISTRANT-BIRTH-PLACE | 0 | The registrant's place of birth | TEXT or NULL
X-FR-REGISTRANT-DISCLOSE | 0 | Setting this parameter to `1` discloses the registrant's details | TEXT or NULL
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | Companies with a European trademark can additionally add their trademark number using this parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM | 0 | Legal form of the entity (in case registrant is not a natural person) | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | Other form than the possible values of the above parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-ID | 0 | Companies having their head office in the territory of the European Union must provide their VAT-ID with this parameter | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | The date of declaration of the association | TEXT or NULL
X-FR-REGISTRANT-JO-NUMBER | 0 | The number of the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-JO-PAGE | 0 | The page of the announcement in the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | The date of publication in the Journal Officiel | TEXT or NULL
X-FR-REGISTRANT-DUNS-NUMBER | 0 | The DUNS number is a nine-digit number, issued by Dun & Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this parameter | TEXT or NULL
X-FR-REGISTRANT-LOCAL-ID | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-IT-PIN | 0 | If the registrant is an individual, the PIN has to be: <br> The registrant's fiscal code or  the number of an identity document<br>If  the registrant is an organization, the PIN has to be:<br> The company's fiscal code or the company's VAT number | TEXT or NULL
X-IT-REGISTRANT-ENTITY-TYPE | 0 | In some special cases you need to specify the exact entity type of the registrant:<br>`1`: Italian and foreign natural persons<br>`2`: Italian Companies / one man companies<br>`3`:  freelance workers / professionals <br>`4`: non-profit organizations<br>`5`: public organizations<br>`6`:  	other subjects<br>`7`: foreigners who match 2 - 6 | TEXT or NULL
X-IT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-IT-ACCEPT-LIABILITY-TAC | 0 | Accepts "Section 3 - Declarations and assumptions of liability" | `0`, `1` or NULL
X-IT-ACCEPT-REGISTRATION-TAC | 0 | Accepts "Section 5 - Consent to the processing of personal data for registration" | `0`, `1` or NULL
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | Accepts - "Section 6 - Consent to the processing of personal data for diffusion and accessibility via the internet" | `0`, `1` or NULL
X-IT-ACCEPT-EXPLICIT-TAC | 0 | Accepts "Section 7 - Explicit acceptance of the following points" | `0`, `1` or NULL
X-JOBS-TITLE | 0 | Registrant's title; only relevant for .JOBS domains | TEXT or NULL
X-JOBS-COMPANYURL | 0 | Company URL for .JOBS | TEXT or NULL
X-JOBS-INDUSTRYCLASSIFICATION | 0 | Industry Classification for .JOBS | TEXT or NULL
X-JOBS-HRANAME | 0 | Human Resources Association name for .JOBS | TEXT or NULL
X-JOBS-ADMINTYPE | 0 | Set to `1` in order to indicate that the registrant is also the administrative contact of the domain; only relevant for .JOBS domains | `0` or `1`
X-LT-REGISTRANT-LEGAL-ID | 0 | Legal entity identification code of the registrant of a .LT domain. Required as of December 1, 2018 if the registrant is a legal entity. | TEXT or NULL
X-MY-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | Document submitted as a proof of the registrant's identity | LONGTEXT
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-NL-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Domicile Contact Service for the Owner-C, if you can't provide a domicile address in the Netherlands | `0`, `1` or NULL
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SG-RCBID | 0 | The company registration number has to be provided with this parameter if the registrant is a organization from Singapore | TEXT or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL
X-ATTORNEY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-LAWYER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-DENTIST-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `0`, `1` or NULL
X-MARKETS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-TRADING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-SPREADBETTING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CFD-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-BROKER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-FOREX-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-LAW-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ABOGADO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-MAKEUP-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-BIBLE-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ECO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-HOMES-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-VOTE-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-VOTO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-REGISTRANT-IDNUMBER | 0 | The registrant's ID number | TEXT or NULL
X-ADMIN-IDNUMBER | 0 | The admin's ID number | TEXT or NULL
X-VATID | 0 | Domain contacts' VAT-ID | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
218 | Request is available
219 | Request is not available
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACTION | 0 | 1 | Always `check` | TEXT
ADMINCONTACT[0..N] | 0 | N | Contact Handle of the new domain admin | TEXT
AUTH | 0 | 1 | The domain's authorization code | TEXT
BILLINGCONTACT[0..N] | 0 | N | Contact Handle of the new billing contact | TEXT
CREATEDBY | 0 | 1 | Registrar that registered the domain | TEXT
CREATEDDATE | 0 | 1 | The creation date of the domain | DATETIME
EXPIRATIONDATE | 0 | 1 | Registration expiration date of the domain | DATETIME
HOST[0..N] | 0 | N | Nameserver hostnames and IP addresses | TEXT
MODE | 0 | 1 | The mode as chosen in the command | TEXT
NAMESERVER[0..N] | 0 | N | Nameserver hostnames | TEXT
OLD-ADMINCONTACT[0..N] | 0 | N | Contact Handle of the old domain admin | TEXT
OLD-ADMINCONTACTDETAILS | 0 | 1 | The old domain admin's basic contact data | TEXT
OLD-AUTH | 0 | 1 | The domain's old authorization code | TEXT
OLD-BILLINGCONTACT[0..N] | 0 | N | Contact Handle of the old billing contact | TEXT
OLD-CREATEDBY | 0 | 1 | Registrar that registered the domain | TEXT
OLD-CREATEDDATE | 0 | 1 | The creation date of the domain | DATETIME
OLD-EXPIRATIONDATE | 0 | 1 | The old registration expiration date of the domain | DATETIME
OLD-NAMESERVER[0..N] | 0 | N | Old nameserver hostnames | TEXT
OLD-OWNERCONTACT[0..N] | 0 | N | Contact Handle of the old domain owner  | TEXT
OLD-REGISTRANTDETAILS | 0 | 1 | The old domain owner's basic contact data | TEXT
OLD-REGISTRAR | 0 | 1 | Old sponsoring registrar | TEXT
OLD-REGISTRATIONEXPIRATIONDATE | 0 | 1 | The old registration expiration date of the domain | DATETIME
OLD-STATUS[0..N] | 0 | N | Old domain status | TEXT
OLD-TECHCONTACT[0..N] | 0 | N | Contact Handle of the old technical contact | TEXT
OLD-TECHCONTACTDETAILS | 0 | 1 | The old technical contact's basic contact data | TEXT
OLD-TRANSFERDATE | 0 | 1 | Old transfer date | DATETIME
OLD-UPDATEDBY | 0 | 1 | Old registrar that updated the domain | TEXT
OLD-UPDATEDDATE | 0 | 1 | Old date of last modification | DATETIME
OLD-X-ABOGADO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-ADMIN-BIRTHDATE | 0 | 1 | Old admin's birthdate | TEXT or NULL
OLD-X-ADMIN-BIRTHPLACE | 0 | 1 | Old admin's birthplace | TEXT or NULL
OLD-X-ADMIN-IDAUTHORITY | 0 | 1 | Authority that has issued the old admin's ID number | TEXT or NULL
OLD-X-ADMIN-IDNUMBER | 0 | 1 | Old admin's ID number | TEXT or NULL
OLD-X-ADMIN-VATID | 0 | 1 | Old admin's VAT-ID | TEXT or NULL
OLD-X-AE-ACCEPT-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-AE-ELIGIBILITY-ID-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-ELIGIBILITY-ID-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-ELIGIBILITY-NAME | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-ELIGIBILITY-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-POLICY-REASON | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-REGISTRANT-ID-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-REGISTRANT-ID-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AE-REGISTRANT-NAME | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-ATTORNEY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-AU-REGISTRANT-ID-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-AU-REGISTRANT-ID-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-BILLING-BIRTHDATE | 0 | 1 | Old billing contact's birthdate | TEXT or NULL
OLD-X-BILLING-BIRTHPLACE | 0 | 1 | Old billing contact's birthplace  | TEXT or NULL
OLD-X-BILLING-IDAUTHORITY | 0 | 1 | Authority that has issued the old billing contact's ID number | TEXT or NULL
OLD-X-BILLING-IDNUMBER | 0 | 1 | Old billing contact's ID number | TEXT or NULL
OLD-X-BILLING-VATID | 0 | 1 | Old billing contact's VAT-ID | TEXT or NULL
OLD-X-BROKER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-CA-CHANGEWITHOUTAPPROVAL | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-CA-LANGUAGE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-CA-LEGALTYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-CFD-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-DENTIST-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-ERRP-EMAIL | 0 | 1 | Old email address of the RSP appearing in the ERRP email | EMAIL or NULL
OLD-X-ERRP-PHONE | 0 | 1 | Old phone number of the RSP appearing in the ERRP email | PHONE or NULL
OLD-X-ERRP-RSP | 0 | 1 | Old name of the RSP appearing in the ERRP email | TEXT or NULL
OLD-X-ERRP-SIGNATURE[0..3] | 0 | 4 | Old signature appearing at the end of the ERRP email | TEXT or NULL
OLD-X-ERRP-TAC-URL | 0 | 1 | Old Terms and Conditions URL of the RSP appearing in the ERRP email | TEXT or NULL
OLD-X-ERRP-URL | 0 | 1 | Old URL of the RSP appearing in the ERRP email | TEXT or NULL
OLD-X-ES-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-ES-ADMIN-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-BILLING-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-BILLING-TIPO-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-REGISTRANT-FORM-JURIDICA | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-REGISTRANT-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-REGISTRANT-TIPO-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-TECH-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-ES-TECH-TIPO-IDENTIFICACION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-EU-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-FI-ACCEPT-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-FI-BASED-ON-PERSON-NAME | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FI-DOMAIN-NAME-HOLDER-COMPANY-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FI-IDNUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FI-PERSON-NAME-REGISTRATION-ID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FI-PERSON-NAME-REGISTRATION-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FOREX-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-FR-ACCEPT-TRANSFER-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-FR-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-FR-REGISTRANT-BIRTH-DATE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-BIRTH-PLACE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-DISCLOSE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-DUNS-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-JO-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-JO-PAGE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-KEY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-LEGAL-FORM | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-LEGAL-ID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-LOCAL-ID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-HK-REGISTRANT-BIRTH-DATE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-CHINESE-COMPANY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-DOCUMENT-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-DOCUMENT-ORIGIN-COUNTRY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-DOCUMENT-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-INDUSTRY-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-HK-REGISTRANT-OTHER-DOCUMENT-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-IDAUTHORITY | 0 | 1 | Authority that has issued the old domain contacts' personal or organizational identification number | TEXT or NULL
OLD-X-IDNUMBER | 0 | 1 | Old domain contacts' personal or organizational identification number | TEXT or NULL
OLD-X-IPR-APPDATE | 0 | 1 | Old trademark application date | TEXT or NULL
OLD-X-IPR-CCLOCALITY | 0 | 1 | Old trademark country | TEXT or NULL
OLD-X-IPR-NAME | 0 | 1 | Old trademark name | TEXT or NULL
OLD-X-IPR-NUMBER | 0 | 1 | Old trademark number | TEXT or NULL
OLD-X-IPR-REGDATE | 0 | 1 | Old trademark registration date | TEXT or NULL
OLD-X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-IT-ACCEPT-EXPLICIT-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-IT-ACCEPT-LIABILITY-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-IT-ACCEPT-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-IT-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-IT-PIN | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-IT-REGISTRANT-ENTITY-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-LAW-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-LAWYER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-MARKETS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-MELBOURNE-NEXUS-CATEGORY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-MK-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-MY-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-MY-REGISTRANT-RACE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NGO-ACCEPT-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-NICSE-IDNUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NICSE-VATID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NL-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-NO-CONSENTING-PERSON-NAME | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NO-DECLARATION-TIMESTAMP | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NO-DECLARATION-VERSION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-NO-REGISTRANT-IDENTITY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-PM-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-PT-REGISTRANT-VATID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RE-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-REGISTRANT-BIRTHDATE | 0 | 1 | Old registrant's birthdate | TEXT or NULL
OLD-X-REGISTRANT-BIRTHPLACE | 0 | 1 | Old registrant's birthdate | TEXT or NULL
OLD-X-REGISTRANT-DOMICILE-ADDRESS-HOUSENO | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-DOMICILE-ADDRESS-HSNO-SUFX | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-DOMICILE-ADDRESS-POSTCODE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-DOMICILE-ADDRESS-STREET | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-DOMICILE-ADDRESS-TOWN | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-IDAUTHORITY | 0 | 1 | Authority that has issued the old registrant's ID number | TEXT or NULL
OLD-X-REGISTRANT-IDNUMBER | 0 | 1 | Old registrant's ID number | TEXT or NULL
OLD-X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-BODY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-ID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-YEAR | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-CC | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-STATE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-REGISTRANT-VATID | 0 | 1 | Old registrant's VAT-ID | TEXT or NULL
OLD-X-REGULATORY-BODY-AUTHORIZATION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RO-ACCEPT-LEGAL-USE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RO-ACCEPT-REGISTRATION-RULES | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RO-PERSONTYPE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-RU-REGISTRANT-BIRTH-DATE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-KPP | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-PASSPORT-DATA | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-PASSPORT-DATE | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-PASSPORT-LOCATION | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-PASSPORT-NUMBER | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-RU-REGISTRANT-TIN | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-SG-RCBID | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-SPREADBETTING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-SYDNEY-NEXUS-CATEGORY | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-TECH-BIRTHDATE | 0 | 1 | Old technical contact's birthdate | TEXT or NULL
OLD-X-TECH-BIRTHPLACE | 0 | 1 | Old technical contact's birthplace | TEXT or NULL
OLD-X-TECH-IDAUTHORITY | 0 | 1 | Authority that has issued the old technical contact's ID number | TEXT or NULL
OLD-X-TECH-IDNUMBER | 0 | 1 | Old technical contact's ID number | TEXT or NULL
OLD-X-TECH-VATID | 0 | 1 | Old technical contact's VAT-ID | TEXT or NULL
OLD-X-TF-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-TRADING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-TRAVEL-UIN | 0 | 1 | Old TLD specific domain flag | TEXT
OLD-X-VATID | 0 | 1 | Old domain contacts' VAT-ID | TEXT or NULL
OLD-X-WDRP-MAILFROM | 0 | 1 | Old name of the sender used for the WDRP email | TEXT or NULL
OLD-X-WDRP-RSP | 0 | 1 | Old name of the RSP appearing in the WDRP email | TEXT or NULL
OLD-X-WDRP-SIGNATURE[0..3] | 0 | 4 | Old signature appearing at the end of the WDRP email | TEXT or NULL
OLD-X-WDRP-URL | 0 | 1 | Old URL of the RSP appearing in the WDRP email | TEXT or NULL
OLD-X-WF-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OLD-X-WHOIS-BANNER[0..2] | 0 | 3 | Old text displayed in our whois | TEXT
OLD-X-WHOIS-RSP | 0 | 1 | Old RSP name displayed in our whois | TEXT
OLD-X-WHOIS-URL | 0 | 1 | Old URL displayed in our whois | TEXT
OLD-X-YT-ACCEPT-TRUSTEE-TAC | 0 | 1 | Old TLD specific domain flag | INT
OWNERCONTACT[0..N] | 0 | N | Contact Handle of the new domain owner | TEXT
POLICYAPPROVECONFIRMATION | 0 | 1 | Trade approval confirmation policy | TEXT
REGISTRAR | 0 | 1 | New sponsoring registrar | TEXT
REGISTRATIONEXPIRATIONDATE | 0 | 1 | Registration expiration date of the domain | DATETIME
REPOSITORY | 0 | 1 | Domain repository | TEXT
STATUS[0..N] | 0 | N | New domain status | TEXT
TECHCONTACT[0..N] | 0 | N | Contact Handle of the new technical contact | TEXT
TRADEWITHINREPOSITORY | 0 | 1 | Indicates if the repository of the domain is still the same after the trade | TEXT
UPDATEDBY | 0 | 1 | New registrar that updated the domain | TEXT
UPDATEDDATE | 0 | 1 | New date of last modification | DATETIME
X-ABOGADO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-AE-ACCEPT-REGISTRATION-TAC | 0 | 1 | TLD specific domain flag | INT
X-AE-ELIGIBILITY-ID-NUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-AE-ELIGIBILITY-ID-TYPE | 0 | 1 | TLD specific domain flag | TEXT
X-AE-ELIGIBILITY-NAME | 0 | 1 | TLD specific domain flag | TEXT
X-AE-ELIGIBILITY-TYPE | 0 | 1 | TLD specific domain flag | TEXT
X-AE-POLICY-REASON | 0 | 1 | TLD specific domain flag | TEXT
X-AE-REGISTRANT-ID-NUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-AE-REGISTRANT-ID-TYPE | 0 | 1 | TLD specific domain flag | TEXT
X-AE-REGISTRANT-NAME | 0 | 1 | TLD specific domain flag | TEXT
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-ATTORNEY-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-BROKER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-CA-CHANGEWITHOUTAPPROVAL | 0 | 1 | TLD specific domain flag | TEXT
X-CA-LANGUAGE | 0 | 1 | TLD specific domain flag | TEXT
X-CA-LEGALTYPE | 0 | 1 | TLD specific domain flag | TEXT
X-CFD-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-DENTIST-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-ES-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | 1 | TLD specific domain flag | INT
X-ES-ADMIN-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-BILLING-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-BILLING-TIPO-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-REGISTRANT-FORM-JURIDICA | 0 | 1 | TLD specific domain flag | TEXT
X-ES-REGISTRANT-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-REGISTRANT-TIPO-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-TECH-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-ES-TECH-TIPO-IDENTIFICACION | 0 | 1 | TLD specific domain flag | TEXT
X-EU-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-FOREX-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-FI-IDNUMBER | 0 | 1 | Registrant's personal or organizational identification number | TEXT
X-FI-REGISTRANT-BIRTH-DATE | 0 | 1 | The registrant's birth date | TEXT
X-FI-REGISTRANT-IDNUMBER | 0 | 1 | The registrant's ID number; only relevant for .FI domains | TEXT
X-FR-ACCEPT-TRANSFER-TAC | 0 | 1 | TLD specific domain flag | INT
X-FR-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-FR-REGISTRANT-BIRTH-DATE | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-BIRTH-PLACE | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-DISCLOSE | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-DUNS-NUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-JO-NUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-JO-PAGE | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-KEY | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-LEGAL-FORM | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-LEGAL-ID | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-LOCAL-ID | 0 | 1 | TLD specific domain flag | TEXT
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | 1 | TLD specific domain flag | INT
X-IT-ACCEPT-EXPLICIT-TAC | 0 | 1 | TLD specific domain flag | INT
X-IT-ACCEPT-LIABILITY-TAC | 0 | 1 | TLD specific domain flag | INT
X-IT-ACCEPT-REGISTRATION-TAC | 0 | 1 | TLD specific domain flag | INT
X-IT-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-IT-PIN | 0 | 1 | TLD specific domain flag | TEXT
X-IT-REGISTRANT-ENTITY-TYPE | 0 | 1 | TLD specific domain flag | TEXT
X-LAW-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-LAWYER-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-MARKETS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-FILM-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-MAKEUP-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-MELBOURNE-NEXUS-CATEGORY | 0 | 1 | TLD specific domain flag | TEXT
X-MY-ACCEPT-TRUSTEE-TAC | 0 | 1 | Activates the trustee service | INT
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | 1 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | 1 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | 1 | Document submitted as a proof of the registrant's identity | LONGTEXT
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | 1 | TLD specific domain flag | INT
X-NICSE-IDNUMBER | 0 | 1 | TLD specific domain flag | TEXT
X-NICSE-VATID | 0 | 1 | TLD specific domain flag | TEXT
X-NL-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-PM-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-PT-ROID | 0 | 1 | TLD specific domain flag | TEXT
X-RE-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-BODY | 0 | 1 | TLD specific domain flag | TEXT
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-ID | 0 | 1 | TLD specific domain flag | TEXT
X-REGISTRANT-QUALIFIED-LAWYER-ACCREDITATION-YEAR | 0 | 1 | TLD specific domain flag | TEXT
X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-CC | 0 | 1 | TLD specific domain flag | TEXT
X-REGISTRANT-QUALIFIED-LAWYER-JURISDICTION-STATE | 0 | 1 | TLD specific domain flag | TEXT
X-REGULATORY-BODY-AUTHORIZATION | 0 | 1 | TLD specific domain flag | TEXT
X-SPREADBETTING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-SYDNEY-NEXUS-CATEGORY | 0 | 1 | TLD specific domain flag | TEXT
X-SG-ACCEPT-TRUSTEE-TAC | 0 | 1 | Activates the trustee service | INT
X-SG-RCBID | 0 | 1 | The company registration number for Singapore based .SG registrants | TEXT
X-TF-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-TRADING-ACCEPT-HIGHLY-REGULATED-TAC | 0 | 1 | TLD specific domain flag | INT
X-WF-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT
X-WHOIS-BANNER[0..2] | 0 | 3 | Text displayed in our whois | TEXT
X-WHOIS-RSP | 0 | 1 | RSP name displayed in our whois | TEXT
X-WHOIS-URL | 0 | 1 | URL displayed in our whois | TEXT
X-YT-ACCEPT-TRUSTEE-TAC | 0 | 1 | TLD specific domain flag | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckDomainTrade
DOMAIN = hexonet-trade.li
OWNERCONTACT0 = P-TUE1378125
EOF
```
### Response

```
[RESPONSE]
CODE = 218
DESCRIPTION = Request is available
PROPERTY[ACTION][0] = check
PROPERTY[ADMINCONTACT][0] = P-JDE1318234
PROPERTY[AUTH][0] = tm9Jwo1dH4
PROPERTY[BILLINGCONTACT][0] = P-JDE1318234
PROPERTY[CREATEDBY][0] = hexonet
PROPERTY[CREATEDDATE][0] = 2016-12-14 12:42:17
PROPERTY[EXPIRATIONDATE][0] = 2017-12-30 23:00:00
PROPERTY[MODE][0] = full
PROPERTY[NAMESERVER][0] = ns1.hexonet.net
PROPERTY[NAMESERVER][1] = ns2.hexonet.net
PROPERTY[OLD-ADMINCONTACT][0] = P-JDE1318234
PROPERTY[OLD-ADMINCONTACTDETAILS][0] = Example Inc., John Doe, Dulles, DE
PROPERTY[OLD-AUTH][0] = PAcnHEJOxA
PROPERTY[OLD-BILLINGCONTACT][0] = P-JDE1318234
PROPERTY[OLD-CREATEDBY][0] = hexonet
PROPERTY[OLD-CREATEDDATE][0] = 2016-12-14 12:42:17
PROPERTY[OLD-EXPIRATIONDATE][0] = 2017-12-30 23:00:00
PROPERTY[OLD-NAMESERVER][0] = ns1.hexonet.net
PROPERTY[OLD-NAMESERVER][1] = ns2.hexonet.net
PROPERTY[OLD-OWNERCONTACT][0] = P-JDE1318234
PROPERTY[OLD-REGISTRANTDETAILS][0] = Example Inc., John Doe, Dulles, DE
PROPERTY[OLD-REGISTRAR][0] = hexonet
PROPERTY[OLD-REGISTRATIONEXPIRATIONDATE][0] = 2017-12-30 23:00:00
PROPERTY[OLD-STATUS][0] = ACTIVE
PROPERTY[OLD-TECHCONTACT][0] = P-JDE1318234
PROPERTY[OLD-TECHCONTACTDETAILS][0] = Example Inc., John Doe, Dulles, DE
PROPERTY[OLD-TRANSFERDATE][0] = 0000-00-00 00:00:00
PROPERTY[OLD-UPDATEDBY][0] = hexonet
PROPERTY[OLD-UPDATEDDATE][0] = 2016-12-14 12:42:16
PROPERTY[OLD-X-WDRP-RSP][0] = Test GmbH
PROPERTY[OLD-X-WHOIS-RSP][0] = ABC-123
PROPERTY[OLD-X-WHOIS-URL][0] = http://cp-ote.hexonet.net
PROPERTY[OWNERCONTACT][0] = P-TUE1378125
PROPERTY[POLICYAPPROVECONFIRMATION][0] = REALTIME
PROPERTY[REGISTRAR][0] = hexonet
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-12-30 23:00:00
PROPERTY[REPOSITORY][0] = SWITCH-OTE-1API1
PROPERTY[STATUS][0] = REQUESTED
PROPERTY[TECHCONTACT][0] = P-JDE1318234
PROPERTY[TRADEWITHINREPOSITORY][0] = 1
PROPERTY[UPDATEDBY][0] = hexonet
PROPERTY[UPDATEDDATE][0] = 2016-12-14 12:42:16
PROPERTY[X-WHOIS-RSP][0] = ABC-123
PROPERTY[X-WHOIS-URL][0] = http://cp-ote.hexonet.net
EOF
```

----
