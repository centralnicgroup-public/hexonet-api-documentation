# CreateRoleUser

## DESCRIPTION
Creates a role user with certain rights to access various API commands.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateRoleUser` | COMMAND
ROLEID | 1 | The role user ID | TEXT
PASSWORD | 1 | The role user password | TEXT
DESCRIPTION[0..N] | 0 | Description text to describe e.g. the position or rights of a user within a company | TEXT or NULL
ACL[0..N] | 0 |  A list of API commands which execution the role user is either denied or granted. <br>Must be stated in the following syntax: API command, followed by squared or round brackets, a colon, and ALLOW or DENY. <br>Example: `RenewDomain():DENY` denies the execution of RenewDomain commands for the role user.<br><br>You can also allow or deny only the execution of commands with certain parameters via wildcards. <br>Squared brackets work for white- and blacklisting with any amount of parameters.<br>Round brackets do only work for at maximum one parameter and enforce the use of a given parameter in the command. <br>If you are in doubt which bracket to use, use the squared bracket. Example: <br>ACL0 = `RenewDomain[`<br>ACL1 = `domain=*.uk`<br>ACL2 = `]:DENY`<br> denies the execution of  RenewDomain commands for .UK domains only. | TEXT or NULL
ALLOWEDIP[0..N] | 0 |  List of IP addresses/subnets from which a role user is allowed to log in | TEXT or NULL
STATUS | 0 | Set the status of the role user to `ACTIVE` or `INACTIVE`. Default value is `ACTIVE` | `INACTIVE` or `ACTIVE`
DEFAULTPOLICY | 0 | If no rights for a certain command are defined, this policy is used. Must be either `ALLOW` or `DENY`. Default is `DENY` | `ALLOW` or `DENY`
SUBUSER | 0 | Subuser for which the role user should be created | TEXT

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
540 | Attribute value is not unique
541 | Invalid attribute value
549 | Command failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = CreateRoleUser
ACL0 = QueryDomainList[]:ALLOW
ACL1 = QueryExtendedDomainList():ALLOW
ACL2 = DeleteDomain():ALLOW
ACL3 = RenewDomain[
ACL4 = DOMAIN = *.uk
ACL5 = PERIOD = 1
ACL6 = ]:ALLOW
DEFAULTPOLICY = DENY
DESCRIPTION0 = Test User
DESCRIPTION1 = This is only a test user
PASSWORD = topsecret
ROLEID = myrole
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
The above example command creates a role user which can only execute the following API commands:
* QueryDomainList
* QueryExtendedDomainList
* DeleteDomain
* RenewDomain, but only for .UK domains and with a period of 1

The execution of all other API commands is forbidden via the DEFAULTPOLICY `DENY`.

