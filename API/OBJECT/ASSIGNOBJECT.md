# AssignObject

## DESCRIPTION
Assign an object to an subuser or to the user itself.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `AssignObject` | COMMAND
OBJECTCLASS | 1 | Class of the object. Valid Classes are:<br>`DOMAIN`<br>`DOMAINTRANSFER`<br>`CONTACT`<br>`DNSZONE`<br>`VSERVER`<br>`MOBILEACCOUNT`<br>`SSLCERT`<br>`DOMAINAPPLICATION` | TEXT
OBJECTID | 1 | ID of the object, e. g. `domainname.com` | TEXT
USER | 1 | ID of the object's new user | TEXT
REASON | 0 | Can be used for documentation purpose as it will be logged | TEXT

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
541 | Invalid attribute value
545 | Object not found

No properties are returned

----
## Example

### Command

```
[COMMAND]
COMMAND = AssignObject
OBJECTCLASS = DOMAIN
OBJECTID = hexonet-domain.com
USER = subresell.com
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
* The user must have the authorization to access the object as well as the new user. Further, the gaining user needs to have pricing defined for the objectclass / subclass.
