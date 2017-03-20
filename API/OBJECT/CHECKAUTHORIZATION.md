# CheckAuthorization

## DESCRIPTION
Check if the user is authorized to access and manage an object.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckAuthorization` | COMMAND
OBJECTCLASS | 1 | Class of the object, e. g. DOMAIN | TEXT
OBJECTID | 1 | ID of the object, e. g. `domainname.com` | TEXT

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
531 | Authorization failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
LANGUAGE | 0 | 1 | If OBJECTCLASS is USER the user's default language gets returned here  | TEXT


----
## Example

### Command

```
[COMMAND]
COMMAND = CheckAuthorization
OBJECTCLASS = USER
OBJECTID = testuser1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[LANGUAGE][0] = en_US
EOF
```

----
