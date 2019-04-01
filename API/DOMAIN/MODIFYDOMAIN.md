# ModifyDomain

## DESCRIPTION
Modify a domain name.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyDomain` | COMMAND
DOMAIN | 0 | Domain name; required unless DOMAINAUTH parameter is used | DOMAIN
DOMAINAUTH | 0 | Domain name and authorization code provided as one parameter; must have the form "DOMAIN AUTH" | TEXT
ADDNAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME
DELNAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME
NAMESERVER[0..12] | 0 | Nameserver Hostname | HOSTNAME or NULL
NAMESERVERSET | 0 | ID of a nameserver set | TEXT or NULL
SECDNS-DS[0..N] | 0 | Set the respective SECDNS record | LONGTEXT or NULL
ADDSECDNS-DS[0..N] | 0 | Add the respective SECDNS record | LONGTEXT or NULL
DELSECDNS-DS[0..N] | 0 | Delete the respective SECDNS record | LONGTEXT or NULL
SECDNS-KEY[0..N] | 0 | Set the respective SECDNS record | LONGTEXT or NULL
ADDSECDNS-KEY[0..N] | 0 | Add the respective SECDNS record | LONGTEXT or NULL
DELSECDNS-KEY[0..N] | 0 | Delete the respective SECDNS record | LONGTEXT or NULL
SECDNS-MAXSIGLIFE | 0 | Set the lifespan of the SECDNS key| INT
SECDNS-URGENT | 0 | Set to `1` in order to request a high priority SECDNS update; note that if this is not supported or cannot be executed at the moment, the whole update request may be rejected | `0` or `1`
SECDNS-REMOVE-ALL | 0 | If set to `1` all SECDNS records get deleted | `0` or `1`
ADDOWNERCONTACT0 | 0 | Add the respective owner contact | CONTACT
DELOWNERCONTACT0 | 0 | Delete the respective owner contact | CONTACT
OWNERCONTACT[0..4] | 0 | Set the respective owner contact | CONTACT or NULL
ADDADMINCONTACT[0..2] | 0 | Add the respective admin contact | CONTACT
DELADMINCONTACT[0..2] | 0 | Delete the respective admin contact | CONTACT
ADMINCONTACT[0..2] | 0 | Set the respective admin contact | CONTACT or NULL
ADDTECHCONTACT[0..2] | 0 | Add the respective technical contact | CONTACT
DELTECHCONTACT[0..2] | 0 | Delete the respective technical contact | CONTACT
TECHCONTACT[0..2] | 0 | Set the respective technical contact | CONTACT or NULL
ADDBILLINGCONTACT[0..2] | 0 | Add the respective billing contact | CONTACT
DELBILLINGCONTACT[0..2] | 0 | Delete the respective billing contact | CONTACT
BILLINGCONTACT[0..2] | 0 | Set the respective billing contact | CONTACT or NULL
ADDSTATUS[0..N] | 0 | Add a status flag like `clientTransferProhibited` | DOMAINSTATUS
DELSTATUS[0..N] | 0 | Delete a status flag like `clientTransferProhibited` | DOMAINSTATUS
STATUS[0..N] | 0 | Set a status flag like `clientTransferProhibited` | DOMAINSTATUS or NULL
AUTH | 0 | Domain authorization code (min 6 letters) | TEXT
HOST[0..N] | 0 | Nameserver hostnames and IP addresses | TEXT or NULL
DELHOST[0..N] | 0 | Delete the respective host | TEXT or NULL
ADDHOST[0..N] | 0 | Add the respective host | TEXT or NULL
GENERATERANDOMAUTH | 0 | If set to `1` a random authorization code gets generated for the domain | `0`, `1` or NULL
TRANSFERLOCK | 0 | If set to `1` the clientTransferProhibited flag gets set | `0`, `1` or NULL
FORCE | 0 | Enforce certain domain updates that would otherwise be rejected; only possible for repository owners | `0`, `1` or NULL
REGISTRANT-VERIFIED | 0 | By setting this parameter to `1` it is declared that the domain registrant has been verified; only possible for repository owners | `1` or NULL
X-CAT-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-DISCLOSE | 0 | If set to `1` the domain's details get disclosed | `0`, `1` or NULL
X-HEALTH-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1`
X-REGISTRANT-DISCLOSE | 0 | If set to `1` the registrant's details get disclosed  | `0`, `1` or NULL
X-ADMIN-DISCLOSE | 0 |  If set to `1` the admin's details get disclosed | `0`, `1` or NULL
X-TECH-DISCLOSE | 0 |  If set to `1` the technical contact's details get disclosed | `0`, `1` or NULL
X-BILLING-DISCLOSE | 0 |  If set to `1` the billing contact's details get disclosed | `0`, `1` or NULL
X-REGISTRANT-BIRTHDATE | 0 | The registrant's birthdate | TEXT or NULL
X-ADMIN-BIRTHDATE | 0 | The admin's birthdate | TEXT or NULL
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
X-ASSOCIATION-ID | 0 | Special contact ID; only relevant for .XXX domains | TEXT or NULL
X-ASSOCIATION-AUTH | 0 | Special contact authorization code; only relevant for .XXX domains | TEXT or NULL
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
X-AR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-ASIA-CED-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0` or `1`
X-ASIA-CED-CCLOCALITY | 0 | Location or domicile of the Entity (based on the corresponding ISO3166 code).  | TEXT or NULL
X-ASIA-CED-CONTACT | 0 | Indicates which contact should be used as CED. Must be `registrant`, `admin`, `tech` or `billing` | TEXT or NULL
X-ASIA-CED-LOCALITYSP | 0 | Province of establishment of the CED.  | TEXT or NULL
X-ASIA-CED-LOCALITYCITY | 0 | City of establishment of the CED.  | TEXT or NULL
X-ASIA-CED-LEGALENTITYTYPE | 0 | Must be one of the following: <br>`naturalPerson`<br>`corporation`<br>`cooperative`<br>`partnership`<br>`government`<br>`politicalParty`<br>`society`<br>`institution`<br>`other Type of Entity` | TEXT or NULL
X-ASIA-CED-IDENTFORM | 0 | Must be one of the following: <br>`passport`<br>`certificate`<br>`legislation`<br>`societyRegistry`<br>`politicalPartyRegistry`<br>`other`  | TEXT or NULL
X-ASIA-CED-IDENTNUMBER | 0 | Identification Number / Code of Reference (e.g. Passport number, Business Certificate number, Act or Legislation number/code, etc.).  | TEXT or NULL
X-ASIA-CED-OTHERLETYPE | 0 | Other legal entity type | TEXT or NULL
X-ASIA-CED-OTHERIDENTFORM | 0 | If the legal entity type or form of identification is "other", please enter the appropriate information to support the claim. | TEXT or NULL
X-ASIA-NOTF-CONTACT | 0 | With this parameter you can specify an Operations and Notifications Contact (OPN/NOTF Contact) to designate the point of contact to whom documentary evidence requests, auction invitations, and reminders are to be sent | CONTACT or NULL
X-ASIA-MAINTAINERURL | 0 | This parameter can contain the URL and/or name of the party responsible for maintaining the domain. | TEXT or NULL
X-ASIA-REGAGENT-CONTACT | 0 | Contact Handle ID | CONTACT or NULL
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
X-BERLIN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RUHR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-BAYERN-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-HAMBURG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-CA-DOMAIN-TRADEMARK | 0 | Domain trademark | TEXT or NULL
X-CA-ACCEPT-AGREEMENT-VERSION | 0 | Version of the registrant agreement that is being accepted | TEXT or NULL
X-CA-LANGUAGE | 0 | The registrant contact's language (default is `EN`) | TEXT or NULL
X-CA-LEGALTYPE | 0 |  The legal type of the domain owner* | TEXT or NULL
X-CA-DISCLOSE | 0 | Set to `1` to disclose the contact's details | `0`, `1` or NULL
X-CN-REGISTRANT-ID-NUMBER | 0 | ID number of the registrant. Only relevant for .CN domains | TEXT or NULL
X-CN-REGISTRANT-ID-TYPE | 0 | The type of ID provided for the registrant. Only relevant for .CN domains | `SFZ`, `HZ`, `JGZ`, `ORG`, `YYZZ` or `QT`
X-CN-ADMIN-ID-NUMBER | 0 | ID number of the administrative contact. Only relevant for .CN domains | TEXT or NULL
X-CN-ADMIN-ID-TYPE | 0 | The type of ID provided for the admin contact. Only relevant for .CN domains | `SFZ`, `HZ`, `JGZ`, `ORG`, `YYZZ` or `QT`
X-CN-TECH-ID-NUMBER | 0 | ID number of the technical contact. Only relevant for .CN domains | TEXT or NULL
X-CN-TECH-ID-TYPE | 0 | The type of ID provided for the tech contact. Only relevant for .CN domains | `SFZ`, `HZ`, `JGZ`, `ORG`, `YYZZ` or `QT`
X-CN-BILLING-ID-NUMBER | 0 | ID number of the billing contact. Only relevant for .CN domains | TEXT or NULL
X-CN-BILLING-ID-TYPE | 0 | The type of ID provided for the billing contact. Only relevant for .CN domains | `SFZ`, `HZ`, `JGZ`, `ORG`, `YYZZ` or `QT`
X-CORE-PRIVACY-DISCLOSURE | 0 | Privacy disclosure settings, set to `NATURE-TRUE` to disclose contact details, set to `NATURAL-FALSE` to hide the contact details. Must be set to `LEGAL` if the owner contact is an organization. | `NATURAL-FALSE`, `NATURAL-TRUE` or `LEGAL`
X-DE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-DE-NSENTRY[0..4] | 0 | DNS resource records to directly add to the .DE root nameservers | TEXT or NULL
X-DPML-VARIANT-LABEL[0..N] | 0 | When registering a Rightside DPML block up to 10 variants can be stated here that will be blocked in addition to the primary DPML block | TEXT or NULL
X-ES-ADMIN-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-ADMIN-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-TECH-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-TECH-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-ES-BILLING-TIPO-IDENTIFICACION | 0 | Must be one of the following:<br>`0`: Otra; For non-spanish owner<br>`1`: NIF/DNI; For Spanish Individual or Organization<br>`3`: NIE: Alien registration card | `0`, `1` or `3`
X-ES-BILLING-IDENTIFICACION | 0 | One of the following ID numbers can be provided via this parameter:<br>__For non-spanish owner__: passport number, drivers license number or even national identify card number<br>__For Spanish Individual or Organization__: Spanish National Personal ID or company VAT ID number<br>__Alien registration card__: Spanish resident alien ID number | TEXT or NULL
X-FI-REGISTRANT-BIRTH-DATE | 0 | The registrant's birth date; only relevant for .FI domains<br>Mandatory for non-finish private persons | TEXT or NULL
X-FI-REGISTRANT-IDNUMBER | 0 | The registrant's ID number; only relevant for .FI domains | TEXT or NULL
X-EU-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-AFNIC-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-RE-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-PM-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-TF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-WF-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-YT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-FR-BIRTHDATE | 0 | Birth date of the registrant | TEXT or NULL
X-FR-BIRTHPLACE | 0 | Birth place of the registrant | TEXT or NULL
X-FR-DATE-PUBLICATION-JO | 0 | Date of the declaration of the trademark registration | TEXT or NULL
X-FR-NUMERO-DE-PAGE-ANNOUNCE-JO | 0 | Trademark registration journal number | TEXT or NULL
X-FR-SIREN-OR-SIRET | 0 | SIREN / SIRET number | TEXT or NULL
X-FR-WALDEC | 0 | WALDEC number | TEXT or NULL
X-FR-DUNS | 0 | DUNS number | TEXT or NULL
X-FR-LOCAL | 0 | Companies with a local identifier specific to a country of the European Economic Area can provide their local identifier using this parameter | TEXT or NULL
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
X-HK-REGISTRANT-DOCUMENT-TYPE | 0 | Must be one of the following for individuals:<br>`HKID`: Hong Kong Identity Number<br>`OTHID`: Other's Country Identity Number<br>`PASSNO`: Passport No.<br>`BIRTHCERT`: Birth Certificate<br>`OTHIDV`: Others Individual Document<br>Must be one of the following for organizations:<br>`BR`: Business Registration Certificate<br>`CI`: Certificate of Incorporation<br>`CRES`: Certificate of Registration of a School<br>`HKSARG`: Hong Kong Special Administrative Region Government Department <br>`HKORDINANCE`: Ordinance of Hong Kong<br>`OTHORG`: Others Organization Document | TEXT or NULL
X-HK-REGISTRANT-OTHER-DOCUMENT-TYPE | 0 | Type of document if other document was chosen | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-NUMBER | 0 | The respective document number | TEXT or NULL
X-HK-REGISTRANT-DOCUMENT-ORIGIN-COUNTRY | 0 | ISO-3166 Country Code | COUNTRY or NULL
X-HK-REGISTRANT-BIRTH-DATE | 0 | Registrant's birth date, mandatory if the registrant is an individual | TEXT or NULL
X-HK-REGISTRANT-INDUSTRY-TYPE | 0 | Registrant's industry type; default is: `0` (not specified) | TEXT or NULL
X-IT-PIN | 0 |  If the registrant is an individual, the PIN has to be: <br> The registrant's fiscal code or  the number of an identity document<br>If  the registrant is an organization, the PIN has to be:<br> The company's fiscal code or the company's VAT number | TEXT or NULL
X-IT-NATIONALITY | 0 | The nationality of the registrant contact if it deviates from the country code. | TEXT or NULL
X-IT-CONSENTFORPUBLISHING | 0 | State if you agree to the .IT Consent for Publishing | `0`, `1` or NULL
X-IT-ACCEPT-DIFFUSION-AND-ACCESSIBILITY-TAC | 0 | Accepts - "Section 6 - Consent to the processing of personal data for diffusion and accessibility via the internet" | `0`, `1` or NULL
X-IT-REGISTRANT-ENTITY-TYPE | 0 | In some special cases you need to specify the exact entity type of the registrant:<br>`1`: Italian and foreign natural persons<br>`2`: Italian Companies / one man companies<br>`3`:  freelance workers / professionals <br>`4`: non-profit organizations<br>`5`: public organizations<br>`6`:  	other subjects<br>`7`: foreigners who match 2 - 6  | TEXT or NULL
X-IT-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
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
X-NAME-EMAILFORWARD | 0 | Email Address | EMAIL
X-NICSE-IDNUMBER | 0 | This number must be provided for individuals as well as for organizations. For individuals or companies located in Sweden a valid Swedish personal or organizational number must be stated (6 digits, dash, 4 digits).<br> For individuals and companies outside of Sweden the ID number (e.g. Civic registration number, company registration number, or the equivalent) can consist of 4 to 123 characters. | TEXT or NULL
X-NICSE-VATID | 0 | The VAT-ID has to be stated for companies that are located inside the European Union but outside Sweden | TEXT or NULL
X-NICSE-DISCLOSE | 0 | If set to `1` the registrant's details get disclosed | `0`, `1` or NULL
X-NL-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-NL-REGISTRANT-LEGAL-FORM | 0 | Registrant's legal form | `ANDERS`, `BGG`, `BRO`, `BV`, `COOP`, `CV`, `EENMANSZAAK`, `EESV`, `KERK`, `MAATSCHAP`, `NV`, `OWM`, `PERSOON`, `REDR`, `STICHTING`, `VERENIGING`, `VOF` or NULL
X-NL-REGISTRANT-LEGAL-FORM-REG-NO | 0 | Registrant's legal form registration number | TEXT or NULL
X-NO-REGISTRANT-IDENTITY | 0 | The organization number of the Norwegian organization (consisting of exactly 9 digits) or the PID Number in format N.PRI.12345678 | TEXT
X-NOMINET-DATA-QUALITY-LOCK | 0 | By setting this parameter to `1` it is declared that the domain registrant has been verified; only possible for repository owners | `1` or NULL
X-NYC-REGISTRANT-NEXUS-CATEGORY | 0 | The value of this parameter has to be either <br>`1` for a natural person whose primary place of domicile is a valid physical address in the City of New York or <br> `2` for an entity or organization that has a physical street address in the City of New York| `1`, `2` or NULL
X-SG-RCBID | 0 | The company registration number has to be provided with this parameter if the registrant is a organization from Singapore | TEXT or NULL
X-SG-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-UK-REG-OPT-OUT | 0 | If set to `Y`, the registrant's contact data will not be shown in the WHOIS | TEXT or NULL
X-UK-REG-TYPE | 0 | Registrant type | TEXT or NULL
X-UK-ACCEPT-TRUSTEE-TAC | 0 | Activates the trustee service | `0`, `1` or NULL
X-JOBS-TITLE | 0 | Registrant's title; only relevant for .JOBS domains | TEXT or NULL
X-JOBS-COMPANYURL | 0 | The company's URL | TEXT or NULL
X-JOBS-INDUSTRYCLASSIFICATION | 0 | Industry Classification for .JOBS | TEXT or NULL
X-JOBS-HRANAME | 0 | Human Resources Association name for .JOBS | TEXT or NULL
X-JOBS-ADMINTYPE | 0 | Set to `1` in order to indicate that the registrant is also the administrative contact of the domain; only relevant for .JOBS domains | `0`, `1` or NULL
X-TEL-WHOISTYPE | 0 | With this parameter the way the domain will be displayed in the WHOIS can be selected | `Legal`, `Natural` or NULL
X-TEL-PUBLISH | 0 | If set to `N`, the registrant's contact data will not be shown in the WHOIS | `Y`, `N` or NULL
X-US-NEXUS-APPPURPOSE | 0 | Must be one of the following:<br> `P1`: Business use for profit <br>`P2`: Non-profit business, club, association, religious organization, etc.<br>`P3`: Personal use<br> `P4`: Education purposes <br> `P5`: Government purposes | `P1`, `P2`, `P3`, `P4` or `P5`
X-US-NEXUS-CATEGORY | 0 | Must be one of the following:<br> `C11`: a United States citizen<br> `C12`: a permanent resident of the United States of America or any of its posessions or territories. <br> `C21`: U.S. Organization incorporated within one of the 50 states or a U.S. Territory An entity or organization that has a bona fide presence in the United States of America or any of its possessions or territories.<br> `C31`:  Regularly engages in lawful activities (sales of goods or services or other business, commercial or non-commercial, including not-for-profit relations in the United States) <br> `C32`: Entity has an office or other facility in the US. | `C11`, `C12`, `C21`, `C31` or `C32`
X-US-NEXUS-VALIDATOR | 0 | Specify the two-letter country-code of the registrant (if Nexus Category is either C31 or C32). | COUNTRY
X-PRO-REGISTRATIONTYPE | 0 | Type of .PRO registration | TEXT or NULL
X-PRO-REDIRECT | 0 | Can be used to enter a REDIRECT of a SecondLevelRedirecting .PRO domain to a Third-Level-Domain | TEXT or NULL
X-PRO-ACTIVATION | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | `1`, `0` or NULL
X-PRO-PW | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | TEXT or NULL
X-PRO-ROID | 0 | Necessary for the activation of a .PRO Third-Level-Resolving domain after creating an A/V record. | TEXT or NULL
X-PRO-TRADEMARKNAME | 0 | The name of the registered trademark | TEXT or NULL
X-PRO-TRADEMARKJURISDICTION | 0 | ISO-3166 Country Code of the country in which the jurisdiction for the trademark applies | COUNTRY or NULL
X-PRO-TRADEMARKDATE | 0 | The registration date of the registered trademark | TEXT or NULL
X-PRO-TRADEMARKNUMBER | 0 | The registration number of the registered trademark | TEXT or NULL
X-PT-REGISTRANT-VATID | 0 | The registrant's VAT-ID | TEXT or NULL
X-PT-ADMIN-VATID | 0 | The admin's VAT-ID | TEXT or NULL
X-PT-TECH-VATID | 0 | The technical contact's VAT-ID | TEXT or NULL
X-PT-REGISTRANT-MOBILE | 0 | Registrant's mobile number | PHONE or NULL
X-PT-TECH-MOBILE | 0 | Technical contact's mobile number | PHONE or NULL
X-SWISS-REGISTRANT-ENTERPRISE-ID | 0 | The enterprise ID, in the specific context of .swiss based on current rules, is the Swiss UID/IDE/IDI. | TEXT
X-SYDNEY-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: New South Wales Entities<br>`B`: New South Wales Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-MELBOURNE-NEXUS-CATEGORY | 0 | The registrant of the domain must one of 3 criteria:<br>`A`: Victorian Entities<br>`B`: Victorian Residents<br>`C`: Associated Entities | `A`, `B`, `C` or NULL
X-XXX-ACCEPT-REGISTRATION-TAC | 0 | Set to `1` to accept the terms and conditions | NULL, `1` or `0`
X-XXX-MEMBERSHIP-CONTACT | 0 | Contact Handle ID | CONTACT or NULL
X-XXX-NON-RESOLVING | 0 |  If you want to register a .XXX domain that should not resolve, please provide this flag upon registration | `0`, `1` or NULL
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
X-BOATS-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-ECO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-HOMES-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-VOTE-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-VOTO-ACCEPT-HIGHLY-REGULATED-TAC | 0 | Set to `1` to accept the terms and conditions of a highly regulated TLD | `1` or NULL
X-REGULATORY-BODY-CONTACT-EMAIL | 0 | Email Address | EMAIL or NULL
X-REGULATORY-BODY-CONTACT-PHONE | 0 | ITU Phone Number | PHONE or NULL
X-ACCEPT-WHOISTRUSTEE-TAC | 0 | Activates the Whois Trustee Service | `0`, `1` or NULL
X-ACCEPT-WHOISTRUSTEELITE-TAC | 0 | Activates the Whois Trustee Service Lite | `0`, `1` or NULL
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
INTERNALDNS | 0 | Creates the necessary dns zone before submitting update request to the registry. | `0`, `1` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
506 | Invalid option value
507 | Invalid command format
510 | Command not supported for this class
521 | Too many sessions open. Server closing connection
530 | Authentication failed
531 | Authorization failed
532 | Domain names linked with name server
536 | Object already flagged for transfer
540 | Attribute value is not unique
541 | Invalid attribute value
543 | Final or implicit attribute cannot be updated
544 | Entity on hold
545 | Object not found
546 | Credit limit exceeded
547 | Invalid command sequence
549 | Command Failed
552 | Object status does not allow for operation
553 | Operation not allowed. Object pending transfer

NOTE: The response might include the parameter 'PENDING = 1'. This indicates that the update request has not been completed yet and that it might still get rejected.

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
STATUS | 0 | 1 | The current update status in case the update has not been completed yet | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyDomain
ADMINCONTACT0 = P-TUE1378125
DOMAIN = hexonet-domain.com
NAMESERVER0 = ns1.ispapi.net
NAMESERVER1 = ns2.ispapi.net
NAMESERVER2 = ns3.ispapi.net
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
EOF
```

----
