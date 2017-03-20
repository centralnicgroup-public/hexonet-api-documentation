# ImportDomain

## DESCRIPTION
This command is used add a domain name that only exists at the respective registry to a dedicated user account. The complementary command is ReleaseDomain.

## AVAILABILITY
Only for registrars using our RegistrarOC system.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ImportDomain` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
REPOSITORY | 0 | Provide the respective domain repository. If not given the domain repository will be determined automatically and will be the same as the one used for new domain registrations of the same TLD. | TEXT
SUBUSER | 0 | The account in which the domain should be created | TEXT
CREATEDDATE | 0 | The created date of the domain. | TEXT or NULL
EXPIRATIONDATE | 0 | Only allowed for dediacted TLDs where the respective registry does not provide an expiration date. | TEXT or NULL
PERIOD | 0 | The period is used to calculate the respective accounting. The accounting is only created if PAY is set to `1`. If no period is provided the default registration period is used. | PERIOD
PAY | 0 | Create a respective accounting for all users in the chain. | TEXT
X-PT-ROID | 0 | Only required in order to import .PT domains. It is the ROID of the domain provided by the registry. | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 |	Invalid attribute name
504 |	Missing required attribute
505 |	Invalid attribute value syntax
530 |	Authentication failed
531 |	Authorization failed
540 |	Attribute value is not unique
541 |	Invalid attribute value
545 |	Object not found
546 |	Credit limit exceeded
549 |	Command failed
552 |	Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ImportDomain
DOMAIN = hexonet-domain.se
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
