# ReissueSSLCert

## DESCRIPTION
Request a replacement for an existing SSL certificate using a new CSR. This is useful when your private key got compromised or if you want to change the Subject Alternative Names (SANs) of a Unified Communications Certificate (UCC).

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ReissueSSLCert` | COMMAND
SSLCERTID | 1 | SSL certificate ID | TEXT
CSR[0..N] | 1 | The certificate signing request (CSR) in base64 encoding line by line | TEXT or NULL
EMAIL | 0 | Email address to send the confirmation email to; if omitted the email address originally used will be used again | TEXT or NULL
ALTERNATECN[0..N] | 0 | Subject Alternative Names that should be included in the new SSL certificate | TEXT or NULL
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
DOMAIN[0..N] | 0 | Domain name(s) for which the SSL certificate will be reissued; must be the same as the Common Name (CN) plus the Subject Alternative Names (SANs) of the CSR if provided | TEXT or NULL
VALIDATION[0..N] | 0 | Domain control validation method; can be `DNSZONE`, `EMAIL`, `URL`; the default is: `EMAIL` | TEXT or NULL
VALIDATIONEMAIL[0..N] | 0 | Email address the domain control validation email is supposed to be sent to; only relevant if the validation method is `EMAIL`; if omitted the email address of the applicant is used | TEXT or NULL
PEM[0..N] | 0 | Private key in PEM format; will be used for the creation of a CSR; only relevant if no CSR is provided | TEXT or NULL
CREATEPRIVATEKEY | 0 | If set to `1` a new private key will be created which will be used for the creation of a new CSR; otherwise the old private key will be re-used; only relevant if no private key and no CSR are provided | `0`, `1` or NULL
KEYLENGTH | 0 | Key length of the private key that will be created; must be between `2048` and `8192`; only relevant if CREATEPRIVATEKEY is used | INT or NULL
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
530 | Authentication failed
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DOMAIN[0..N] | 0 | N | Domain name(s) for which the SSL certificate will be reissued | TEXT
VALIDATION[0..N] | 0 | N | Domain control validation method | TEXT
VALIDATIONDNSRR[0..N] | 0 | N | Domain control validation DNS Resource Record; only relevant if the domain control validation method is `DNSZONE` | TEXT or NULL
VALIDATIONEMAIL[0..N] | 0 | N | Email address the domain control validation email will be sent to; only relevant if the validation method is `EMAIL` | TEXT or NULL
VALIDATIONURL[0..N] | 0 | N | Domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL
VALIDATIONURLCONTENT[0..N] | 0 | N | Expected content at domain control validation URL; only relevant if the domain control validation method is `URL` | TEXT or NULL

----
## Example

### Command

```
[COMMAND]
COMMAND = ReissueSSLCert
CSR0 = -----BEGIN CERTIFICATE REQUEST-----
CSR1 = MIIC4zCCAcsCAQAwgYExCzAJBgNVBAYTAkRFMQswCQYDVQQIDAJTTDEQMA4GA1UE
CSR2 = BwwHSG9tYnVyZzETMBEGA1UECQwKVGFsc3RyLiAyNzENMAsGA1UECgwEMUFQSTER
CSR3 = MA8GA1UEAwwIMWFwaS5uZXQxHDAaBgkqhkiG9w0BCQEWDWluZm9AMWFwaS5uZXQw
CSR4 = ggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDusb/fRaT3OaLhInufevV2
CSR5 = eSfU2mgKfxIY7B6CffBYDLn261dUwX0cOGGtudb9zN7hawAHqStbpvh1KMnyE1UF
CSR6 = YrQ4L9CIbAzfCEG65npCu1Yqydqnh9C8fjNF2b7B71hIZX7b4WZ8Zq519KK/Yiis
CSR7 = 8BXX5IPT84BwILwz0VJcWiavZJnr8SRdMiUzlhaQ43wx0r8JW6UM4lxyS/lrob6s
CSR8 = ERmvGpGSMlvvOD5j/XA/PZrft9v6h3c3bv3WFB1ndyFNBY0nlVxdfK5iLalC0Kah
CSR9 = IFKHo0p5x6IhgBdFWwgxVxD/kkQ5mP70HpT3B3FgJK13R5ZCrGFjHx6b/E/N2t0L
CSR10 = AgMBAAGgHDAaBgkqhkiG9w0BCQ4xDTALMAkGA1UdEwQCMAAwDQYJKoZIhvcNAQEL
CSR11 = BQADggEBAAcUhF/eSIOqITyYYYgTeDBnIoKdJXPuNKeqxD8uaRaNKORgIm3wfkiP
CSR12 = Xs42dalsaOeOWMJVMnqRXldanFUdFyIlDr+KMEuDliEQ+t08yMRrRvC1CicXaGIH
CSR13 = uynGKV8C6+04f8Fb1laQO9sGC2Up4XuXxi1cWe01u0Ao8DguKeFS+QeUXWF6GuMV
CSR14 = 1ZHEx38KEvaRUCrT3l53+nD5W5H1do8ZpbQPh+3SgeEmRwLwhY4P0m2bzU2ZyF5L
CSR15 = UlSO5l8dfPkWonPsJDTSNPHNeI+dJTraO+ilJStfkOrf0OgmlUl05IoYZwd87vDl
CSR16 = NEWIAYNM7JRZMUW6QLJU1MBFGPAM0UM =
CSR17 = -----END CERTIFICATE REQUEST-----
SSLCERTID = OMYBwbNtDFG6Rp47YFuzE
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[DOMAIN][0] = 1api.net
PROPERTY[VALIDATION][0] = EMAIL
PROPERTY[VALIDATIONDNSRR][0] =
PROPERTY[VALIDATIONEMAIL][0] = info@1api.net
PROPERTY[VALIDATIONURL][0] =
PROPERTY[VALIDATIONURLCONTENT][0] =
EOF
```

----
