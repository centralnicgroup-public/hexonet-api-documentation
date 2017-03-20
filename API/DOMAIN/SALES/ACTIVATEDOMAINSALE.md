# ActivateDomainSale

## DESCRIPTION
This command is used for confirmation of aftermarket FOA pre-confirmations. E.g. AfterNIC requires them for com/net/org/biz/info. Sedo requires them for all gTLDs.

If the command gets used on a white-label page without user pre-authentication, then only DOMAIN[0..N]= and TRIGGER= parameters should get used for security reasons.

Otherwise, if the confirmation page is inside an area with user pre-authentication, then we should allow the user to set the aftermarket channel permissions here, too.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ---- | ----
COMMAND | 1 | `ActivateDomainSale` | COMMAND
DOMAIN[0..N] | 1 | The domain names. | DOMAIN
TRIGGER | 1 | The trigger from the confirmation link | TEXT
AFTERNIC-STATUS | 0 | The listing status on AfterNIC | `DISABLED`, `ACTIVE` or `NONE`
SEDO-STATUS | 0 | The listing status on Sedo | `DISABLED`, `ACTIVE` or `NONE`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
549 | Channel error

----
## Example

### Command

```
[COMMAND]
COMMAND=ActivateDomainSale
DOMAIN=test12345.com
TRIGGER=af2340fc06543689dfe0a
AFTERNIC-STATUS=ACTIVE
SEDO-STATUS=DISABLED
EOF
```
### Response

```
[RESPONSE]
DESCRIPTION=Command completed successfully
CODE=200
...
EOF
```

----
