# DENIC_CreateAuthInfo1

## DESCRIPTION
This command is used to create an AuthInfo1, an Authorization Code for a .DE domain, which is needed in
order to transfer a .DE domain to another registrar which supports the AuthInfo1 transfer procedure for .DE domains.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DENIC_CreateAuthInfo1` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
AUTH | 0 | Using this parameter you can set your own AuthInfo1 instead of letting us generate a random code | TEXT
X-DE-AUTHINFO1-EXPIRATIONDATE | 0 | You may set a date on which the AuthInfo1 expires. If you don't use this parameter, we will set a standard expiration date | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500 | Invalid command name
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
545 | Object not found
549 | Command failed
552 | Object status does not allow for operation

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
AUTH | 1 | 1 | The new AuthInfo1 | TEXT
STATUS[0..N] | 1 | N | The status of the domain | TEXT
X-DE-AUTHINFO1-EXPIRATIONDATE | 1 | 1 | The expiration date of the AuthInfo1 | DATETIME


----
## Example

### Command

```
[COMMAND]
COMMAND = DENIC_CreateAuthInfo1
AUTH = topsecret
DOMAIN = mytestdomain1.de
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[AUTH][0] = topsecret
PROPERTY[STATUS][0] = ACTIVE
PROPERTY[X-DE-AUTHINFO1-EXPIRATIONDATE][0] = 2016-12-17
EOF
```

----
