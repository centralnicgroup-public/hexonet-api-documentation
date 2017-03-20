# QuerySSLCertDCVEMailAddressList

## DESCRIPTION
Query the list of possible confirmation email addresses.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QuerySSLCertDCVEMailAddressList` | COMMAND
SSLCERTCLASS | 0 | Product type; only relevant if no SSL certificate ID is provided | PATTERN
SSLCERTID | 0 | ID of an existing SSL certificate order; if provided the actual confirmation email address of this SSL certificate order will be returned | TEXT or NULL
DOMAIN | 0 | Domain name for which the SSL certificate would be ordered; only relevant if no SSL certificate ID is provided | TEXT or NULL
CSR[0..N] | 0 | Certificate signing request (CSR) in base64 encoding line by line; only relevant if no SSL certificate ID and no domain are provided | TEXT or NULL

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
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EMAIL[0..N] | 0 | N | Email address | TEXT
LEVEL[0..N] | 0 | N | Type of email address; can be:<br>`WHOIS`: email address retrieved from domain WHOIS<br>`GENERIC`: standard confirmation email address<br>`MANUAL`: email address that can be used in order to trigger a manual validation process | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QuerySSLCertDCVEMailAddressList
DOMAIN = hexonet.net
SSLCERTCLASS = GEOTRUST_RAPIDSSL
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EMAIL][0] = info@hexonet.net
PROPERTY[EMAIL][1] = info@hexonet.net
PROPERTY[EMAIL][2] = admin@hexonet.net
PROPERTY[EMAIL][3] = administrator@hexonet.net
PROPERTY[EMAIL][4] = hostmaster@hexonet.net
PROPERTY[EMAIL][5] = webmaster@hexonet.net
PROPERTY[EMAIL][6] = postmaster@hexonet.net
PROPERTY[EMAIL][7] = support_preprod@geotrust.com
PROPERTY[LEVEL][0] = WHOIS
PROPERTY[LEVEL][1] = WHOIS
PROPERTY[LEVEL][2] = GENERIC
PROPERTY[LEVEL][3] = GENERIC
PROPERTY[LEVEL][4] = GENERIC
PROPERTY[LEVEL][5] = GENERIC
PROPERTY[LEVEL][6] = GENERIC
PROPERTY[LEVEL][7] = MANUAL
EOF
```

----

