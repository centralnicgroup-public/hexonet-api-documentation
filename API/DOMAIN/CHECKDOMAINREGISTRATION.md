# CheckDomainRegistration

## DESCRIPTION
Check if a domain registration requested by a respective AddDomain command would work.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckDomainRegistration` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
PERIOD | 0 | Registration period:<br>`NY` for N years<br>`NM` for N months<br>(please note that "Y" and "M" are case sensitive) | PERIOD
RENEWALMODE | 0 | The domain's renewal mode | NULL or TEXT
OWNERCONTACT[0..4] | 1 | Owner/Registrant Contact Handle IDs. | CONTACT or NULL
ADMINCONTACT[0..2] | 1 | The Administrative Contact Handle IDs. | CONTACT or NULL
TECHCONTACT[0..2] | 1 | The Technical Contact Handle IDs. | CONTACT or NULL
BILLINGCONTACT[0..2] | 1 | The Billing Contact Handle IDs. | CONTACT or NULL
NAMESERVER[0..12] | 0 | Nameserver hostnames | HOSTNAME or NULL
SECDNS-DS[0..N] | 0 | SECDNS resource records | LONGTEXT or NULL
SECDNS-KEY[0..N] | 0 | SECDNS resource records | LONGTEXT or NULL
SECDNS-MAXSIGLIFE | 0 | Maximum lifespan of the SECDNS signature | INT
AUTH | 0 | Auth-Info code | TEXT or NULL
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
TRANSFERLOCK | 0 | TRANSFERLOCK=`1` locks a domain immediately after creating it | `0`, `1` or NULL
SUBUSER | 0 | The account in which the domain should be created | TEXT or NULL
NAMESERVERSET | 0 | ID of a nameserver set | TEXT or NULL
CLAIMKEY | 0 | If there is a claim on the domain name the claim key has to be provided with this parameter | TEXT or NULL
CLAIMKEY-UPDATEDDATE | 0 | Date when the claim key has been updated the last time | DATETIME or NULL
NOTICE-ACCEPT-ID | 0 | ID of the accepted claims notice; NOTICE-POA-ACCEPT-HASH should be used instead | TEXT or NULL
NOTICE-EXPIRATIONDATE | 0 | Expiration date of the accepted claims notice; NOTICE-POA-ACCEPT-HASH should be used instead | DATETIME or NULL
NOTICE-ACCEPTEDDATE | 0 | Date when the claims notice has been accepted; NOTICE-POA-ACCEPT-HASH should be used instead | DATETIME or NULL
NOTICE-POA-ACCEPT-HASH | 0 | By providing the appropriate hash value, a respective claim notice is accepted | TEXT or NULL
LAUNCH-MARK-CODE | 0 | Special allocation token provided by the registry | TEXT or NULL
X-CAT-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-CHANNEL-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NUL
X-COOP-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULLL
X-DISCLOSE | 0 | Set to `1` to disclose the domain's details | `0`, `1` or NULL
X-HEALTH-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1`
X-REGISTRANT-DISCLOSE | 0 | Set to `1` to disclose the registrant's details | `0`, `1` or NULL
X-ADMIN-DISCLOSE | 0 | Set to `1` to disclose the admins's details | `0`, `1` or NULL
X-TECH-DISCLOSE | 0 | Set to `1` to disclose the technical contact's details | `0`, `1` or NULL
X-BILLING-DISCLOSE | 0 | Set to `1` to disclose the biling contact's details | `0`, `1` or NULL
X-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-ACCEPT-SSL-REQUIREMENT | 0 | Set to `1` to accept the policy and enforcement terms | `0`, `1` or NULL
X-REGISTRANT-BIRTHDATE | 0 | The registrant's birthdate | TEXT or NULL
X-ADMIN-BIRTHDATE | 0 | The admins's birthdate | TEXT or NULL
X-TECH-BIRTHDATE | 0 | The technical contact's birthdate | TEXT or NULL
X-BILLING-BIRTHDATE | 0 | The billing contact's birthdate | TEXT or NULL
X-REGISTRANT-BIRTHPLACE | 0 | The registrant's birthplace | TEXT or NULL
X-ADMIN-BIRTHPLACE | 0 | The admin's birthplace | TEXT or NULL
X-TECH-BIRTHPLACE | 0 | The technical contact's birthplace | TEXT or NULL
X-BILLING-BIRTHPLACE | 0 | The billing contact's birthplace | TEXT or NULL
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
X-ALLOCATIONTOKEN | 0 | Allocation token for the registration of reserved domain names | TEXT
X-ASSOCIATION-ID | 0 | Special contact ID; only relevant for .XXX domains | TEXT or NULL
X-AE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .AE domains | `0`, `1` or NULL
X-AE-REGISTRANT-NAME | 0 | Registrant's name; only relevant for .AE domains | TEXT or NULL
X-AE-REGISTRANT-ID-TYPE | 0 | Registrant's ID type; only relevant for .AE domains | TEXT or NULL
X-AE-REGISTRANT-ID-NUMBER | 0 | Registrant's ID number; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-TYPE | 0 | Registration eligibility type; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-NAME | 0 | Registration eligibility name; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-ID-TYPE | 0 | Registration eligibility ID type; only relevant for .AE domains | TEXT or NULL
X-AE-ELIGIBILITY-ID-NUMBER | 0 | Registration eligibility ID number; only relevant for .AE domains | TEXT or NULL
X-AE-POLICY-REASON | 0 | Registration reason; only relevant for .AE domains | TEXT or NULL
X-AERO-ENS-AUTH-ID | 0 | The ID needed to register a .AERO domain | TEXT or NULL
X-AERO-ENS-AUTH-KEY | 0 | The respective password | TEXT or NULL
X-ASIA-CED-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0` or `1`
X-ASIA-CED-CCLOCALITY | 0 | Location or domicile of the Entity (based on the corresponding ISO3166 code). | TEXT or NULL
X-ASIA-CED-CONTACT | 0 | Indicates which contact should be used as CED. Must be `registrant`, `admin`, `tech` or `billing` | TEXT or NULL
X-ASIA-CED-LOCALITYSP | 0 | Province of establishment of the CED. | TEXT or NULL
X-ASIA-CED-LOCALITYCITY | 0 | City of establishment of the CED. | TEXT or NULL
X-ASIA-CED-LEGALENTITYTYPE | 0 | Must be one of the following: <br>`naturalPerson`<br>`corporation`<br>`cooperative`<br>`partnership`<br>`government`<br>`politicalParty`<br>`society`<br>`institution`<br>`other Type of Entity` | TEXT or NULL
X-ASIA-CED-IDENTFORM | 0 | Must be one of the following: <br>`passport`<br>`certificate`<br>`legislation`<br>`societyRegistry`<br>`politicalPartyRegistry`<br>`other` | TEXT or NULL
X-ASIA-CED-IDENTNUMBER | 0 | Identification Number / Code of Reference (e.g. Passport number, Business Certificate number, Act or Legislation number/code, etc.). | TEXT or NULL
X-ASIA-CED-OTHERLETYPE | 0 | Other legal entity type | TEXT or NULL
X-ASIA-CED-OTHERIDENTFORM | 0 | If the legal entity type or form of identification is "other", please enter the appropriate information to support the claim. | TEXT or NULL
X-ASIA-MAINTAINERURL | 0 | In order to register a .ASIA domain, this parameter can be used to display information about the maintainer, e.g. the provider of the domain, in the .ASIA whois | TEXT or NULL
X-ASIA-REGAGENT-CONTACT | 0 | With this parameter, a contact handle can be used to display the provider or reseller through whose system the .ASIA domain has been registered | CONTACT or NULL
X-AT-ADMIN-DISCLOSE | 0 | Set to `1` to disclose the administrative contact's details  | `0`, `1` or NULL
X-AT-ADMIN-DISCLOSE-EMAIL | 0 | Set to `1` to disclose the administrative contact's email address | `0`, `1` or NULL
X-AT-ADMIN-DISCLOSE-FAX | 0 | Set to `1` to disclose the administrative contact's fax number | `0`, `1` or NULL
X-AT-ADMIN-DISCLOSE-VOICE | 0 | Set to `1` to disclose the administrative contact's phone number | `0`, `1` or NULL
X-AT-DISCLOSE | 0 | Set to `1` to disclose the details for all contacts | `0`, `1` or NULL
X-AT-DISCLOSE-EMAIL | 0 |  Set to `1` to disclose the email address for all contacts | `0`, `1` or NULL
X-AT-DISCLOSE-FAX | 0 | Set to `1` to disclose the fax number for all contacts | `0`, `1` or NULL
X-AT-DISCLOSE-VOICE | 0 | Set to `1` to disclose the phone number for all contacts | `0`, `1` or NULL
X-AT-REGISTRANT-DISCLOSE | 0 | Set to `1` to disclose the registrant contact's details | `0`, `1` or NULL
X-AT-REGISTRANT-DISCLOSE-EMAIL | 0 | Set to `1` to disclose the registrant contact's email address | `0`, `1` or NULL
X-AT-REGISTRANT-DISCLOSE-FAX | 0 | Set to `1` to disclose the registrant contact's fax number | `0`, `1` or NULL
X-AT-REGISTRANT-DISCLOSE-VOICE | 0 | Set to `1` to disclose the registrant contact's phone number | `0`, `1` or NULL
X-AT-TECH-DISCLOSE | 0 | Set to `1` to disclose the technical contact's details | `0`, `1` or NULL
X-AT-TECH-DISCLOSE-EMAIL | 0 | Set to `1` to disclose the technical contact's email address | `0`, `1` or NULL
X-AT-TECH-DISCLOSE-FAX | 0 | Set to `1` to disclose the technical contact's fax number | `0`, `1` or NULL
X-AT-TECH-DISCLOSE-VOICE | 0 | Set to `1` to disclose the technical contact's phone number | `0`, `1` or NULL
X-AU-REGISTRANT-ID-TYPE | 0 | The ID Type can be one of the following:<br>`ABN`: Australian Business Number<br>`ACN`:  Australian Company Number<br>`RBN`: Business Registration Number<br>`TM`:  Trademark Number | `ABN`, `ACN`, `RBN`, `TM` or `OTHER`
X-AU-REGISTRANT-ID-NUMBER | 0 | The respective ID number depending on the registrant ID type | TEXT or NULL
X-AR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BERLIN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RUHR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BAYERN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-HAMBURG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BR-REGISTER-NUMBER | 0 | The X-BR-REGISTER-NUMBER parameter is mandatory for the registration of a .com.br domain without trustee service | TEXT or NULL
X-CAT-ENS-AUTH-ID | 0 | The ID needed to register a .CAT domain | TEXT or NULL
X-CAT-ENS-AUTH-KEY | 0 | The respective password | TEXT or NULL
X-CAT-ENS-INTENDED-USE | 0 | How the .CAT domain is intended to be used | TEXT or NULL
X-CA-ACCEPT-AGREEMENT-VERSION | 0 | Version of the registrant agreement that is being accepted | TEXT or NULL
X-CA-DISCLOSE | 0 | Set to `1` to disclose the contact's details | `0`, `1` or NULL
X-CA-LEGALTYPE | 0 | The legal type of the domain owner | TEXT or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CA-REGISTRANT-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CA-ADMIN-LANGUAGE | 0 | The admins contact's language (default is `EN`) | TEXT or NULL
X-CA-TECH-LANGUAGE | 0 | The technical contact's language (default is `EN`) | TEXT or NULL
X-CL-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-CN-REGISTRANT-ID-NUMBER | 0 | ID number of the registrant. Only relevant for .CN domains | TEXT or NULL
X-CN-REGISTRANT-ID-TYPE | 0 | The type of ID provided for the registrant. Only relevant for .CN domains | `SFZ`, `HZ`, `GAJMTX`, `TWJMTX`, `WJLSFZ`, `GAJZZ`, `TWJZZ`, `JGZ`, `QT`, `ORG`, `YYZZ`, `TYDM`, `BDDM`, `JDDWFW`, `SYDWFR`, `WGCZJG`, `SHTTFR`, `ZJCS`, `MBFQY`, `JJHFR`, `LSZY`, `WGZHWH`, `WLCZJG`, `SFJD`, `JWJG`, `SHFWJG`, `MBXXBX`, `YLJGZY`, `GZJGZY`, `BJWSXX` or `QTTYDM`
X-CN-ADMIN-ID-NUMBER | 0 | ID number of the administrative contact. Only relevant for .CN domains | TEXT or NULL
X-CN-ADMIN-ID-TYPE | 0 | The type of ID provided for the admin contact. Only relevant for .CN domains | `SFZ`, `HZ`, `GAJMTX`, `TWJMTX`, `WJLSFZ`, `GAJZZ`, `TWJZZ`, `JGZ`, `QT`, `ORG`, `YYZZ`, `TYDM`, `BDDM`, `JDDWFW`, `SYDWFR`, `WGCZJG`, `SHTTFR`, `ZJCS`, `MBFQY`, `JJHFR`, `LSZY`, `WGZHWH`, `WLCZJG`, `SFJD`, `JWJG`, `SHFWJG`, `MBXXBX`, `YLJGZY`, `GZJGZY`, `BJWSXX` or `QTTYDM`
X-CN-TECH-ID-NUMBER | 0 | ID number of the technical contact. Only relevant for .CN domains | TEXT or NULL
X-CN-TECH-ID-TYPE | 0 | The type of ID provided for the tech contact. Only relevant for .CN domains | `SFZ`, `HZ`, `GAJMTX`, `TWJMTX`, `WJLSFZ`, `GAJZZ`, `TWJZZ`, `JGZ`, `QT`, `ORG`, `YYZZ`, `TYDM`, `BDDM`, `JDDWFW`, `SYDWFR`, `WGCZJG`, `SHTTFR`, `ZJCS`, `MBFQY`, `JJHFR`, `LSZY`, `WGZHWH`, `WLCZJG`, `SFJD`, `JWJG`, `SHFWJG`, `MBXXBX`, `YLJGZY`, `GZJGZY`, `BJWSXX` or `QTTYDM`
X-CN-BILLING-ID-NUMBER | 0 | ID number of the billing contact. Only relevant for .CN domains | TEXT or NULL
X-CN-BILLING-ID-TYPE | 0 | The type of ID provided for the billing contact. Only relevant for .CN domains | `SFZ`, `HZ`, `GAJMTX`, `TWJMTX`, `WJLSFZ`, `GAJZZ`, `TWJZZ`, `JGZ`, `QT`, `ORG`, `YYZZ`, `TYDM`, `BDDM`, `JDDWFW`, `SYDWFR`, `WGCZJG`, `SHTTFR`, `ZJCS`, `MBFQY`, `JJHFR`, `LSZY`, `WGZHWH`, `WLCZJG`, `SFJD`, `JWJG`, `SHFWJG`, `MBXXBX`, `YLJGZY`, `GZJGZY`, `BJWSXX` or `QTTYDM`
X-CORE-INTENDED-USE | 0 | Parameter describing the intended use for the domain name | TEXT or NULL
X-CORE-PRIVACY-DISCLOSURE | 0 | Privacy disclosure settings, set to `NATURE-TRUE` to disclose contact details, set to `NATURAL-FALSE` to hide the contact details. Must be set to `LEGAL` if the owner contact is an organization. | `NATURAL-FALSE`, `NATURAL-TRUE` or `LEGAL`
X-DE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-DE-NSENTRY[0..4] | 0 | DNS resource records to directly add to the .DE root nameservers | TEXT or NULL
X-DE-ABUSE-CONTACT | 0 | Abuse contact information for the domain that will be displayed by the registry. Value must consist of a valid URI template string, either a mailto link (e.g. `mailto:contact@example.com` ) or a valid http/https URL (e.g. `https://mycontactform.example`) | TEXT or NULL
X-DE-GENERAL-REQUEST | 0 | General request contact information for the domain that will be displayed by the registry. Value must consist of a valid URI template string, either a mailto link (e.g. `mailto:contact@example.com` ) or a valid http/https URL (e.g. `https://mycontactform.example`) | TEXT or NULL
X-DK-ADMIN-CONTACT | 0 | Customers with an existing DK-HOSTMASTER account can provide their User ID in order to place newly registered domains on their existing account; only relevant for .DK domains | CONTACT or NULL
X-DK-AGREEMENT-ACCEPTEDDATE | 0 | If this date is provided during the registration request for a .DK domain the alternative registration path is enabled and the conclusion of the agreement is not requested by the registry any more. If this flag is present you are responsible to adjust your purchase flow as required by the registry. Further information is available at https://www.dk-hostmaster.dk/en/implementation-guide-registration-dk (How to - method 1). | DATETIME
X-DK-REGISTRANT-CONTACT | 0 | Customers with an existing DK-HOSTMASTER account can provide their User ID in order to place newly registered domains on their existing account; only relevant for .DK domains | CONTACT or NULL
X-DK-VATID | 0 | VAT-ID; only relevant for .DK domains | TEXT or NULL
X-EE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-ES-ACCION-COMERCIAL | 0 | Special promotion token; only relevant for registrar OC customers | TEXT or NULL
X-ES-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Accepts the terms and conditions of an individual registration | `0`, `1` or NULL
X-ES-REGISTRANT-FORM-JURIDICA | 0 | Registrant's legal form | `1`, `39`, `47`, `59`, `68`, `124`, `150`, `152`, `164`, `181`, `197`, `203`, `229`, `269`, `286`, `365`, `434`, `436`, `439`, `476`, `510`, `524`, `525`, `554`, `560`, `562`, `566`, `608`, `612`, `713`, `717`, `744`, `745`, `746`, `747`, `877`, `878` or `879`
X-ES-REGISTRANT-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card<br>`4`: VAT: Tax number | `0`, `1`, `3` or `4`
X-ES-REGISTRANT-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-ADMIN-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-TECH-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-TECH-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-BILLING-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-BILLING-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-EU-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Trustee Contact Service for the Owner-C, I you can't provide a local presence in the EU | `0`, `1` or NULL
X-EU-REGISTRANT-CITIZENSHIP | 0 | Citizenship of the registrant. Only relevant for natural persons with an European citizenship residing outside of the EU | `at`, `be`, `bg`, `cz`, `cy`, `de`, `dk`, `es`, `ee`, `fi`, `fr`, `gr`, `hu`, `ie`, `it`, `lt`, `lu`, `lv`, `mt`, `nl`, `pl`, `pt`, `ro`, `se`, `sk`, `si` or `hr`
X-EU-REGISTRANT-LANG | 0 | Language of the .EU Domain registrant; possible values:<br>`cs`<br>`da`<br>`de`<br>`el`<br>`en`<br>`es`<br>`et`<br>`fi`<br>`fr`<br>`hu`<br>`it`<br>`lt`<br>`lv`<br>`mt`<br>`nl`<br>`pl`<br>`pt`<br>`sk`<br>`sl`<br>`sv` | `cs`, `da`, `de`, `el`, `en`, `es`, `et`, `fi`, `fr`, `hu`, `it`, `lt`, `lv`, `mt`, `nl`, `pl`, `pt`, `sk`, `sl` or `sv`
X-FI-IDNUMBER | 0 | Registrant's personal or organizational identification number; only relevant for .FI domains | TEXT or NULL
X-FI-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .FI domains | `0`, `1` or NULL
X-FI-DOMAIN-NAME-HOLDER-COMPANY-TYPE | 0 | Type of company applying for an .FI domain; possible values:<br>`0`: Private person<br>`1`: Company (default)<br>`2`: Association<br>`3`: Foundation<br>`4`: Municipality<br>`5`: Political party<br>`6`: State<br>`7`: Public corporation | INT or NULL
X-FI-DEPARTMENT | 0 | Company department; only relevant for .FI domains | TEXT or NULL
X-FI-BASED-ON-PERSON-NAME | 0 | Set to `1` in order to indicate that the domain name is based on the personal or company name of the registrant; only relevant for .FI domains | TEXT or NULL
X-FI-PERSON-NAME-REGISTRATION-ID | 0 | The register where the company name on which the domain name is based has been registered; only relevant for .FI domains | INT or NULL
X-FI-PERSON-NAME-REGISTRATION-NUMBER | 0 | The registration number of the registered company name on which the domain name is based; only relevant for .FI domains | TEXT or NULL
X-FI-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date; only relevant for .FI domains<br>Mandatory for non-finish private persons | TEXT or NULL
X-FI-REGISTRANT-IDNUMBER | 0 | The registrant's ID number; only relevant for .FI domains | TEXT or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Enables our .FR Trustee Solution which sets our .FR trustee contact as contact person for the domain | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-PM-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-WF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-YT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-ADMIN-DISCLOSE | 0 | Set to `1` to disclose the administrators's details | TEXT or NULL
X-FR-DATE-PUBLICATION-JO | 0 | Date of the declaration of the trademark registration | TEXT or NULL
X-FR-NUMERO-DE-PAGE-ANNOUNCE-JO | 0 | Trademark registration journal number | TEXT or NULL
X-FR-SIREN-OR-SIRET | 0 | SIREN / SIRET number | TEXT or NULL
X-FR-WALDEC | 0 | WALDEC number | TEXT or NULL
X-FR-DUNS | 0 | DUNS number | TEXT or NULL
X-FR-LOCAL | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-FR-REGISTRANT-BIRTH-DATE | 0 | Birth date of the registrant | TEXT or NULL
X-FR-REGISTRANT-BIRTH-PLACE | 0 | Birth place of the registrant | TEXT or NULL
X-FR-REGISTRANT-DISCLOSE | 0 | Set to `1` to disclose the registrant's details | TEXT or NULL
X-FR-REGISTRANT-TRADEMARK-NUMBER | 0 | Registration number of the registered trademark | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM | 0 | Legal form of the entity (in case registrant is not a natural person) | TEXT or NULL
X-FR-REGISTRANT-LEGAL-FORM-OTHER | 0 | Other form than the possible values of the above parameter | TEXT or NULL
X-FR-REGISTRANT-LEGAL-ID | 0 | ID of the registrant | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-DECLARATION | 0 | Date of the declaration of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-JO-NUMBER | 0 | Trademark registration journal number | TEXT or NULL
X-FR-REGISTRANT-JO-PAGE | 0 | Trademark registration journal page | TEXT or NULL
X-FR-REGISTRANT-JO-DATE-PUBLICATION | 0 | Publication date of the trademark registration | TEXT or NULL
X-FR-REGISTRANT-DUNS-NUMBER | 0 | The DUNS number is a nine-digit number, issued by Dun & Bradstreet. DUNS is the abbreviation of Data Universal Numbering System. Companies with a valid DUNS number are still obliged having their head office in the territory of the European Union. The DUNS number can be provided using this parameter | TEXT or NULL
X-FR-REGISTRANT-LOCAL-ID | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
X-GAY-ACCEPT-REQUIREMENTS | 0 | Set to `1` to accept the policy and enforcement terms | `0`, `1` or NULL
X-HK-REGISTRANT-CHINESE-COMPANY | 0 | Company name in Chinese | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-TYPE | 0 | Must be one of the following for individuals:<br>`HKID`: Hong Kong Identity Number<br>`OTHID`: Other's Country Identity Number<br>`PASSNO`: Passport No.<br>`BIRTHCERT`: Birth Certificate<br>`OTHIDV`: Others Individual Document<br>Must be one of the following for organizations:<br>`BR`: Business Registration Certificate<br>`CI`: Certificate of Incorporation<br>`CRES`: Certificate of Registration of a School<br>`HKSARG`: Hong Kong Special Administrative Region Government Department <br>`HKORDINANCE`: Ordinance of Hong Kong<br>`OTHORG`: Others Organization Document | TEXT or NULL
X-HK-REGISTRANT-OTHER-DOCUMENT-TYPE | 0 | Type of document if other document was chosen | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-NUMBER | 0 | The respective document number | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-ORIGIN-COUNTRY | 0 | ISO-3166 Country Code | COUNTRY or NULL
X-HK-REGISTRANT-BIRTH-DATE | 0 | Registrant's birth date, mandatory if the registrant is an individual | TEXT or NULL
X-HK-REGISTRANT-INDUSTRY-TYPE | 0 | Registrant's industry type; default is: `0` (not specified) | TEXT or NULL
X-HK-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Accept the terms and conditions of a individual registration | `0`, `1` or NULL
X-HU-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-IDN-LANGUAGE | 0 | If the domain is an IDN domain, please state the IDN language code | TEXT
X-IE-CONTACT-TYPE | 0 | The type of the registrant, following values are possible:<br>`CHA `: a charitable organization based in Ireland<br>`COM `: a business or company that is incorporated in Ireland<br>`OTH `: an individual or organization that does not fall into the charity or company categories but has a connection to Ireland | TEXT
X-IE-CRO-NUMBER | 0 | The Companies Registration Office (CRO)identifier. Mandatory if the `X-IE-CONTACT-TYPE` is `COM`. | TEXT
X-IE-SUPPORT-NUMBER | 0 | The identifier for a charity or a supporting number (RBN or VAT, for example)for other contact types. Mandatory if the `X-IE-CONTACT-TYPE` is `CHA`. | TEXT
X-IE-REGISTRANT-CLASS | 0 | The class of the registrant, following values are possible:<br>`Body Corporate (Ltd,PLC,Company)`<br>`Constitutional Body `<br>`Discretionary Applicant `<br>`Natural Person `<br>`School/Educational Institution `<br>`Sole Trader `<br>`Statutory Body `<br>`Unincorporated Association` | TEXT
X-IE-REGISTRANT-CATEGORY | 0 | Based on the registrant class the registrant category has to state one of the following details:<br>`Body Corporate (Ltd,PLC,Company)`: Corporate Name, Discretionary Name, Publication Name, Registered Business Name, Registered Trade Mark Name<br>`Constitutional Body`: Discretionary Name, Publication Name, Registered Trade Mark Name, State Agency Name<br>`Discretionary Applicant`: Discretionary Name<br>`Natural Person`: Discretionary Name, Personal Name, Politician's Name, Registered Trade Mark Name<br>`School/Educational Institution`: Discretionary Name, Publication Name, Registered Trade Mark Name, School/Educational Institution Name<br>`Sole Trader`: Discretionary Name, Personal Trading Name, Publication Name, Registered Business Name, Registered Trade Mark Name<br>`Statutory Body`: Discretionary Name, Publication Name, Registered Trade Mark Name, State Agency Name<br>`Unincorporated Association`: Discretionary Name, Publication Name, Registered Business Name, Registered Trade Mark Name, Unincorporated Association Name | TEXT
X-IE-REGISTRANT-REMARKS | 0 | Trade mark number or VAT-ID | TEXT
X-IT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-IT-PIN | 0 | Taxpayer number for .IT domain registrations | TEXT or NULL
X-IT-NATIONALITY | 0 | The nationality of the registrant contact if it deviates from the country code | TEXT or NULL
X-IT-REGISTRANT-ENTITY-TYPE | 0 | In some special cases you need to specify the exact entity type of the registrant:<br>`1`: Italian and foreign natural persons<br>`2`: Italian Companies / one man companies<br>`3`:  freelance workers / professionals <br>`4`: non-profit organizations<br>`5`: public organizations<br>`6`:  	other subjects<br>`7`: foreigners who match 2 - 6 | TEXT or NULL
X-IT-CONSENTFORPUBLISHING | 0 | State if you agree to the .IT Consent for Publishing | `0`, `1` or NULL
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | Accepts - "Section 6 - Consent to the processing of personal data for diffusion and accessibility via the internet" | `0`, `1` or NULL
X-IT-ACCEPT-LIABILITY-TAC | 0 | Accepts "Section 3 - Declarations and assumptions of liability" | `0`, `1` or NULL
X-IT-ACCEPT-REGISTRATION-TAC | 0 | Accepts "Section 5 - Consent to the processing of personal data for registration" | `0`, `1` or NULL
X-IT-ACCEPT-EXPLICIT-TAC | 0 | Accepts "Section 7 - Explicit acceptance of the following points" | `0`, `1` or NULL
X-JP-ORGANIZATION | 0 | Organization name; only relevant for .JP domains | TEXT or NULL
X-JP-KANA-ORGANIZATION | 0 | Organization name in Japanese; only relevant for .JP domains | TEXT or NULL
X-JP-ADDRESS | 0 | Organization address; only relevant for .JP domains | TEXT or NULL
X-JP-TITLE | 0 | Representative title; only relevant for .JP domains | TEXT or NULL
X-JP-REGISTRATION-DATE | 0 | Organization registration date; only relevant for .JP domains | TEXT or NULL
X-JP-REGISTRATION-ADDRESS | 0 | Organization registration address; only relevant for .JP domains | TEXT or NULL
X-JP-NAME | 0 | Representative name; only relevant for .JP domains | TEXT or NULL
X-JP-TYPE | 0 | Organization type; only relevant for .JP domains | TEXT or NULL
X-JP-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-KR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-LT-REGISTRANT-LEGAL-ID | 0 | Legal entity identification code of the registrant of a .LT domain. Required as of December 1, 2018 if the registrant is a legal entity. | TEXT or NULL
X-MK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MOBI-ACCEPT-INSTANTMOBILIZER-TAC | 0 | Activates the Instant Mobilizer | `0`, `1` or NULL
X-MOBI-INSTANTMOBILIZER-DOMAIN | 0 | The website to proxy | DOMAIN or NULL
X-MY-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-MY-REGISTRANT-ORGANIZATION-TYPE | 0 | The registrant's organization type | INT
X-MY-REGISTRANT-RACE | 0 | Registrant's nationality | `MALAY`, `CHINESE`, `INDIAN` or `OTHERS`
X-MY-REGISTRANT-PROOF-OF-IDENTITY | 0 | Document submitted as a proof of the registrant's identity | LONGTEXT
X-NAME-NOEMAIL | 0 | Only applies to .NAME registration (`1` = "Yes" / `0` = "No") | `1`, `0` or NULL
X-NAME-EMAILFORWARD | 0 | .NAME eMail Forwarding | EMAIL or NULL
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-NICSE-DISCLOSE | 0 | If set to `1` the registrant's details get disclosed | `0`, `1` or NULL
X-NGO-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-ONG-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | `0`, `1` or NULL
X-NL-ACCEPT-TRUSTEE-TAC | 0 | Set this parameter to `1` to use our Trustee Contact Service for the Owner-C, if you can't provide a local presence in the Netherlands. | `0`, `1` or NULL
X-NL-REGISTRANT-LEGAL-FORM | 0 | Registrant's legal form | `ANDERS`, `BGG`, `BRO`, `BV`, `COOP`, `CV`, `EENMANSZAAK`, `EESV`, `KERK`, `MAATSCHAP`, `NV`, `OWM`, `PERSOON`, `REDR`, `STICHTING`, `VERENIGING`, `VOF` or NULL
X-NL-REGISTRANT-LEGAL-FORM-REG-NO | 0 | Registrant's legal form registration number | TEXT or NULL
X-NO-REGISTRANT-IDENTITY | 0 | The organization number of the Norwegian organization (consisting of exactly 9 digits) or the PID Number in format N.PRI.12345678 | TEXT
X-NO-DECLARATION-VERSION | 0 | Version of the declaration form on which the domain name policy is accepted | TEXT or NULL
X-NO-CONSENTING-PERSON-NAME | 0 | Name of the person accepting the domain name policy | TEXT or NULL
X-NO-DECLARATION-TIMESTAMP | 0 | Date and time when the domain name policy has been accepted | TEXT or NULL
X-NU-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .NU domains | `0`, `1` or NULL
X-NYC-REGISTRANT-NEXUS-CATEGORY | 0 | The value of this parameter has to be either <br>`1` for a natural person whose primary place of domicile is a valid physical address in the City of New York or <br> `2` for an entity or organization that has a physical street address in the City of New York | `1`, `2` or NULL
X-PARIS-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions of the registration | `0`, `1` or NULL
X-PL-REASON | 0 | .PL Reason of registration | TEXT or NULL
X-PRO-REGISTRATIONTYPE | 0 | Type of .PRO registration | TEXT or NULL
X-PRO-REDIRECT | 0 | Can be used to enter a REDIRECT of a SecondLevelRedirecting .PRO domain to a Third-Level-Domain | TEXT or NULL
X-PRO-ACTIVATION | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | `1`, `0` or NULL
X-PRO-PW | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | TEXT or NULL
X-PRO-ROID | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | TEXT or NULL
X-PRO-TRADEMARKNAME | 0 | The name of the registered trademark | TEXT or NULL
X-PRO-TRADEMARKJURISDICTION | 0 | ISO-3166 Country Code of the country in which the jurisdiction for the trademark applies | COUNTRY or NULL
X-PRO-TRADEMARKDATE | 0 | The registration date of the registered trademark | TEXT or NULL
X-PRO-TRADEMARKNUMBER | 0 | The registration number of the registered trademark | TEXT or NULL
X-PT-REGISTRANT-VATID | 0 | The registrant's VAT-ID. Required if the contact is used for the first time for a .PT domain | TEXT or NULL
X-PT-ADMIN-VATID | 0 | The admin's VAT-ID | TEXT or NULL
X-PT-TECH-VATID | 0 | The technical contact's VAT-ID. Required if the contact is used for the first time for a .PT domain | TEXT or NULL
X-PT-LEGITIMACY | 0 | Registrant type; only relevant for .PT domains | TEXT or NULL
X-PT-REGISTRATION-BASIS | 0 | Registration reason; only relevant for .PT domains | TEXT or NULL
X-PT-BRAND-DATE | 0 | Registration date of the brand; only relevant for .PT domains | DATE or NULL
X-PT-BRAND-NUMBER | 0 | Registration number of the brand; only relevant for .PT domains | TEXT or NULL
X-PT-BRAND-WAY-OF-REGISTRY | 0 | Registration type of the brand; only relevant for .PT domains | TEXT or NULL
X-PT-ARBITRATION | 0 | Special arbitration parameter; only relevant for .PT domains | `true`, `false` or NULL
X-PT-REGISTRANT-MOBILE | 0 | Registrant's mobile number | PHONE or NULL
X-PT-TECH-MOBILE | 0 | Technical contact's mobile number | PHONE or NULL
X-RO-PERSONTYPE | 0 | Registrant entity type; can be `c` (company) or `p` (person)  | TEXT or NULL
X-RU-KPP | 0 | Registrant's KPP number | TEXT or NULL
X-RU-ACCEPT-INDIVIDUAL-REGISTRATION-TAC | 0 | Set `1` to accept the terms and condition of a individual registration, mandatory if the registrant is an individual | `0`, `1` or NULL
X-RU-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-DATA | 0 | Registrant's passport data including passport number, issue date, and place of issue | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-NUMBER | 0 | Registrant's passport number | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-DATE | 0 | Registrant's passport issue date | TEXT or NULL
X-RU-REGISTRANT-PASSPORT-LOCATION | 0 | Registrant's passport place of issue | TEXT or NULL
X-RU-REGISTRANT-KPP | 0 | Registrant's KPP number | TEXT or NULL
X-RU-REGISTRANT-TIN | 0 | Registrant's TIN number | TEXT or NULL
X-RU-REGISTRANT-NAME | 0 | Registrant's name | TEXT or NULL
X-SE-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions; only relevant for .SE domains | `0`, `1` or NULL
X-SG-RCBID | 0 | Companies located in Singapore must enter their registration number | TEXT or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-SWISS-UID | 0 | The enterprise ID, in the specific context of .swiss based on current rules, is the Swiss UID/UPI/IDE/IDI. | TEXT
X-SWISS-OWNER-TYPE | 0 | The owner type, in the specific context of .swiss based on current rules, depending on application for natural persons (P) or organizations (O) | `P` or `O`
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-TEL-WHOISTYPE | 0 | With this parameter the way the domain will be displayed in the WHOIS can be selected | `Legal`, `Natural` or NULL
X-TEL-PUBLISH | 0 | If set to `N`, the registrant's contact data will not be shown in the WHOIS | `Y`, `N` or NULL
X-TO-CUSTOMER-HANDLE | 0 | Customer handle; only relevant for .TO domains | TEXT or NULL
X-TRAVEL-UIN | 0 | In order to register .travel domains the registrant has to provide a UIN "Unique Identification Number". The UIN can be provided to the registrant through an Association Authentification Partner (a list of AAPs can be viewed under http://www.tralliance.info/authentication.htm). | TEXT or NULL
X-TRAVEL-INDUSTRY | 0 | In order to register .travel domains the registrant has to indicate a relationship to the travel industry | `1` or NULL
X-UK-REG-OPT-OUT | 0 | If set to `Y`, the registrant's contact data will not be shown in the WHOIS | TEXT or NULL
X-UK-REG-TYPE | 0 | Registrant type | TEXT or NULL
X-UK-REG-CO-NO | 0 | Registrant Company Number | TEXT or NULL
X-UK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | `P1`, `P2`, `P3`, `P4`, `P5` or NULL
X-US-NEXUS-CATEGORY | 0 | Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | `C11`, `C12`, `C21`, `C31`, `C32` or NULL
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32) | COUNTRY or NULL
X-VE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-XXX-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions of the registration | NULL, `1` or `0`
X-XXX-MEMBERSHIP-CONTACT | 0 | Contact Handle ID | CONTACT or NULL
X-XXX-NON-RESOLVING | 0 | Set to `1` to register a .XXX domain that should not resolve | `0`, `1` or NULL
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
X-BOATS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-HOMES-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-WDRP-RSP | 0 | Name of the RSP appearing in the WDRP email | TEXT or NULL
X-WDRP-URL | 0 | URL of the RSP appearing in the WDRP email | TEXT or NULL
X-WDRP-SIGNATURE[0..3] | 0 | Signature appearing at the end of the WDRP email | TEXT or NULL
X-WDRP-MAILFROM | 0 | Name of the sender used for the WDRP email | TEXT or NULL
X-ERRP-RSP | 0 | Name of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-URL | 0 | URL of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-EMAIL | 0 | Email address of the RSP appearing in the ERRP email | EMAIL or NULL
X-ERRP-PHONE | 0 | Phone number of the RSP appearing in the ERRP email | PHONE or NULL
X-ERRP-TAC-URL | 0 | Terms and Conditions of the RSP appearing in the ERRP email | TEXT or NULL
X-ERRP-SIGNATURE[0..3] | 0 | Signature appearing at the end of the ERRP email | TEXT or NULL
X-WHOIS-URL | 0 | URL to display in our whois | TEXT or NULL
X-WHOIS-RSP | 0 | RSP name to display in our whois | TEXT or NULL
X-WHOIS-BANNER[0..2] | 0 | Text to display in our whois (e.g. Advertising campaign) | TEXT or NULL
X-ID-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ZA-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ZUERICH-AGREEMENT | 0 | Set to `1` to accept the local laws of Canton of Zurich, in particular to the TLDV ordinance | `1` or NULL
X-ZUERICH-UID | 0 |   Enterprise Identification Number (UID) or PUBLIC | TEXT
X-ACCEPT-WHOISTRUSTEE-TAC | 0 | Activates the Whois Trustee Service | `0`, `1` or NULL
X-ACCEPT-WHOISTRUSTEELITE-TAC | 0 | Activates the Whois Trustee Service Lite | `0`, `1` or NULL
INTERNALDNS | 0 | Creates the necessary dns zone before submitting application to the registry. | `0`, `1` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
218 | Request is available
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
546 | Credit limit exceeded
549 | Command Failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT[0..N] | 0 | N | Administrative contacts | CONTACT
ADMINCONTACTMANAGEMENTTYPE | 1 | 1 | How administrative contacts are managed at the registry; can be `THICK`, `THIN`, `PLAIN` | TEXT
BILLINGCONTACT[0..N] | 0 | N | Billing contacts | CONTACT
BILLINGCONTACTMANAGEMENTTYPE | 1 | 1 | How billing contacts are managed at the registry; can be `THICK`, `THIN`, `PLAIN` | TEXT
NAMESERVER[0..N] | 0 | N | Nameservers | HOSTNAME
OWNERCONTACT[0..N] | 0 | N | Registrant contacts | CONTACT
OWNERCONTACTMANAGEMENTTYPE | 1 | 1 | How registrant contacts are managed at the registry; can be `THICK`, `THIN`, `PLAIN` | TEXT
REPOSITORY | 1 | 1 | Domain repository | TEXT
REPOSITORYADMINCONTACT[0..N] | 0 | N | Repository administrative contacts | CONTACT
REPOSITORYBILLINGCONTACT[0..N] | 0 | N | Repository billing contacts | CONTACT
REPOSITORYOWNERCONTACT[0..N] | 0 | N | Repository registrant contacts | CONTACT
REPOSITORYTECHCONTACT[0..N] | 0 | N | Repository technical contacts | CONTACT
TECHCONTACT[0..N] | 0 | N | Technical contacts | CONTACT
TECHCONTACTMANAGEMENTTYPE | 1 | 1 | How technical contacts are managed at the registry; can be `THICK`, `THIN`, `PLAIN` | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckDomainRegistration
ADMINCONTACT0 = P-TUE1378025
BILLINGCONTACT0 = P-TUE1378025
DOMAIN = domain123abc.com
NAMESERVER0 = ns1.hexonet.net
NAMESERVER1 = ns2.hexonet.net
OWNERCONTACT0 = P-TUE1378025
TECHCONTACT0 = P-TUE1378025
EOF
```
### Response

```
[RESPONSE]
CODE = 218
DESCRIPTION = Request is available
PROPERTY[ADMINCONTACT][0] = P-TUE1378025
PROPERTY[ADMINCONTACTMANAGEMENTTYPE][0] = THIN
PROPERTY[BILLINGCONTACT][0] = P-TUE1378025
PROPERTY[BILLINGCONTACTMANAGEMENTTYPE][0] = THIN
PROPERTY[NAMESERVER][0] = ns1.hexonet.net
PROPERTY[NAMESERVER][1] = ns2.hexonet.net
PROPERTY[OWNERCONTACT][0] = P-TUE1378025
PROPERTY[OWNERCONTACTMANAGEMENTTYPE][0] = THIN
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[TECHCONTACT][0] = P-TUE1378025
PROPERTY[TECHCONTACTMANAGEMENTTYPE][0] = THIN
EOF
```

----
