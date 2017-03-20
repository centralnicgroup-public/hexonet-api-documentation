# StatusSSLCert

## DESCRIPTION
Query your certificate signing request, the availability status of a cert, the signed cert data and expiration information.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusSSLCert` | COMMAND
SSLCERTID | 1 | The unique ID of the SSL certificate | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
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
CACRT[0..N] | 0 | N | Intermediate / Root CA certificate | TEXT
CITY | 0 | 1 | Default contact address city | TEXT or NULL
CN | 0 | 1 | Common Name | TEXT
COUNTRY | 0 | 1 | Default contact address country code | COUNTRY or NULL
CREATEDBY | 0 | 1 | Registrar that ordered the SSL certificate | TEXT
CREATEDDATE | 0 | 1 | Order date of the SSL certificate order | DATETIME
CRT[0..N]| 0 | N | Signed certificate | TEXT
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
SSLCERTID | 1 | 1 | SSL certificate ID | TEXT
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
VALIDATIONEMAIL[0..N] | 0 | N | Email address the domain control validation email was sent to; only relevant if the validation method is `EMAIL` | TEXT or NULL
VALIDATIONURL[0..N] | 0 | N | Domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL
VALIDATIONURLCONTENT[0..N] | 0 | N | Expected content at domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL
ZIP | 0 | 1 | Default contact address postal code | TEXT or NULL


----
## Example

### Command

```
[COMMAND]
COMMAND = StatusSSLCert
SSLCERTID = 3029900396
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ADMINCONTACT0CITY][0] = Testcity
PROPERTY[ADMINCONTACT0COUNTRY][0] = DE
PROPERTY[ADMINCONTACT0EMAIL][0] = info@1api.net
PROPERTY[ADMINCONTACT0FIRSTNAME][0] = Uetzel
PROPERTY[ADMINCONTACT0LASTNAME][0] = Maxke
PROPERTY[ADMINCONTACT0ORGANIZATION][0] = Test Org
PROPERTY[ADMINCONTACT0PHONE][0] = +49.12345678
PROPERTY[ADMINCONTACT0STATE][0] = SL
PROPERTY[ADMINCONTACT0STREET][0] = Teststreet 2
PROPERTY[ADMINCONTACT0TITLE][0] = Hansel
PROPERTY[ADMINCONTACT0ZIP][0] = 12345
PROPERTY[BILLINGCONTACT0CITY][0] = Testcity
PROPERTY[BILLINGCONTACT0COUNTRY][0] = DE
PROPERTY[BILLINGCONTACT0EMAIL][0] = info@1api.net
PROPERTY[BILLINGCONTACT0FIRSTNAME][0] = Uetzel
PROPERTY[BILLINGCONTACT0LASTNAME][0] = Maxke
PROPERTY[BILLINGCONTACT0ORGANIZATION][0] = Test Org
PROPERTY[BILLINGCONTACT0PHONE][0] = +49.12345678
PROPERTY[BILLINGCONTACT0STATE][0] = SL
PROPERTY[BILLINGCONTACT0STREET][0] = Teststreet 2
PROPERTY[BILLINGCONTACT0TITLE][0] = Hansel
PROPERTY[BILLINGCONTACT0ZIP][0] = 12345
PROPERTY[CACRT][0] = -----BEGIN CERTIFICATE-----
PROPERTY[CACRT][1] = MIID1DCCArygAwIBAgIQHpFpjHVf56b6C+OC9siGTDANBgkqhkiG9w0BAQsFADCB
PROPERTY[CACRT][2] = gzELMAkGA1UEBhMCR0IxGzAZBgNVBAgTEkdyZWF0ZXIgTWFuY2hlc3RlcjEQMA4G
PROPERTY[CACRT][3] = A1UEBxMHU2FsZm9yZDEaMBgGA1UEChMRQ09NT0RPIENBIExpbWl0ZWQxKTAnBgNV
PROPERTY[CACRT][4] = BAMTIFRlc3QgUlNBIENlcnRpZmljYXRpb24gQXV0aG9yaXR5MB4XDTE0MDEwMTAw
PROPERTY[CACRT][5] = MDAwMFoXDTMwMTIzMTIzNTk1OVowgYMxCzAJBgNVBAYTAkdCMRswGQYDVQQIExJH
PROPERTY[CACRT][6] = cmVhdGVyIE1hbmNoZXN0ZXIxEDAOBgNVBAcTB1NhbGZvcmQxGjAYBgNVBAoTEUNP
PROPERTY[CACRT][7] = TU9ETyBDQSBMaW1pdGVkMSkwJwYDVQQDEyBUZXN0IFJTQSBDZXJ0aWZpY2F0aW9u
PROPERTY[CACRT][8] = IEF1dGhvcml0eTCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAL/ZSIMZ
PROPERTY[CACRT][9] = BY4Ifq5oXcdSPDa5ArrYahP4qhO9aES9jT7TEr5tpNIQQP044h+3MGc7Cgf17OYS
PROPERTY[CACRT][10] = qpd4WvvhgUCkc8XDda3JgKEgCaHfnjgynBtXk6JP8stMIuKPZS9WcEQSKB7JPOnj
PROPERTY[CACRT][11] = aHdBkLRfbuSu0y7he9IoibiSCIU5mJ8T6QNd5wEWBp4jgRQWnLBXtJENtCzcU5j2
PROPERTY[CACRT][12] = sPh0gZUFjlu1V3Cc8JUENzDpMpjtxNYHtbL68BFXcWvy7hrqnE4eNM5K3DfEacdr
PROPERTY[CACRT][13] = vFgIQNfCMc4KEh2DFzDoCZpchDLhVGrYrTObG4D/RR0oT2QuFqbaiatLcG/armNU
PROPERTY[CACRT][14] = gb+4VH1R/HOQaf0CAwEAAaNCMEAwHQYDVR0OBBYEFIaGHcsGJX0nAVdr5Wo40ORE
PROPERTY[CACRT][15] = r5MyMA4GA1UdDwEB/wQEAwIBhjAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3DQEB
PROPERTY[CACRT][16] = CwUAA4IBAQCeQAWeNNtsKuUt5V9JifMy2AduOcK7lndhM24L8KG86o7aoye1QDqM
PROPERTY[CACRT][17] = fFmUrFo7nDVno6G013PnRo97BcrVPoMVB66TP5LywOrLrVoiIF9I5OD4BrtgvrRt
PROPERTY[CACRT][18] = lT3iMZwxjzU19lgEcLs+sJZhug2eDKAjp0PaJ40Wg5sno3CRq/urYgtIAiFdxgMB
PROPERTY[CACRT][19] = efK0Ejivos5RLDzmHjA/Wo+jFMfXvdP6RxVmz7NxfcwsI+sOSWmb60dZlaC1yVZ0
PROPERTY[CACRT][20] = PbD2DFj7yEnW94p86d7Thmv6ksaqbOeWdJErnYJkqXPB0wSazHQeQHjWp91j4Zwl
PROPERTY[CACRT][21] = YRhZQfovwiRi601iWNNE7hPrMb87Fkvy
PROPERTY[CACRT][22] = -----END CERTIFICATE-----
PROPERTY[CITY][0] = Testcity
PROPERTY[CN][0] = 1api.net
PROPERTY[COUNTRY][0] = DE
PROPERTY[CREATEDBY][0] = SYSTEM
PROPERTY[CREATEDDATE][0] = 2016-11-22 08:55:50
PROPERTY[CRT][0] = -----BEGIN CERTIFICATE-----
PROPERTY[CRT][1] = MIIFHTCCBAWgAwIBAgIRALkeili0QF/XvdBpXUu0YJYwDQYJKoZIhvcNAQELBQAw
PROPERTY[CRT][2] = gYMxCzAJBgNVBAYTAkdCMRswGQYDVQQIExJHcmVhdGVyIE1hbmNoZXN0ZXIxEDAO
PROPERTY[CRT][3] = BgNVBAcTB1NhbGZvcmQxGjAYBgNVBAoTEUNPTU9ETyBDQSBMaW1pdGVkMSkwJwYD
PROPERTY[CRT][4] = VQQDEyBUZXN0IFJTQSBDZXJ0aWZpY2F0aW9uIEF1dGhvcml0eTAeFw0xNjExMjIw
PROPERTY[CRT][5] = MDAwMDBaFw0xNzExMjIyMzU5NTlaME0xITAfBgNVBAsTGERvbWFpbiBDb250cm9s
PROPERTY[CRT][6] = IFZhbGlkYXRlZDEVMBMGA1UECxMMRXNzZW50aWFsU1NMMREwDwYDVQQDEwgxYXBp
PROPERTY[CRT][7] = Lm5ldDCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAO6xv99FpPc5ouEi
PROPERTY[CRT][8] = e5969XZ5J9TaaAp/EhjsHoJ98FgMufbrV1TBfRw4Ya251v3M3uFrAAepK1um+HUo
PROPERTY[CRT][9] = yfITVQVitDgv0IhsDN8IQbrmekK7VirJ2qeH0Lx+M0XZvsHvWEhlftvhZnxmrnX0
PROPERTY[CRT][10] = or9iKKzwFdfkg9PzgHAgvDPRUlxaJq9kmevxJF0yJTOWFpDjfDHSvwlbpQziXHJL
PROPERTY[CRT][11] = +WuhvqwRGa8akZIyW+84PmP9cD89mt+32/qHdzdu/dYUHWd3IU0FjSeVXF18rmIt
PROPERTY[CRT][12] = qULQpqEgUoejSnnHoiGAF0VbCDFXEP+SRDmY/vQelPcHcWAkrXdHlkKsYWMfHpv8
PROPERTY[CRT][13] = T83a3QsCAwEAAaOCAb8wggG7MB8GA1UdIwQYMBaAFIaGHcsGJX0nAVdr5Wo40ORE
PROPERTY[CRT][14] = r5MyMB0GA1UdDgQWBBSgViiysYfsEAR6ieWdAGDgraDSCjAOBgNVHQ8BAf8EBAMC
PROPERTY[CRT][15] = BaAwDAYDVR0TAQH/BAIwADAdBgNVHSUEFjAUBggrBgEFBQcDAQYIKwYBBQUHAwIw
PROPERTY[CRT][16] = UAYDVR0gBEkwRzA7BgwrBgEEAbIxAQIBAwQwKzApBggrBgEFBQcCARYdaHR0cHM6
PROPERTY[CRT][17] = Ly9zZWN1cmUuY29tb2RvLm5ldC9DUFMwCAYGZ4EMAQIBMEoGA1UdHwRDMEEwP6A9
PROPERTY[CRT][18] = oDuGOWh0dHA6Ly9jcmwuY29tb2RvY2EuY29tL1Rlc3RSU0FDZXJ0aWZpY2F0aW9u
PROPERTY[CRT][19] = QXV0aG9yaXR5LmNybDB7BggrBgEFBQcBAQRvMG0wRQYIKwYBBQUHMAKGOWh0dHA6
PROPERTY[CRT][20] = Ly9jcnQuY29tb2RvY2EuY29tL1Rlc3RSU0FDZXJ0aWZpY2F0aW9uQXV0aG9yaXR5
PROPERTY[CRT][21] = LmNydDAkBggrBgEFBQcwAYYYaHR0cDovL29jc3AuY29tb2RvY2EuY29tMCEGA1Ud
PROPERTY[CRT][22] = EQQaMBiCCDFhcGkubmV0ggx3d3cuMWFwaS5uZXQwDQYJKoZIhvcNAQELBQADggEB
PROPERTY[CRT][23] = AI5bYdlOaOkwCt26HCv9lD2pAsO9+LLTLfgLwNWFAl44W6Rs1Ldrp3SKqLv+b2K2
PROPERTY[CRT][24] = K/FUQTOHz43C4s1VZMT9gjS7LPyVxEt6vm86SRzIfNfp/9zwW1pDrEvdE44pwqE2
PROPERTY[CRT][25] = dzuuYrfbt9v0vnZUHoSUEeWpvBBfEAVZduYEO2WXr4cvoQmvbFqKB8lI+Z6q2C3n
PROPERTY[CRT][26] = qpvVdBAu5JQryJfzoqulKVDZgWJI6fzAN7EyH3iNJJ0/bTYG2CJe6n7VtRGAXpJG
PROPERTY[CRT][27] = VyoDerenp8QGnpAqWeZBZyJgRRltkwZHlFFuD4rLH1W6rl0Ybhck5cAIfnTs2KTg
PROPERTY[CRT][28] = 6gsvrCzMg/g2aG0TRKQ/JhY=
PROPERTY[CRT][29] = -----END CERTIFICATE-----
PROPERTY[CSR][0] = -----BEGIN CERTIFICATE REQUEST-----
PROPERTY[CSR][1] = MIICwzCCAasCAQAwbzELMAkGA1UEBhMCREUxCzAJBgNVBAgMAlNMMRAwDgYDVQQH
PROPERTY[CSR][2] = DAdIb21idXJnMRAwDgYDVQQKDAdIRVhPTkVUMREwDwYDVQQDDAgxYXBpLm5ldDEc
PROPERTY[CSR][3] = MBoGCSqGSIb3DQEJARYNaW5mb0AxYXBpLm5ldDCCASIwDQYJKoZIhvcNAQEBBQAD
PROPERTY[CSR][4] = ggEPADCCAQoCggEBAO6xv99FpPc5ouEie5969XZ5J9TaaAp/EhjsHoJ98FgMufbr
PROPERTY[CSR][5] = V1TBfRw4Ya251v3M3uFrAAepK1um+HUoyfITVQVitDgv0IhsDN8IQbrmekK7VirJ
PROPERTY[CSR][6] = 2qeH0Lx+M0XZvsHvWEhlftvhZnxmrnX0or9iKKzwFdfkg9PzgHAgvDPRUlxaJq9k
PROPERTY[CSR][7] = mevxJF0yJTOWFpDjfDHSvwlbpQziXHJL+WuhvqwRGa8akZIyW+84PmP9cD89mt+3
PROPERTY[CSR][8] = 2/qHdzdu/dYUHWd3IU0FjSeVXF18rmItqULQpqEgUoejSnnHoiGAF0VbCDFXEP+S
PROPERTY[CSR][9] = RDmY/vQelPcHcWAkrXdHlkKsYWMfHpv8T83a3QsCAwEAAaAPMA0GCSqGSIb3DQEJ
PROPERTY[CSR][10] = DjEAMA0GCSqGSIb3DQEBCwUAA4IBAQBzhg6MwUQJGVr51O55LkprWnWwQVi85sN3
PROPERTY[CSR][11] = 398E+An4zqAkSnfmU42WSnR8/hZLE8Y4eGwDV6k4AgF6rlRcEeQgHgvfsfQuOUzm
PROPERTY[CSR][12] = Zk96oIIBSO/i4E2MfobCPFzVNqwhhWw031mJxFCUs1vkFqNoXZJAkTId9Uj635VF
PROPERTY[CSR][13] = olnO/O1GXy4rhfBC+ofTS3ugKwArm/opoA1NQaXIXPV/Eceep1svsm74kIAYkge0
PROPERTY[CSR][14] = swUWeZaVGOVFJk0RD1MMG+x2yKOTTfJl3B3ua9cgSW8lfYt0qa6k7qUEhWt/uXOm
PROPERTY[CSR][15] = +GUyfpQnyikQGtEOEMLhAvgLORp45suKby2P2f3tZcAvMoLR6xXk
PROPERTY[CSR][16] = -----END CERTIFICATE REQUEST-----
PROPERTY[CSRORGANIZATION][0] = HEXONET
PROPERTY[DELETIONHOLDPERIOD][0] =
PROPERTY[DELETIONRESTORABLEPERIOD][0] =
PROPERTY[DOMAIN][0] = 1api.net
PROPERTY[DOMAINCOUNT][0] = 1
PROPERTY[EMAIL][0] = info@1api.net
PROPERTY[EXPIRATIONDATE][0] = 2017-11-22 23:59:59
PROPERTY[FAX][0] =
PROPERTY[FIRSTNAME][0] = Uetzel
PROPERTY[JOBTITLE][0] = Hansel
PROPERTY[LASTNAME][0] = Maxke
PROPERTY[ORDERDATA][0] = 3029900396
PROPERTY[ORDERREFERENCE][0] = 36237701
PROPERTY[ORGANIZATION][0] = Test Org
PROPERTY[OWNERCONTACT0CITY][0] = Testcity
PROPERTY[OWNERCONTACT0COUNTRY][0] = DE
PROPERTY[OWNERCONTACT0EMAIL][0] = info@1api.net
PROPERTY[OWNERCONTACT0FIRSTNAME][0] = Uetzel
PROPERTY[OWNERCONTACT0LASTNAME][0] = Maxke
PROPERTY[OWNERCONTACT0ORGANIZATION][0] = Test Org
PROPERTY[OWNERCONTACT0PHONE][0] = +49.12345678
PROPERTY[OWNERCONTACT0STATE][0] = SL
PROPERTY[OWNERCONTACT0STREET][0] = Teststreet 2
PROPERTY[OWNERCONTACT0TITLE][0] = Hansel
PROPERTY[OWNERCONTACT0ZIP][0] = 12345
PROPERTY[PEERUSER][0] =
PROPERTY[PHONE][0] = +49.12345678
PROPERTY[PROVINCE][0] = SL
PROPERTY[REGISTRAR][0] = SYSTEM
PROPERTY[REGISTRATIONEXPIRATIONDATE][0] = 2017-11-22 23:59:59
PROPERTY[REGISTRATIONGRACEPERIOD][0] = 0
PROPERTY[RENEWALACCOUNTINGPERIOD][0] = -7d
PROPERTY[RENEWALFAILUREPERIOD][0] = -3d
PROPERTY[RENEWALFINALIZATIONPERIOD][0] = -3d
PROPERTY[REVISION][0] =
PROPERTY[SLOTTYPE][0] =
PROPERTY[SSLCERTCLASS][0] = COMODO_ESSENTIALSSL
PROPERTY[SSLCERTCN][0] = 1api.net
PROPERTY[SSLCERTDOMAIN][0] = 1api.net
PROPERTY[SSLCERTID][0] = 3029900396
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[STATUSDETAILS][0] = Valid
PROPERTY[STREET][0] = Teststreet 2
PROPERTY[TECHCONTACT0CITY][0] = Testcity
PROPERTY[TECHCONTACT0COUNTRY][0] = DE
PROPERTY[TECHCONTACT0EMAIL][0] = info@1api.net
PROPERTY[TECHCONTACT0FIRSTNAME][0] = Uetzel
PROPERTY[TECHCONTACT0LASTNAME][0] = Maxke
PROPERTY[TECHCONTACT0ORGANIZATION][0] = Test Org
PROPERTY[TECHCONTACT0PHONE][0] = +49.12345678
PROPERTY[TECHCONTACT0STATE][0] = SL
PROPERTY[TECHCONTACT0STREET][0] = Teststreet 2
PROPERTY[TECHCONTACT0TITLE][0] = Hansel
PROPERTY[TECHCONTACT0ZIP][0] = 12345
PROPERTY[UPDATEDBY][0] = SYSTEM
PROPERTY[UPDATEDDATE][0] = 2016-11-22 08:55:50
PROPERTY[USER][0] = test.user
PROPERTY[VALIDATION][0] = EMAIL
PROPERTY[VALIDATIONDNSRR][0] =
PROPERTY[VALIDATIONEMAIL][0] = info@1api.net
PROPERTY[VALIDATIONURL][0] =
PROPERTY[VALIDATIONURLCONTENT][0] =
PROPERTY[ZIP][0] = 12345
EOF
```

----
