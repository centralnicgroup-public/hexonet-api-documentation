# UpdateRoleUser

## DESCRIPTION
This command updates several parameters of a certain role user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateRoleUser` | COMMAND
ROLEID | 1 | The role user ID | TEXT
PASSWORD | 0 | The role user password | TEXT
OTPSECRET | 0 | Secret used for two-factor authentication. | TEXT or NULL
DESCRIPTION[0..N] | 0 | Description text to describe e.g. the position or rights of a user within a company | TEXT or NULL
ACL[0..N] | 0 | A list of API commands which execution the role user is either denied or granted. <br>Must be stated in the following syntax: API command, followed by squared or round brackets, a colon, and ALLOW or DENY. <br>Example: `RenewDomain():DENY` denies the execution of RenewDomain commands for the role user.<br><br>You can also allow or deny only the execution of commands with certain parameters via wildcards. <br>Squared brackets work for white- and blacklisting with any amount of parameters.<br>Round brackets do only work for at maximum one parameter and enforce the use of a given parameter in the command. <br>If you are in doubt which bracket to use, use the squared bracket. Example: <br>ACL0 = `RenewDomain[`<br>ACL1 = `domain=*.uk`<br>ACL2 = `]:DENY`<br> denies the execution of  RenewDomain commands for .UK domains only. | TEXT or NULL
ALLOWEDIP[0..N] | 0 | List of IP addresses from which a role user is allowed to log in | TEXT or NULL
STATUS | 0 | Set the status of the role user to `ACTIVE` or `INACTIVE` | `ACTIVE` or `INACTIVE`
DEFAULTPOLICY | 0 | If no rights for a certain command are defined, this policy is used | `DENY` or `ALLOW`
SUBUSER | 0 | By providing this parameter you can modify the role user of a certain subuser | TEXT

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
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
COMMAND = UpdateRoleUser
ACL0 = RenewDomain[
ACL1 = domain=*.uk
ACL2 = ]:DENY
ALLOWEDIP0 = 1.2.3.4
DEFAULTPOLICY = ALLOW
ROLEID = myrole
STATUS = ACTIVE
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

* To clear existing property values for DESCRIPTION[0..N], ACL[0..N] and ALLOWEDIP[0..N] following command has to be executed (the values can not be cleared individually):

```
COMMAND = UpdateRoleUser
ACL0 =
ALLOWEDIP0 =
DESCRIPTION0 =
```

* Setting ACL[0..N], ALLOWEDIP[0..N], DESCRIPTION[0..N] overwrites existing values for the role user
