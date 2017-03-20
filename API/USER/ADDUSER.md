# AddUser

## DESCRIPTION
Create a new subuser.

## AVAILABILITY
Your account must have the ALLOW_SUBUSER relation set to `1`.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AddUser` | COMMAND
SUBUSER | 1 | New user ID | TEXT
PASSWORD | 1 | Password for the new user | TEXT
CREDIT | 0 | Credit limit of the new user | TEXT
VAT | 1 | Additional V.A.T % for the new user, e.g. `16.00` | TEXT
TAXRATES | 0 | Tax rates | TEXT or NULL
CURRENCY | 1 | Currency of the new user account, e.g. `USD` | TEXT
USERCLASS | 0 | Name of a UserClass (see ModifyUserClass to learn more about UserClasses) | TEXT
RELATION[0..N] | 0 | Relations for the new user | TEXT
ENVIRONMENT[0..N] | 0 | Environment parameters for the new user | TEXT
COMMENT[0..N] | 0 | Comment in one or more lines | TEXT or NULL
ALLOWEDIP[0..N] | 0 | Allowed IP addresses | TEXT or NULL

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
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = AddUser
SUBUSER = subreseller.com
PASSWORD = topsecret
CREDIT = 0.00
CURRENCY = EUR
VAT = 16.00
RELATION0 = ZONES:com,net
RELATION1 = PRICE_CLASS_DOMAIN_COM_ANNUAL:9.00
RELATION2 = PRICE_CLASS_DOMAIN_COM_SETUP=0.00
RELATION3 = PRICE_CLASS_DOMAIN_NET_ANNUAL:9.00
RELATION4 = PRICE_CLASS_DOMAIN_NET_SETUP=0.00
ENVIRONMENT0 = user-info/contact/company/organization:Testcompany
ENVIRONMENT1 = user-info/contact/company/street:Teststreet_address
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
