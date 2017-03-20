# ModifyUserPassword

## DESCRIPTION
With this command the three basic security features of an account can be managed:
* Modify the password
* Enable and disable 2 factor authentication or update the currently set OTP secret
* Set a list of IPs from which a user can connect to the account

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyUserPassword` | COMMAND
PASSWORD | 0 | New password to be set | TEXT
OLDPASSWORD | 0 | The password which is currently set, must be stated if the existing password should be updated, i.e. if the parameter PASSWORD is stated  | TEXT or NULL
OTPSECRET | 0 | The OTP secret which should be used for the 2 factor authentication. Stating this parameter can have 3 different effects:<br>If it is left empty the 2 factor authentication will be disabled if it was previously enabled<br>If 2 factor authentication is currently disabled and a valid OTP secret is stated 2 factor authentication will be enabled<br>If 2 factor authentication is enabled and a new OTP secret is stated the current OTP secret will be updated | TEXT or NULL
OTP | 0 | The OTP which was created with the new OTP secret to be set. This is a required parameter if you want to update the current OTP secret or enable 2 factor authentaction | TEXT or NULL
OLDOTP | 0 | The OTP which was created with the OTP secret that is currently set. This parameter is required if 2 factor authentication is enabled for the account and you want to either set a new OTP secret or disable 2 factor authentication by setting an empty OTP secret | TEXT or NULL
ALLOWEDIP[0..N] | 0 | List of IP addresses from which the user is allowed to log in | TEXT or NULL

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
552 | Object status does not allow for operation

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyUserPassword
PASSWORD = topsecret!
OLDPASSWORD = previouspassword
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
