# UK_CheckRightOfRegistration

## DESCRIPTION
If you have registered a 3rd level .UK domain before the 10 June 2014 you have the right to register the respective 2nd level .UK domain with the same contact data.
This command checks if you have the right of registration for a dedicated 2nd level .UK domain.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UK_CheckRightOfRegistration` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
NAME | 1 | The registrant's name | TEXT or NULL
STREET | 0 |The registrant's street | TEXT
CITY | 1 | The registrant's city | TEXT
ZIP | 0 | The registrant's ZIP code  | TEXT
COUNTRY | 1 | ISO-3166 Country Code | COUNTRY
EMAIL | 1 | Email Address | EMAIL
ORGANIZATION | 0 | The registrant's organization  | TEXT or NULL
STATE | 0 | The registrant's state | TEXT or NULL

----
## RESPONSE

Code | Description
---- | ----
210 | Domain name available
211	| Domain name not available
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
504	| Missing required attribute
505 | Invalid attribute value syntax
507 | Invalid command format
530 | Authentication failed
552 | Object status does not allow for operation



Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
REASON | 1 | 1 | If you do not have the right of registration the reason is stated here | TEXT or NULL
X-UK-RIGHT-OF-REGISTRATION-DOMAIN | 1 | 1 | The 3rd level .UK domain which grants you the right of registration | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = UK_CheckRightOfRegistration
CITY = Test City
COUNTRY = GB
DOMAIN = horatio-1api-de.uk
EMAIL = test@mail.test
NAME = Test Name
ORGANIZATION = Test Organization
STATE = Test State
STREET = Test Street
ZIP = 012345
EOF
```
### Response

```
[RESPONSE]
CODE = 211
DESCRIPTION = Domain name not available; ORGANIZATION
PROPERTY[REASON][0] = ORGANIZATION
PROPERTY[X-UK-RIGHT-OF-REGISTRATION-DOMAIN][0] = horatio-1api-de.co.uk
EOF
```

----
