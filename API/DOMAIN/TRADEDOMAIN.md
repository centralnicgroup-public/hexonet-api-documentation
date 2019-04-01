# TradeDomain

## DESCRIPTION
Change the registrant of a domain name. For certain TLDs, the registrant cannot be changed via the ModifyDomain command, but only explicitly using this TradeDomain command.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `TradeDomain` | COMMAND
DOMAIN | 1 | Domain Name | TEXT
OWNERCONTACT0 | 0 | Contact Handle of the new domain owner.<br>This parameter is required if a trade is requested (ACTION=request), if a pending trade is canceled (ACTION=cancel) this parameter is not mandatory. | CONTACT
ORDER | 0 | Trade order action:<br>`CREATE` - create a trade order<br>`REPLACE` - replace a trade order<br>`UPDATE` - update a trade order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | Trade order ID. Will only be considered if the parameter ORDER is set to REPLACE or UPDATE. If the parameter is not stated and the parameter ORDER is set to REPLACE or UPDATE then an auto detection of the order ID will be done. | INT
ADMINCONTACT0 | 0 | Contact Handle of the new domain admin | CONTACT
TECHCONTACT0 | 0 | Contact Handle of the new technical contact | CONTACT
BILLINGCONTACT0 | 0 | Contact Handle of the new billing contact | CONTACT
NAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME or NULL
AUTH | 0 | The domain's authorization code | TEXT
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
ACTION | 0 | Defines the action to perform. Supported values are:<br>`request`: Request a new ownership change (parameter OWNERCONTACT mandatory)<br>`cancel`: Cancel a pending Trade (parameter OWNERCONTACT **not** mandatory)<br><br>The default value is `request` | TEXT or NULL
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
X-AU-REGISTRANT-ID-NUMBER | 0 | The respective ID number depending on the registrant ID type | TEXT or NULL
X-AU-REGISTRANT-ID-TYPE | 0 | The ID Type can be one of the following:<br>`ABN`: Australian Business Number<br>`ACN`:  Australian Company Number<br>`RBN`: Business Registration Number<br>`TM`:  Trademark Number | TEXT or NULL
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CORE-INTENDED-USE | 0 | Parameter describing the intended use for the domain name | TEXT or NULL
X-ES-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Set `1` to accept the terms and condition of a individual registration, mandatory if the registrant is an individual | `0`, `1` or NULL
X-ES-REGISTRANT-FORM-JURIDICA | 0 | Registrant's legal form | `1`, `39`, `47`, `59`, `68`, `124`, `150`, `152`, `164`, `181`, `197`, `203`, `229`, `269`, `286`, `365`, `434`, `436`, `439`, `476`, `510`, `524`, `525`, `554`, `560`, `562`, `566`, `608`, `612`, `713`, `717`, `744`, `745`, `746`, `747`, `877`, `878` or `879`
X-ES-REGISTRANT-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-REGISTRANT-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number   | TEXT or NULL
X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-ADMIN-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number   | TEXT or NULL
X-ES-TECH-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-TECH-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number   | TEXT or NULL
X-ES-BILLING-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-BILLING-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number   | TEXT or NULL
X-EU-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Trustee Contact Service for the Owner-C, if you can't provide a local presence in the EU | `0`, `1` or NULL
X-FI-IDNUMBER | 0 | Registrant's personal or organizational identification number; only relevant for .FI domains | TEXT or NULL
X-FI-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-FI-DOMAIN-NAME-HOLDER-COMPANY-TYPE | 0 | Type of company applying for an .FI domain; possible values:<br>`0`: Private person<br>`1`: Company (default)<br>`2`: Association<br>`3`: Foundation<br>`4`: Municipality<br>`5`: Political party<br>`6`: State<br>`7`: Public corporation | INT or NULL
X-FI-BASED-ON-PERSON-NAME | 0 | Set to `1` in order to indicate that the domain name is based on the personal or company name of the registrant; only relevant for .FI domains | TEXT or NULL
X-FI-PERSON-NAME-REGISTRATION-ID | 0 | The register where the company name on which the domain name is based has been registered; only relevant for .FI domains | INT or NULL
X-FI-PERSON-NAME-REGISTRATION-NUMBER | 0 | The registration number of the registered company name on which the domain name is based; only relevant for .FI domains | TEXT or NULL
X-FI-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date; only relevant for .FI domains<br>Mandatory for non-finish private persons | TEXT or NULL
X-FI-REGISTRANT-IDNUMBER | 0 | The registrant's ID number; only relevant for .FI domains | TEXT or NULL
X-FR-ACCEPT-TRANSFER-TAC | 0 | Set to `1` to accept the .FR TRANSFER terms and conditions | `0`, `1` or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service  | `0`, `1` or NULL
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
X-HK-REGISTRANT-CHINESE-COMPANY | 0 | Company name in Chinese | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-TYPE | 0 | Must be one of the following for individuals:<br>`HKID`: Hong Kong Identity Number<br>`OTHID`: Other's Country Identity Number<br>`PASSNO`: Passport No.<br>`BIRTHCERT`: Birth Certificate<br>`OTHIDV`: Others Individual Document<br>Must be one of the following for organizations:<br>`BR`: Business Registration Certificate<br>`CI`: Certificate of Incorporation<br>`CRES`: Certificate of Registration of a School<br>`HKSARG`: Hong Kong Special Administrative Region Government Department <br>`HKORDINANCE`: Ordinance of Hong Kong<br>`OTHORG`: Others Organization Document  | TEXT or NULL
X-HK-REGISTRANT-OTHER-DOCUMENT-TYPE | 0 | Type of document if other document was chosen | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-NUMBER | 0 | The respective document number | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-ORIGIN-COUNTRY | 0 | ISO-3166 Country Code | COUNTRY or NULL
X-HK-REGISTRANT-BIRTH-DATE | 0 | Registrant's birth date, mandatory if the registrant is an individual | TEXT or NULL
X-HK-REGISTRANT-INDUSTRY-TYPE | 0 | Registrant's industry type; default is: `0` (not specified) | TEXT or NULL
X-HK-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Set `1` to accept the terms and condition of a individual registration, mandatory if the registrant is an individual | `0`, `1` or NULL
X-IE-REGISTRANT-CLASS | 0 | The class of the registrant, following values are possible:<br>`Body Corporate (Ltd,PLC,Company)`<br>`Constitutional Body `<br>`Discretionary Applicant `<br>`Natural Person `<br>`School/Educational Institution `<br>`Sole Trader `<br>`Statutory Body `<br>`Unincorporated Association` | TEXT
X-IE-REGISTRANT-CATEGORY | 0 | Based on the registrant class the registrant category has to state one of the following details:<br>`Body Corporate (Ltd,PLC,Company)`: Corporate Name, Discretionary Name, Publication Name, Registered Business Name, Registered Trade Mark Name<br>`Constitutional Body`: Discretionary Name, Publication Name, Registered Trade Mark Name, State Agency Name<br>`Discretionary Applicant`: Discretionary Name<br>`Natural Person`: Discretionary Name, Personal Name, Politician's Name, Registered Trade Mark Name<br>`School/Educational Institution`: Discretionary Name, Publication Name, Registered Trade Mark Name, School/Educational Institution Name<br>`Sole Trader`: Discretionary Name, Personal Trading Name, Publication Name, Registered Business Name, Registered Trade Mark Name<br>`Statutory Body`: Discretionary Name, Publication Name, Registered Trade Mark Name, State Agency Name<br>`Unincorporated Association`: Discretionary Name, Publication Name, Registered Business Name, Registered Trade Mark Name, Unincorporated Association Name  | TEXT
X-IE-REGISTRANT-REMARKS | 0 | Trade mark number or VAT-ID | TEXT
X-IT-PIN | 0 |  If the registrant is an individual, the PIN has to be: <br> The registrant's fiscal code or  the number of an identity document<br>If  the registrant is an organization, the PIN has to be:<br> The company's fiscal code or the company's VAT number  | TEXT or NULL
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
X-MK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MY-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | Document submitted as a proof of the registrant's identity | LONGTEXT
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-NL-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Domicile Contact Service for the Owner-C, if you can't provide a domicile address in the Netherlands | `0`, `1` or NULL
X-NO-REGISTRANT-IDENTITY | 0 | The organization number of the Norwegian organization (consisting of exactly 9 digits) or the PID Number in format N.PRI.12345678 | TEXT
X-NO-DECLARATION-VERSION | 0 | Version of the declaration form on which the domain name policy is accepted | TEXT or NULL
X-NO-CONSENTING-PERSON-NAME | 0 | Name of the person accepting the domain name policy | TEXT or NULL
X-NO-DECLARATION-TIMESTAMP | 0 | Date and time when the domain name policy has been accepted | TEXT or NULL
X-PT-REGISTRANT-VATID | 0 | The registrant's VAT-ID | TEXT or NULL
X-PT-REGISTRANT-MOBILE | 0 | Registrant's mobile number | PHONE or NULL
X-RO-PERSONTYPE | 0 | Registrant entity type; can be `c` (company) or `p` (person) | TEXT or NULL
X-RU-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Set `1` to accept the terms and condition of a individual registration, mandatory if the registrant is an individual  | `0`, `1` or NULL
X-RU-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-DATA | 0 | Registrant's passport data including passport number, issue date, and place of issue | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-NUMBER | 0 | Registrant's passport number | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-DATE | 0 | Registrant's passport issue date | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-LOCATION | 0 | Registrant's passport place of issue | TEXT or NULL
X-RU-REGISTRANT-KPP | 0 | Registrant's KPP number | TEXT or NULL
X-RU-REGISTRANT-TIN | 0 | Registrant's TIN number | TEXT or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SG-RCBID | 0 | The company registration number has to be provided with this parameter if the registrant is a organization from Singapore | TEXT or NULL
X-SWISS-REGISTRANT-ENTERPRISE-ID | 0 |  The enterprise ID, in the specific context of .swiss based on current rules, is the Swiss UID/IDE/IDI. | TEXT
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | TEXT or NULL
X-US-NEXUS-CATEGORY | 0 |Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | TEXT or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | TEXT or NULL
X-TRAVEL-UIN | 0 | The "Unique Identification Number" which entitles the owner to be a registrant of a .TRAVEL domain | TEXT or NULL
X-BAYERN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BERLIN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-HAMBURG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RUHR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
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
X-REGISTRANT-BIRTHDATE | 0 | The registrant's birthdate | TEXT or NULL
X-ADMIN-BIRTHDATE | 0 | The admin's birthdate | TEXT or NULL
X-TECH-BIRTHDATE | 0 | The technical contact's birthdate | TEXT or NULL
X-BILLING-BIRTHDATE | 0 | The billing contact's birthdate | TEXT or NULL
X-REGISTRANT-BIRTHPLACE | 0 | The registrant's birthdate | TEXT or NULL
X-ADMIN-BIRTHPLACE | 0 | The admin's birthplace | TEXT or NULL
X-TECH-BIRTHPLACE | 0 | The technical contact's birthplace | TEXT or NULL
X-BILLING-BIRTHPLACE | 0 | The billing contact's birthplace  | TEXT or NULL
X-VATID | 0 | Domain contacts' VAT-ID | TEXT or NULL
X-REGISTRANT-VATID | 0 | The registrant's VAT-ID | TEXT or NULL
X-ADMIN-VATID | 0 | The admin's VAT-ID | TEXT or NULL
X-TECH-VATID | 0 | The technical contact's VAT-ID | TEXT or NULL
X-BILLING-VATID | 0 | The billing contact's VAT-ID | TEXT or NULL
X-IDNUMBER | 0 | Domain contacts' personal or organizational identification number | TEXT or NULL
X-REGISTRANT-IDNUMBER | 0 | The registrant's ID number | TEXT or NULL
X-ADMIN-IDNUMBER | 0 | The admin's ID number | TEXT or NULL
X-TECH-IDNUMBER | 0 | The technical contact's ID number | TEXT or NULL
X-BILLING-IDNUMBER | 0 | The billing contact's ID number | TEXT or NULL
X-IDAUTHORITY | 0 | Authority that has issued the domain contacts' personal or organizational identification number | TEXT or NULL
X-REGISTRANT-IDAUTHORITY | 0 | Authority that has issued the registrant's ID number | TEXT or NULL
X-ADMIN-IDAUTHORITY | 0 | Authority that has issued the admin's ID number | TEXT or NULL
X-TECH-IDAUTHORITY | 0 | Authority that has issued the technical contact's ID number | TEXT or NULL
X-BILLING-IDAUTHORITY | 0 | Authority that has issued the billing contact's ID number | TEXT or NULL
X-IPR-NAME | 0 | Trademark name | TEXT or NULL
X-IPR-NUMBER | 0 | Trademark number | TEXT or NULL
X-IPR-CCLOCALITY | 0 | Trademark country | TEXT or NULL
X-IPR-REGDATE | 0 | Trademark registration date | TEXT or NULL
X-IPR-APPDATE | 0 | Trademark application date | TEXT or NULL
SUBUSER | 0 | The account in which the domain trade should be executed | TEXT or NULL

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
504 | Missing required attribute
505 | Invalid attribute value syntax
506 | Invalid option value
507 | Invalid command format
530 | Authentication failed
531 | Authorization failed
536 | Object already flagged for transfer
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
546 | Credit limit exceeded
549 | Command failed
552 | Object status does not allow for operation

NOTE: The response might include the parameter 'PENDING = 1'. This indicates that the trade has not been completed yet and that the request might still get rejected.

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = TradeDomain
DOMAIN = hexonet-trade.ch
OWNERCONTACT0 = P-TUE1378125
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully; realtime domain trade succeeded
EOF
```

----
