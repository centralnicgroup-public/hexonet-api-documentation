# StatusRoleUser

## DESCRIPTION
Using this command, you can query all parameters related to a certain role user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusRoleUser` | COMMAND
ROLEID | 1 | The role ID of the role user | TEXT
SUBUSER | 0 | Subuser ID if the role user belongs to a subuser | TEXT

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
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ALLOWEDIP[0..N] | 0 | N | The IP addresses/subnets from which the role user is allowed to log in | TEXT
ACL[0..N] | 0 | N | The rights of the role user | TEXT
CREATEDDATE | 1 | 1 | Date of creation of the role user | DATETIME
DEFAULTPOLICY | 1 | 1 | Default access policy of the role user | TEXT
DESCRIPTION[0..1] | 0 | 2 | Description entered at the creation of the role user | TEXT
OTPSTATUS | 1 | 1 | The status of the 2 factor authentification, `ACTIVE` or `INACTIVE` | TEXT
STATUS | 1 | 1 | Current status of the role user | TEXT
UPDATEDDATE | 1 | 1 | Date of last modification of the role user | DATETIME

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusRoleUser
ROLEID = myrole
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACL][0] = QueryDomainList():ALLOW
PROPERTY[ACL][1] = QueryExtendedDomainList():ALLOW
PROPERTY[ACL][2] = DeleteDomain():ALLOW
PROPERTY[ACL][3] = RenewDomain(
PROPERTY[ACL][4] = DOMAIN=*.uk
PROPERTY[ACL][5] = PERIOD=1
PROPERTY[ACL][6] = ):DENY
PROPERTY[CREATEDDATE][0] = 2016-12-02 10:22:08
PROPERTY[DEFAULTPOLICY][0] = DENY
PROPERTY[DESCRIPTION][0] = Test User
PROPERTY[DESCRIPTION][1] = This is only a test user
PROPERTY[OTPSTATUS][0] = INACTIVE
PROPERTY[STATUS][0] = INACTIVE
PROPERTY[UPDATEDDATE][0] = 2016-12-02 10:22:08
EOF
```

----
