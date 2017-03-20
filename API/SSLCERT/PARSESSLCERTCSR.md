# ParseSSLCertCSR

## DESCRIPTION
Retrieve information of a provided CSR. The command can be used to check the validity of a CSR.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ParseSSLCertCSR` | COMMAND
CSR[0..N] | 1 | The certificate signing request (CSR) in base64 encoding line by line | TEXT or NULL

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
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ALTERNATECN[0..N] | 0 | N | Subject Alternative Name | TEXT
C[0..N] | 0 | N | Country Code | COUNTRY
CACRT | 0 | 1 | Indicates if a CA certificate is requested by the CSR | TEXT
CN[0..N] | 0 | N | Common Name | TEXT
EMAILADDRESS[0..N] | 0 | N | Email address | TEXT
L[0..N] | 0 | N | City | TEXT
O[0..N] | 0 | N | Organization | TEXT
RSAPUBLICKEYBITS | 0 | 1 | Key length of the public key | INT
ST[0..N] | 0 | N | State | TEXT
STREET[0..N] | 0 | N | Street | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = ParseSSLCertCSR
CSR0 = -----BEGIN CERTIFICATE REQUEST-----
CSR1 = MIIDGjCCAgICAQAwgYoxCzAJBgNVBAYTAkRFMQswCQYDVQQIDAJTTDEQMA4GA1UE
CSR2 = BwwHSG9tYnVyZzETMBEGA1UECQwKVGFsc3RyLiAyNzEQMA4GA1UECgwHSEVYT05F
CSR3 = VDEUMBIGA1UEAwwLaGV4b25ldC5uZXQxHzAdBgkqhkiG9w0BCQEWEGluZm9AaGV4
CSR4 = b25ldC5uZXQwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDusb/fRaT3
CSR5 = OaLhInufevV2eSfU2mgKfxIY7B6CffBYDLn261dUwX0cOGGtudb9zN7hawAHqStb
CSR6 = pvh1KMnyE1UFYrQ4L9CIbAzfCEG65npCu1Yqydqnh9C8fjNF2b7B71hIZX7b4WZ8
CSR7 = Zq519KK/Yiis8BXX5IPT84BwILwz0VJcWiavZJnr8SRdMiUzlhaQ43wx0r8JW6UM
CSR8 = 4lxyS/lrob6sERmvGpGSMlvvOD5j/XA/PZrft9v6h3c3bv3WFB1ndyFNBY0nlVxd
CSR9 = fK5iLalC0KahIFKHo0p5x6IhgBdFWwgxVxD/kkQ5mP70HpT3B3FgJK13R5ZCrGFj
CSR10 = Hx6b/E/N2t0LAgMBAAGgSjBIBgkqhkiG9w0BCQ4xOzA5MCwGA1UdEQQlMCOCD3d3
CSR11 = dy5oZXhvbmV0Lm5ldIIQd2lraS5oZXhvbmV0Lm5ldDAJBgNVHRMEAjAAMA0GCSqG
CSR12 = SIb3DQEBCwUAA4IBAQBdMKVliP7VAJ2FXSc2iXJ5EzSYPM2NAZbF/gsZsefyz7/m
CSR13 = 4J4uPPlzmqSVt5HRz1DXmmbvipKhG3qR+EW7OX7djqOzj+/RXKsGcZkcpIXHC7cp
CSR14 = 0WMNSWydL4SUqzPnCF7vReU8oe/WeuIKUboxjLCZk+ziiisTm9j70rplZxASfmkm
CSR15 = 069zyRyqQ0RxIfvjhXRsmg4noqLsFwQ6Md/6xqq4UVa6PobAX1NZiXSOGJ2Rs0Z8
CSR16 = u7bjLkx/JniBrQjhgsQi0xK8VXAKcxqfqsfUI+l+AnTOT+qom3vwZbzN4FtP+sOk
CSR17 = UFwW8mINwx0pipujBDV85FyZ4hfLiUz2zo6sMKtC
CSR18 = -----END CERTIFICATE REQUEST-----
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ALTERNATECN][0] = www.hexonet.net
PROPERTY[ALTERNATECN][1] = wiki.hexonet.net
PROPERTY[C][0] = DE
PROPERTY[CACRT][0] = FALSE
PROPERTY[CN][0] = hexonet.net
PROPERTY[EMAILADDRESS][0] = info@hexonet.net
PROPERTY[L][0] = Homburg
PROPERTY[O][0] = HEXONET
PROPERTY[RSAPUBLICKEYBITS][0] = 2048
PROPERTY[ST][0] = SL
PROPERTY[STREET][0] = Talstr. 27
EOF
```

----
