# ModifyUser

## DESCRIPTION
Modify an existing subuser.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyUser` | COMMAND
SUBUSER | 1 | Subuser ID | TEXT
PASSWORD | 0 | New password for the subuser | TEXT
OTPSECRET | 0 | OTP Secret which should be set for the user | TEXT or NULL
CREDIT | 0 | Credit limit of the subuser | TEXT
VAT | 0 | Additional V.A.T. % for the subuser, e. g. `19.00` | TEXT
CURRENCY | 0 | Currency of the subuser account, e. g. `USD` | TEXT
USERCLASS | 0 | Name of a UserClass (see ModifyUserClass to learn more about UserClasses) | TEXT
ACTIVE | 0 | Activates/deactivates the user account | `0`, `1` or NULL
FLUSHRELATIONS | 0 | Delete all userdefined relations during the update | `0` or `1`
FLUSHENVIRONMENT | 0 | Delete all environment settings during the update | `0` or `1`
RELATION[0..N] | 0 | Relations for the subuser | TEXT
ADDRELATION[0..N] | 0 | Add one or more relations to the users special relations | TEXT
DELRELATION[0..N] | 0 | Remove one or more relations from the users special relations | TEXT
ENVIRONMENT[0..N] | 0 | Add one or more keys to the users environment | TEXT
TAXRATES | 0 | Define taxrates for the respective user | TEXT or NULL
NEWSUBUSER | 0 | New Subuser ID | TEXT
COMMENT[0..N] | 0 | Add a comment line to the users comments field | TEXT or NULL
ALLOWEDIP[0..N] | 0 | Add an IP address to the users list of allowed IP addresses | TEXT or NULL

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
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
545 | Object not found

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyUser
CREDIT = 1000.00
PASSWORD = topsecret
RELATION0 = ZONES:com,net,org
RELATION1 = PRICE_CLASS_DOMAIN_ORG_ANNUAL:9.00
RELATION2 = PRICE_CLASS_DOMAIN_ORG_SETUP:0.00
RELATION3 = PRICE_CLASS_DOMAIN_NET_ANNUAL:10.00
SUBUSER = subuser.test
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
## NOTES
* New relation values overwrite existing relations with the same name.
* Empty relation values delete existing relations with the same name.
* New environment values overwrite existing environment values with the same name.
* Empty environment values delete existing environment values with the same name.
