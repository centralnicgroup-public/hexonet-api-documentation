# CreateSSLCert

## DESCRIPTION
Order an SSL certificate.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateSSLCert` | COMMAND
ORDER | 0 | SSL certificate ordering order action:<br>`CREATE` - create an SSL certificate ordering order<br>`REPLACE` - replace an SSL certificate ordering order<br>`UPDATE` - update an SSL certificate ordering order | `CREATE`, `REPLACE` or `UPDATE`
ORDERID | 0 | ID of the order; only relevant if ORDER is `REPLACE` or `UPDATE` | INT
SSLCERTCLASS | 1 | Choose the type of product, possible values:<br>`COMODO_INSTANTSSL`<br>`COMODO_INSTANTSSLPRO`<br>`COMODO_EVSSL`<br>`COMODO_PREMIUMSSL`<br>`COMODO_ESSENTIALSSL`<br>`COMODO_UCC`<br>`COMODO_WILDCARDSSL`<br>`THAWTE_SSL123`<br>`THAWTE_SSLWEBSERVER`<br>`THAWTE_SSLWEBSERVEREV`<br>`SYMANTEC_SECURESITE`<br>`SYMANTEC_SECUREDITEPRO`<br>`SYMANTEC_SECURESITEEV`<br>`SYMANTEC_SECURESITEPROEV`<br>`GEOTRUST_QUICKSSLPREMIUM`<br>`GEOTRUST_RAPIDSSL`<br>`GEOTRUST_RAPIDSSL_WILDCARD` | TEXT
SSLCERTDOMAIN | 0 | Domain name for which the SSL certificate is ordered; must be the same as the Common Name (CN) of the CSR if provided | TEXT or NULL
PERIOD | 0 | Validity period in years; the default is: `1` | INT
CSR[0..N] | 0 | The certificate signing request (CSR) in base64 encoding line by line | TEXT or NULL
ALTERNATECN[0..N] | 0 | Subject Alternative Names; must match the SAN field of the CSR if provided | TEXT or NULL
OWNERCONTACT[0..4] | 0 | Applicant contact handle | CONTACT or NULL
ADMINCONTACT[0..2] | 0 | Admin contact handle | CONTACT or NULL
TECHCONTACT[0..2] | 0 | Tech contact handle | CONTACT or NULL
BILLINGCONTACT[0..2] | 0 | Billing contact handle | CONTACT or NULL
CSRCONTACT0 | 0 | CSR contact handle; contact data will be used for the creation of a CSR; only relevant if no CSR is provided | CONTACT or NULL
CSRCONTACT0TITLE | 0 | CSR contact job title or position within the company | TEXT or NULL
CSRCONTACT0NAME | 0 | CSR contact full name (FIRSTNAME LASTNAME) | TEXT or NULL
CSRCONTACT0FIRSTNAME | 0 | CSR contact first name | TEXT or NULL
CSRCONTACT0MIDDLENAME | 0 | CSR contact middle name | TEXT or NULL
CSRCONTACT0LASTNAME | 0 | CSR contact last name | TEXT or NULL
CSRCONTACT0ORGANIZATION | 0 | CSR contact organization name | TEXT or NULL
CSRCONTACT0STREET | 0 | CSR contact address street | TEXT or NULL
CSRCONTACT0CITY | 0 | CSR contact address city | TEXT or NULL
CSRCONTACT0STATE | 0 | CSR contact address state / province | TEXT or NULL
CSRCONTACT0ZIP | 0 | CSR contact address postal code | TEXT or NULL
CSRCONTACT0COUNTRY | 0 | CSR contact address country code | TEXT or NULL
CSRCONTACT0PHONE | 0 | CSR contact phone number | TEXT or NULL
CSRCONTACT0FAX | 0 | CSR contact fax number | TEXT or NULL
CSRCONTACT0EMAIL | 0 | CSR contact email address | EMAIL or NULL
DOMAIN[0..N] | 0 | Domain name(s) for which the SSL certificate is ordered; must be the same as the Common Name (CN) plus the Subject Alternative Names (SANs) of the CSR if provided | TEXT or NULL
VALIDATION[0..N] | 0 | Domain control validation method; can be `DNSZONE`, `EMAIL`, `URL`; the default is: `EMAIL` | TEXT or NULL
VALIDATIONEMAIL[0..N] | 0 | Email address the domain control validation email is supposed to be sent to; only relevant if the validation method is `EMAIL`; if omitted the email address of the applicant is used | TEXT or NULL
PEM[0..N] | 0 | Private key in PEM format; will be used for the creation of a CSR; only relevant if no CSR is provided | TEXT or NULL
KEYLENGTH | 0 | Key length of the private key that will be automatically created; must be between `2048` and `8192`; only relevant if no private key and no CSR are provided | INT or NULL
INTERNALDNS | 0 | Creates the DNS zone necessary for DNS based domain control validation;  only relevant if the validation method is `DNSZONE` | `0`, `1` or NULL

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
507 | Invalid command format
530 | Authentication failed
540 | Attribute value is not unique
541 | Invalid attribute value
546 | Credit limit exceeded
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ADMINCONTACT0CITY | 0 | 1 | Admin contact address city | TEXT
ADMINCONTACT0COUNTRY | 0 | 1 | Admin contact address country code | COUNTRY
ADMINCONTACT0EMAIL | 0 | 1 | Admin contact email address | EMAIL
ADMINCONTACT0FAX | 0 | 1 | Admin contact fax number | TEXT
ADMINCONTACT0FIRSTNAME | 0 | 1 | Admin contact first name | TEXT
ADMINCONTACT0LASTNAME | 0 | 1 | Admin contact last name | TEXT
ADMINCONTACT0MIDDLENAME | 0 | 1 | Admin contact middle name | TEXT
ADMINCONTACT0NAME | 0 | 1 | Admin contact full name | TEXT
ADMINCONTACT0ORGANIZATION | 0 | 1 | Admin contact organization name | TEXT
ADMINCONTACT0PHONE | 0 | 1 | Admin contact phone number | TEXT
ADMINCONTACT0STATE | 0 | 1 | Admin contact address state / province | TEXT
ADMINCONTACT0STREET | 0 | 1 | Admin contact address street | TEXT
ADMINCONTACT0TITLE | 0 | 1 | Admin contact job title or position within the company | TEXT
ADMINCONTACT0ZIP | 0 | 1 | Admin contact address postal code | TEXT
ADMINCONTACT1CITY | 0 | 1 | Admin contact address city | TEXT
ADMINCONTACT1COUNTRY | 0 | 1 | Admin contact address country code | COUNTRY
ADMINCONTACT1EMAIL | 0 | 1 | Admin contact email address | EMAIL
ADMINCONTACT1FAX | 0 | 1 | Admin contact fax number | TEXT
ADMINCONTACT1FIRSTNAME | 0 | 1 | Admin contact first name | TEXT
ADMINCONTACT1LASTNAME | 0 | 1 | Admin contact last name | TEXT
ADMINCONTACT1MIDDLENAME | 0 | 1 | Admin contact middle name | TEXT
ADMINCONTACT1NAME | 0 | 1 | Admin contact full name | TEXT
ADMINCONTACT1ORGANIZATION | 0 | 1 | Admin contact organization name | TEXT
ADMINCONTACT1PHONE | 0 | 1 | Admin contact phone number | TEXT
ADMINCONTACT1STATE | 0 | 1 | Admin contact address state / province | TEXT
ADMINCONTACT1STREET | 0 | 1 | Admin contact address street | TEXT
ADMINCONTACT1TITLE | 0 | 1 | Admin contact job title or position within the company | TEXT
ADMINCONTACT1ZIP | 0 | 1 | Admin contact address postal code | TEXT
ADMINCONTACT2CITY | 0 | 1 | Admin contact address city | TEXT
ADMINCONTACT2COUNTRY | 0 | 1 | Admin contact address country code | COUNTRY
ADMINCONTACT2EMAIL | 0 | 1 | Admin contact email address | EMAIL
ADMINCONTACT2FAX | 0 | 1 | Admin contact fax number | TEXT
ADMINCONTACT2FIRSTNAME | 0 | 1 | Admin contact first name | TEXT
ADMINCONTACT2LASTNAME | 0 | 1 | Admin contact last name | TEXT
ADMINCONTACT2MIDDLENAME | 0 | 1 | Admin contact middle name | TEXT
ADMINCONTACT2NAME | 0 | 1 | Admin contact full name | TEXT
ADMINCONTACT2ORGANIZATION | 0 | 1 | Admin contact organization name | TEXT
ADMINCONTACT2PHONE | 0 | 1 | Admin contact phone number | TEXT
ADMINCONTACT2STATE | 0 | 1 | Admin contact address state / province | TEXT
ADMINCONTACT2STREET | 0 | 1 | Admin contact address street | TEXT
ADMINCONTACT2TITLE | 0 | 1 | Admin contact job title or position within the company | TEXT
ADMINCONTACT2ZIP | 0 | 1 | Admin contact address postal code | TEXT
ALTERNATECN[0..N] | 0 | N | Subject Alternative Names | TEXT
BILLINGCONTACT0CITY | 0 | 1 | Billing contact address city | TEXT
BILLINGCONTACT0COUNTRY | 0 | 1 | Billing contact address country code | COUNTRY
BILLINGCONTACT0EMAIL | 0 | 1 | Billing contact email address | EMAIL
BILLINGCONTACT0FAX | 0 | 1 | Billing contact fax number | TEXT
BILLINGCONTACT0FIRSTNAME | 0 | 1 | Billing contact first name | TEXT
BILLINGCONTACT0LASTNAME | 0 | 1 | Billing contact last name | TEXT
BILLINGCONTACT0MIDDLENAME | 0 | 1 | Billing contact middle name | TEXT
BILLINGCONTACT0NAME | 0 | 1 | Billing contact full name | TEXT
BILLINGCONTACT0ORGANIZATION | 0 | 1 | Billing contact organization name | TEXT
BILLINGCONTACT0PHONE | 0 | 1 | Billing contact phone number | TEXT
BILLINGCONTACT0STATE | 0 | 1 | Billing contact address state / province | TEXT
BILLINGCONTACT0STREET | 0 | 1 | Billing contact address street | TEXT
BILLINGCONTACT0TITLE | 0 | 1 | Billing contact job title or position within the company | TEXT
BILLINGCONTACT0ZIP | 0 | 1 | Billing contact address postal code | TEXT
BILLINGCONTACT1CITY | 0 | 1 | Billing contact address city | TEXT
BILLINGCONTACT1COUNTRY | 0 | 1 | Billing contact address country code | COUNTRY
BILLINGCONTACT1EMAIL | 0 | 1 | Billing contact email address | EMAIL
BILLINGCONTACT1FAX | 0 | 1 | Billing contact fax number | TEXT
BILLINGCONTACT1FIRSTNAME | 0 | 1 | Billing contact first name | TEXT
BILLINGCONTACT1LASTNAME | 0 | 1 | Billing contact last name | TEXT
BILLINGCONTACT1MIDDLENAME | 0 | 1 | Billing contact middle name | TEXT
BILLINGCONTACT1NAME | 0 | 1 | Billing contact full name | TEXT
BILLINGCONTACT1ORGANIZATION | 0 | 1 | Billing contact organization name | TEXT
BILLINGCONTACT1PHONE | 0 | 1 | Billing contact phone number | TEXT
BILLINGCONTACT1STATE | 0 | 1 | Billing contact address state / province | TEXT
BILLINGCONTACT1STREET | 0 | 1 | Billing contact address street | TEXT
BILLINGCONTACT1TITLE | 0 | 1 | Billing contact job title or position within the company | TEXT
BILLINGCONTACT1ZIP | 0 | 1 | Billing contact address postal code | TEXT
BILLINGCONTACT2CITY | 0 | 1 | Billing contact address city | TEXT
BILLINGCONTACT2COUNTRY | 0 | 1 | Billing contact address country code | COUNTRY
BILLINGCONTACT2EMAIL | 0 | 1 | Billing contact email address | EMAIL
BILLINGCONTACT2FAX | 0 | 1 | Billing contact fax number | TEXT
BILLINGCONTACT2FIRSTNAME | 0 | 1 | Billing contact first name | TEXT
BILLINGCONTACT2LASTNAME | 0 | 1 | Billing contact last name | TEXT
BILLINGCONTACT2MIDDLENAME | 0 | 1 | Billing contact middle name | TEXT
BILLINGCONTACT2NAME | 0 | 1 | Billing contact full name | TEXT
BILLINGCONTACT2ORGANIZATION | 0 | 1 | Billing contact organization name | TEXT
BILLINGCONTACT2PHONE | 0 | 1 | Billing contact phone number | TEXT
BILLINGCONTACT2STATE | 0 | 1 | Billing contact address state / province | TEXT
BILLINGCONTACT2STREET | 0 | 1 | Billing contact address street | TEXT
BILLINGCONTACT2TITLE | 0 | 1 | Billing contact job title or position within the company | TEXT
BILLINGCONTACT2ZIP | 0 | 1 | Billing contact address postal code | TEXT
CITY | 0 | 1 | Default contact address city | TEXT or NULL
CN | 0 | 1 | Common Name | TEXT
COUNTRY | 0 | 1 | Default contact address country code | COUNTRY or NULL
CREATEDBY | 0 | 1 | Registrar that ordered the SSL certificate | TEXT
CREATEDDATE | 0 | 1 | Order date of the SSL certificate order | DATETIME
CSR[0..N] | 0 | N | Certificate signing request | TEXT
CSRCONTACT0CITY | 0 | 1 | CSR contact address city | TEXT
CSRCONTACT0COUNTRY | 0 | 1 | CSR contact address country code | COUNTRY
CSRCONTACT0EMAIL | 0 | 1 | CSR contact email address | EMAIL
CSRCONTACT0FAX | 0 | 1 | CSR contact fax number | TEXT
CSRCONTACT0FIRSTNAME | 0 | 1 | CSR contact first name | TEXT
CSRCONTACT0LASTNAME | 0 | 1 | CSR contact last name | TEXT
CSRCONTACT0ORGANIZATION | 0 | 1 | CSR contact organization name | TEXT
CSRCONTACT0PHONE | 0 | 1 | CSR contact phone number | TEXT
CSRCONTACT0STATE | 0 | 1 | CSR contact address state / province | TEXT
CSRCONTACT0STREET | 0 | 1 | CSR contact address street | TEXT
CSRCONTACT0TITLE | 0 | 1 | CSR contact job title or position within the company | TEXT
CSRCONTACT0ZIP | 0 | 1 | CSR contact address postal code | TEXT
CSRORGANIZATION | 0 | 1 | Organization name stated in the CSR | TEXT
DELETIONHOLDPERIOD | 0 | 1 | Depreciated property | TEXT or NULL
DELETIONRESTORABLEPERIOD | 0 | 1 | Depreciated property | TEXT or NULL
DOMAIN[0..N] | 0 | N | Domain name(s) for which the SSL certificate was ordered | TEXT
DOMAINCOUNT | 0 | 1 | Number of domain names for which the SSL certificate was ordered | INT
EMAIL | 0 | 1 | Default contact email address | EMAIL or NULL
EXPIRATIONDATE | 1 | 1 | The expiration date of the ordered SSL certificate | DATETIME
FAX | 0 | 1 | Default contact fax number | TEXT or NULL
FIRSTNAME | 0 | 1 | Default contact first name | TEXT or NULL
INTERNALDNS | 0 | 1 | Indicates that if necessary DNS zone for DNS based domain control validation was created | `0`, `1` or NULL
JOBTITLE | 0 | 1 | Default contact job title or position within the company | TEXT or NULL
KEYLENGTH | 0 | 1 | Key length of private key; only present if a private key was provided or automatically created | INT or NULL
LASTNAME | 0 | 1 | Default contact last name | TEXT or NULL
ORDERDATA | 0 | 1 | SSL certificate ID | TEXT
ORDERREFERENCE | 0 | 1 | SSL certificate order number | TEXT
ORGANIZATION | 0 | 1 | Default contact organization name | TEXT
OWNERCONTACT0CITY | 0 | 1 | Applicant address city | TEXT
OWNERCONTACT0COUNTRY | 0 | 1 | Applicant address country code | COUNTRY
OWNERCONTACT0EMAIL | 0 | 1 | Applicant email address | EMAIL
OWNERCONTACT0FAX | 0 | 1 | Applicant fax number | TEXT
OWNERCONTACT0FIRSTNAME | 0 | 1 | Applicant first name | TEXT
OWNERCONTACT0LASTNAME | 0 | 1 | Applicant last name | TEXT
OWNERCONTACT0MIDDLENAME | 0 | 1 | Applicant middle name | TEXT
OWNERCONTACT0NAME | 0 | 1 | Applicant full name | TEXT
OWNERCONTACT0ORGANIZATION | 0 | 1 | Applicant organization name | TEXT
OWNERCONTACT0PHONE | 0 | 1 | Applicant phone number | TEXT
OWNERCONTACT0STATE | 0 | 1 | Applicant address state / province | TEXT
OWNERCONTACT0STREET | 0 | 1 | Applicant address street | TEXT
OWNERCONTACT0TITLE | 0 | 1 | Applicant job title or position within the company | TEXT
OWNERCONTACT0ZIP | 0 | 1 | Applicant address postal code | TEXT
OWNERCONTACT1CITY | 0 | 1 | Applicant address city | TEXT
OWNERCONTACT1COUNTRY | 0 | 1 | Applicant address country code | COUNTRY
OWNERCONTACT1EMAIL | 0 | 1 | Applicant email address | EMAIL
OWNERCONTACT1FAX | 0 | 1 | Applicant fax number | TEXT
OWNERCONTACT1FIRSTNAME | 0 | 1 | Applicant first name | TEXT
OWNERCONTACT1LASTNAME | 0 | 1 | Applicant last name | TEXT
OWNERCONTACT1MIDDLENAME | 0 | 1 | Applicant middle name | TEXT
OWNERCONTACT1NAME | 0 | 1 | Applicant full name | TEXT
OWNERCONTACT1ORGANIZATION | 0 | 1 | Applicant organization name | TEXT
OWNERCONTACT1PHONE | 0 | 1 | Applicant phone number | TEXT
OWNERCONTACT1STATE | 0 | 1 | Applicant address state / province | TEXT
OWNERCONTACT1STREET | 0 | 1 | Applicant address street | TEXT
OWNERCONTACT1TITLE | 0 | 1 | Applicant job title or position within the company | TEXT
OWNERCONTACT1ZIP | 0 | 1 | Applicant address postal code | TEXT
OWNERCONTACT2CITY | 0 | 1 | Applicant address city | TEXT
OWNERCONTACT2COUNTRY | 0 | 1 | Applicant address country code | COUNTRY
OWNERCONTACT2EMAIL | 0 | 1 | Applicant email address | EMAIL
OWNERCONTACT2FAX | 0 | 1 | Applicant fax number | TEXT
OWNERCONTACT2FIRSTNAME | 0 | 1 | Applicant first name | TEXT
OWNERCONTACT2LASTNAME | 0 | 1 | Applicant last name | TEXT
OWNERCONTACT2MIDDLENAME | 0 | 1 | Applicant middle name | TEXT
OWNERCONTACT2NAME | 0 | 1 | Applicant full name | TEXT
OWNERCONTACT2ORGANIZATION | 0 | 1 | Applicant organization name | TEXT
OWNERCONTACT2PHONE | 0 | 1 | Applicant phone number | TEXT
OWNERCONTACT2STATE | 0 | 1 | Applicant address state / province | TEXT
OWNERCONTACT2STREET | 0 | 1 | Applicant address street | TEXT
OWNERCONTACT2TITLE | 0 | 1 | Applicant job title or position within the company | TEXT
OWNERCONTACT2ZIP | 0 | 1 | Applicant address postal code | TEXT
OWNERCONTACT3CITY | 0 | 1 | Applicant address city | TEXT
OWNERCONTACT3COUNTRY | 0 | 1 | Applicant address country code | COUNTRY
OWNERCONTACT3EMAIL | 0 | 1 | Applicant email address | EMAIL
OWNERCONTACT3FAX | 0 | 1 | Applicant fax number | TEXT
OWNERCONTACT3FIRSTNAME | 0 | 1 | Applicant first name | TEXT
OWNERCONTACT3LASTNAME | 0 | 1 | Applicant last name | TEXT
OWNERCONTACT3MIDDLENAME | 0 | 1 | Applicant middle name | TEXT
OWNERCONTACT3NAME | 0 | 1 | Applicant full name | TEXT
OWNERCONTACT3ORGANIZATION | 0 | 1 | Applicant organization name | TEXT
OWNERCONTACT3PHONE | 0 | 1 | Applicant phone number | TEXT
OWNERCONTACT3STATE | 0 | 1 | Applicant address state / province | TEXT
OWNERCONTACT3STREET | 0 | 1 | Applicant address street | TEXT
OWNERCONTACT3TITLE | 0 | 1 | Applicant job title or position within the company | TEXT
OWNERCONTACT3ZIP | 0 | 1 | Applicant address postal code | TEXT
OWNERCONTACT4CITY | 0 | 1 | Applicant address city | TEXT
OWNERCONTACT4COUNTRY | 0 | 1 | Applicant address country code | COUNTRY
OWNERCONTACT4EMAIL | 0 | 1 | Applicant email address | EMAIL
OWNERCONTACT4FAX | 0 | 1 | Applicant fax number | TEXT
OWNERCONTACT4FIRSTNAME | 0 | 1 | Applicant first name | TEXT
OWNERCONTACT4LASTNAME | 0 | 1 | Applicant last name | TEXT
OWNERCONTACT4MIDDLENAME | 0 | 1 | Applicant middle name | TEXT
OWNERCONTACT4NAME | 0 | 1 | Applicant full name | TEXT
OWNERCONTACT4ORGANIZATION | 0 | 1 | Applicant organization name | TEXT
OWNERCONTACT4PHONE | 0 | 1 | Applicant phone number | TEXT
OWNERCONTACT4STATE | 0 | 1 | Applicant address state / province | TEXT
OWNERCONTACT4STREET | 0 | 1 | Applicant address street | TEXT
OWNERCONTACT4TITLE | 0 | 1 | Applicant job title or position within the company | TEXT
OWNERCONTACT4ZIP | 0 | 1 | Applicant address postal code | TEXT
PEERUSER | 0 | 1 | String with all users in the user chain | TEXT
PEM[0..N] | 0 | N | Private key; only present if a private key was provided or automatically created | TEXT
PHONE | 0 | 1 | Default contact phone number | TEXT or NULL
PROVINCE | 0 | 1 | Default contact address state / province | TEXT
REGISTRAR | 0 | 1 | Current sponsoring registrar | TEXT
REGISTRATIONEXPIRATIONDATE | 1 | 1 | The expiration date of the ordered SSL certificate | DATETIME
REGISTRATIONGRACEPERIOD | 0 | 1 | Registration grace period | TEXT
RENEWALACCOUNTINGPERIOD | 0 | 1 | Renewal accounting period | TEXT
RENEWALFAILUREPERIOD | 0 | 1 | Renewal failure period | TEXT
RENEWALFINALIZATIONPERIOD | 0 | 1 | Renewal finalization period | TEXT
REVISION | 0 | 1 | Depreciated property | TEXT or NULL
SERVERSOFTWARE | 0 | 1 | Web server software | TEXT
SLOTTYPE | 0 | 1 | Depreciated property | TEXT or NULL
SSLCERTCLASS | 1 | 1 | Product type | TEXT
SSLCERTCN | 0 | 1 | Common Name | TEXT
SSLCERTDOMAIN | 0 | 1 | Domain name for which the SSL certificate was ordered | TEXT
STATUS | 1 | 1 | SSL certificate status | TEXT
STATUSDETAILS | 0 | 1 | Additional status information | TEXT or NULL
STREET | 0 | 1 | Default contact address street | TEXT or NULL
TECHCONTACT0CITY | 0 | 1 | Tech contact address city | TEXT
TECHCONTACT0COUNTRY | 0 | 1 | Tech contact address country code | COUNTRY
TECHCONTACT0EMAIL | 0 | 1 | Tech contact email address | EMAIL
TECHCONTACT0FAX | 0 | 1 | Tech contact fax number | TEXT
TECHCONTACT0FIRSTNAME | 0 | 1 | Tech contact first name | TEXT
TECHCONTACT0LASTNAME | 0 | 1 | Tech contact last name | TEXT
TECHCONTACT0MIDDLENAME | 0 | 1 | Tech contact middle name | TEXT
TECHCONTACT0NAME | 0 | 1 | Tech contact full name | TEXT
TECHCONTACT0ORGANIZATION | 0 | 1 | Tech contact organization name | TEXT
TECHCONTACT0PHONE | 0 | 1 | Tech contact phone number | TEXT
TECHCONTACT0STATE | 0 | 1 | Tech contact address state / province | TEXT
TECHCONTACT0STREET | 0 | 1 | Tech contact address street | TEXT
TECHCONTACT0TITLE | 0 | 1 | Tech contact job title or position within the company | TEXT
TECHCONTACT0ZIP | 0 | 1 | Tech contact address postal code | TEXT
TECHCONTACT1CITY | 0 | 1 | Tech contact address city | TEXT
TECHCONTACT1COUNTRY | 0 | 1 | Tech contact address country code | COUNTRY
TECHCONTACT1EMAIL | 0 | 1 | Tech contact email address | EMAIL
TECHCONTACT1FAX | 0 | 1 | Tech contact fax number | TEXT
TECHCONTACT1FIRSTNAME | 0 | 1 | Tech contact first name | TEXT
TECHCONTACT1LASTNAME | 0 | 1 | Tech contact last name | TEXT
TECHCONTACT1MIDDLENAME | 0 | 1 | Tech contact middle name | TEXT
TECHCONTACT1NAME | 0 | 1 | Tech contact full name | TEXT
TECHCONTACT1ORGANIZATION | 0 | 1 | Tech contact organization name | TEXT
TECHCONTACT1PHONE | 0 | 1 | Tech contact phone number | TEXT
TECHCONTACT1STATE | 0 | 1 | Tech contact address state / province | TEXT
TECHCONTACT1STREET | 0 | 1 | Tech contact address street | TEXT
TECHCONTACT1TITLE | 0 | 1 | Tech contact job title or position within the company | TEXT
TECHCONTACT1ZIP | 0 | 1 | Tech contact address postal code | TEXT
TECHCONTACT2CITY | 0 | 1 | Tech contact address city | TEXT
TECHCONTACT2COUNTRY | 0 | 1 | Tech contact address country code | COUNTRY
TECHCONTACT2EMAIL | 0 | 1 | Tech contact email address | EMAIL
TECHCONTACT2FAX | 0 | 1 | Tech contact fax number | TEXT
TECHCONTACT2FIRSTNAME | 0 | 1 | Tech contact first name | TEXT
TECHCONTACT2LASTNAME | 0 | 1 | Tech contact last name | TEXT
TECHCONTACT2MIDDLENAME | 0 | 1 | Tech contact middle name | TEXT
TECHCONTACT2NAME | 0 | 1 | Tech contact full name | TEXT
TECHCONTACT2ORGANIZATION | 0 | 1 | Tech contact organization name | TEXT
TECHCONTACT2PHONE | 0 | 1 | Tech contact phone number | TEXT
TECHCONTACT2STATE | 0 | 1 | Tech contact address state / province | TEXT
TECHCONTACT2STREET | 0 | 1 | Tech contact address street | TEXT
TECHCONTACT2TITLE | 0 | 1 | Tech contact job title or position within the company | TEXT
TECHCONTACT2ZIP | 0 | 1 | Tech contact address postal code | TEXT
UPDATEDBY | 0 | 1 | Registrar that updated the SSL certificate | TEXT
UPDATEDDATE | 0 | 1 | Last modification date of the SSL certificate | DATETIME
USER | 0 | 1 | The user that manages this SSL certificate | TEXT
VALIDATION[0..N] | 0 | N | Domain control validation method | TEXT
VALIDATIONDNSRR[0..N] | 0 | N | Domain control validation DNS Resource Record; only relevant if the domain control validation method is `DNSZONE` | TEXT or NULL
VALIDATIONEMAIL[0..N] | 0 | N | Email address the domain control validation email will be sent to; only relevant if the validation method is `EMAIL` | TEXT or NULL
VALIDATIONURL[0..N] | 0 | N | Domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL
VALIDATIONURLCONTENT[0..N] | 0 | N | Expected content at domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL
ZIP | 0 | 1 | Default contact address postal code | TEXT or NULL



----
## Example

### Command

```
[COMMAND]
COMMAND = CreateSSLCert
ADMINCONTACT0 = P-FCZ28558
BILLINGCONTACT0 = P-FCZ28558
CSR0 = -----BEGIN CERTIFICATE REQUEST-----
CSR1 = MIICujCCAaICAQAwdTELMAkGA1UEBhMCREUxCzAJBgNVBAgMAlNMMRAwDgYDVQQH
CSR2 = DAdIb21idXJnMRAwDgYDVQQKDAdIRVhPTkVUMRQwEgYDVQQDDAtoZXhvbmV0Lm5l
CSR3 = dDEfMB0GCSqGSIb3DQEJARYQaW5mb0BoZXhvbmV0Lm5ldDCCASIwDQYJKoZIhvcN
CSR4 = AQEBBQADggEPADCCAQoCggEBAKd2gnSWxH60JCeW4VrzNVIkKfuUgm/Fw/NoyAnT
CSR5 = ruJMwqU4hEWDyD9ynwtcZgrw4MLDg56obSt1i+9C+2Far8HhqnywjSWWaypi7H/2
CSR6 = gPfL3hl7Kab7PJJpgqWOH91mLmfDVSbbZ36w4PUwDlB6twluY/QSgyG2VN9KW2HK
CSR7 = GYOEpDs1Dp7mi8kS6ZLo1r8VTmKh6wtFhN5l8fSFC2f4E9x7r/hO9dn4vu9HobF2
CSR8 = ep+qX12p0nl+wS/JnnJWGTppfEhCszWvTBFnERtZ1jEvwK/iok/PnOJSj4XZyUsB
CSR9 = 3A96iys/TiNdOgVBoBTT3A4518Y5GVUeXUWQ7JwR5DTIiYMCAwEAAaAAMA0GCSqG
CSR10 = SIb3DQEBCwUAA4IBAQB3w7R+qam9ePMjEC5dACfs252/cA2MDBo5XHrldlT7JNye
CSR11 = DuAo7/rHuDK+5oXJWJSM94QFdaZg0l8CVpsW19YauUZ6JbwFimyU5a4LzaMJGEiE
CSR12 = LXkJUgpZV4aJtX28A8+avMX6GozjdLo6u+wnoSrTNq2WIyjz5TGT98EuVznFjgOk
CSR13 = YvVdszR/w6V0bB7DtktGKnhLE+J4wbosP2jIp+IbFgMAz6jBRKExzEmd5BAIATgP
CSR14 = 9gjF9oQ8P7jJOMdCAZoUVuyx5tTzw3ZXhlaocUD8JEw3eFZGy+n0NNWazRB3Fd7+
CSR15 = NpPNajDGktgRMzMQQEqS53kGM4ZLiOVV9kNSXete
CSR16 = -----END CERTIFICATE REQUEST-----
DOMAIN0 = hexonet.net
OWNERCONTACT0 = P-FCZ28558
PERIOD = 1
SERVERSOFTWARE = APACHESSL
SSLCERTCLASS = COMODO_ESSENTIALSSL
TECHCONTACT0 = P-FCZ28558
VALIDATION0 = EMAIL
VALIDATIONEMAIL0 = info@hexonet.net
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ADMINCONTACT0CITY][0] = Test City
PROPERTY[ADMINCONTACT0COUNTRY][0] = DE
PROPERTY[ADMINCONTACT0EMAIL][0] = nomail@test.com
PROPERTY[ADMINCONTACT0FIRSTNAME][0] = Mister
PROPERTY[ADMINCONTACT0LASTNAME][0] = Test
PROPERTY[ADMINCONTACT0NAME][0] = Mister Test
PROPERTY[ADMINCONTACT0ORGANIZATION][0] = Test Organisation
PROPERTY[ADMINCONTACT0PHONE][0] = +49.123456789
PROPERTY[ADMINCONTACT0STREET][0] = Test street 123
PROPERTY[ADMINCONTACT0ZIP][0] = 12345
PROPERTY[BILLINGCONTACT0CITY][0] = Test City
PROPERTY[BILLINGCONTACT0COUNTRY][0] = DE
PROPERTY[BILLINGCONTACT0EMAIL][0] = nomail@test.com
PROPERTY[BILLINGCONTACT0FIRSTNAME][0] = Mister
PROPERTY[BILLINGCONTACT0LASTNAME][0] = Test
PROPERTY[BILLINGCONTACT0NAME][0] = Mister Test
PROPERTY[BILLINGCONTACT0ORGANIZATION][0] = Test Organisation
PROPERTY[BILLINGCONTACT0PHONE][0] = +49.123456789
PROPERTY[BILLINGCONTACT0STREET][0] = Test street 123
PROPERTY[BILLINGCONTACT0ZIP][0] = 12345
PROPERTY[CITY][0] =
PROPERTY[CN][0] = hexonet.net
PROPERTY[COUNTRY][0] =
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-11-02 10:53:28
PROPERTY[CSR][0] = -----BEGIN CERTIFICATE REQUEST-----
PROPERTY[CSR][1] = MIICujCCAaICAQAwdTELMAkGA1UEBhMCREUxCzAJBgNVBAgMAlNMMRAwDgYDVQQH
PROPERTY[CSR][2] = DAdIb21idXJnMRAwDgYDVQQKDAdIRVhPTkVUMRQwEgYDVQQDDAtoZXhvbmV0Lm5l
PROPERTY[CSR][3] = dDEfMB0GCSqGSIb3DQEJARYQaW5mb0BoZXhvbmV0Lm5ldDCCASIwDQYJKoZIhvcN
PROPERTY[CSR][4] = AQEBBQADggEPADCCAQoCggEBAKd2gnSWxH60JCeW4VrzNVIkKfuUgm/Fw/NoyAnT
PROPERTY[CSR][5] = ruJMwqU4hEWDyD9ynwtcZgrw4MLDg56obSt1i+9C+2Far8HhqnywjSWWaypi7H/2
PROPERTY[CSR][6] = gPfL3hl7Kab7PJJpgqWOH91mLmfDVSbbZ36w4PUwDlB6twluY/QSgyG2VN9KW2HK
PROPERTY[CSR][7] = GYOEpDs1Dp7mi8kS6ZLo1r8VTmKh6wtFhN5l8fSFC2f4E9x7r/hO9dn4vu9HobF2
PROPERTY[CSR][8] = ep+qX12p0nl+wS/JnnJWGTppfEhCszWvTBFnERtZ1jEvwK/iok/PnOJSj4XZyUsB
PROPERTY[CSR][9] = 3A96iys/TiNdOgVBoBTT3A4518Y5GVUeXUWQ7JwR5DTIiYMCAwEAAaAAMA0GCSqG
PROPERTY[CSR][10] = SIb3DQEBCwUAA4IBAQB3w7R+qam9ePMjEC5dACfs252/cA2MDBo5XHrldlT7JNye
PROPERTY[CSR][11] = DuAo7/rHuDK+5oXJWJSM94QFdaZg0l8CVpsW19YauUZ6JbwFimyU5a4LzaMJGEiE
PROPERTY[CSR][12] = LXkJUgpZV4aJtX28A8+avMX6GozjdLo6u+wnoSrTNq2WIyjz5TGT98EuVznFjgOk
PROPERTY[CSR][13] = YvVdszR/w6V0bB7DtktGKnhLE+J4wbosP2jIp+IbFgMAz6jBRKExzEmd5BAIATgP
PROPERTY[CSR][14] = 9gjF9oQ8P7jJOMdCAZoUVuyx5tTzw3ZXhlaocUD8JEw3eFZGy+n0NNWazRB3Fd7+
PROPERTY[CSR][15] = NpPNajDGktgRMzMQQEqS53kGM4ZLiOVV9kNSXete
PROPERTY[CSR][16] = -----END CERTIFICATE REQUEST-----
PROPERTY[CSRORGANIZATION][0] = HEXONET
PROPERTY[DELETIONHOLDPERIOD][0] =
PROPERTY[DELETIONRESTORABLEPERIOD][0] =
PROPERTY[DOMAIN][0] = hexonet.net
PROPERTY[DOMAINCOUNT][0] = 1
PROPERTY[EMAIL][0] =
PROPERTY[EXPIRATIONDATE][0] = 2017-11-02 10:53:28
PROPERTY[FAX][0] =
PROPERTY[FIRSTNAME][0] =
PROPERTY[JOBTITLE][0] =
PROPERTY[LASTNAME][0] =
PROPERTY[ORDERDATA][0] = 2870930343
PROPERTY[ORDERREFERENCE][0] = 31046590
PROPERTY[ORGANIZATION][0] =
PROPERTY[OWNERCONTACT0CITY][0] = Test City
PROPERTY[OWNERCONTACT0COUNTRY][0] = DE
PROPERTY[OWNERCONTACT0EMAIL][0] = nomail@test.com
PROPERTY[OWNERCONTACT0FIRSTNAME][0] = Mister
PROPERTY[OWNERCONTACT0LASTNAME][0] = Test
PROPERTY[OWNERCONTACT0NAME][0] = Mister Test
PROPERTY[OWNERCONTACT0ORGANIZATION][0] = Test Organisation
PROPERTY[OWNERCONTACT0PHONE][0] = +49.123456789
PROPERTY[OWNERCONTACT0STREET][0] = Test street 123
PROPERTY[OWNERCONTACT0ZIP][0] = 12345
PROPERTY[PEERUSER][0] =
PROPERTY[PHONE][0] =
PROPERTY[PROVINCE][0] =
PROPERTY[REGISTRAR][0] = SYSTEM
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-11-02 10:53:28
PROPERTY[REGISTRATIONGRACEPERIOD][0] = 0
PROPERTY[RENEWALACCOUNTINGPERIOD][0] = -7d
PROPERTY[RENEWALFAILUREPERIOD][0] = -3d
PROPERTY[RENEWALFINALIZATIONPERIOD][0] = -3d
PROPERTY[REVISION][0] =
PROPERTY[SERVERSOFTWARE][0] = APACHESSL
PROPERTY[SLOTTYPE][0] =
PROPERTY[SSLCERTCLASS][0] = COMODO_ESSENTIALSSL
PROPERTY[SSLCERTCN][0] = hexonet.net
PROPERTY[SSLCERTDOMAIN][0] = hexonet.net
PROPERTY[SSLCERTID][0] = 2870930343
PROPERTY[STATUS][0] = REQUESTEDCREATE
PROPERTY[STATUSDETAILS][0] =
PROPERTY[STREET][0] =
PROPERTY[TECHCONTACT0CITY][0] = Test City
PROPERTY[TECHCONTACT0COUNTRY][0] = DE
PROPERTY[TECHCONTACT0EMAIL][0] = nomail@test.com
PROPERTY[TECHCONTACT0FIRSTNAME][0] = Mister
PROPERTY[TECHCONTACT0LASTNAME][0] = Test
PROPERTY[TECHCONTACT0NAME][0] = Mister Test
PROPERTY[TECHCONTACT0ORGANIZATION][0] = Test Organisation
PROPERTY[TECHCONTACT0PHONE][0] = +49.123456789
PROPERTY[TECHCONTACT0STREET][0] = Test street 123
PROPERTY[TECHCONTACT0ZIP][0] = 12345
PROPERTY[UPDATEDBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-11-02 10:53:28
PROPERTY[USER][0] = test.user
PROPERTY[VALIDATION][0] = EMAIL
PROPERTY[VALIDATIONDNSRR][0] =
PROPERTY[VALIDATIONEMAIL][0] = info@hexonet.net
PROPERTY[VALIDATIONURL][0] =
PROPERTY[VALIDATIONURLCONTENT][0] =
PROPERTY[ZIP][0] =
EOF
```

----
