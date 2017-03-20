# UpdateDomainSaleAccount

## DESCRIPTION
For domain listings on SEDO, each customer needs to assign a SEDO account API key with its HEXONET account.

AfterNIC does not allow us to list domains in other user accounts, so we would need to use our hexonet account and allow our customers to list their domains via our account. It is required for listing domains on AfterNIC.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ---- | ----
COMMAND | 1 | `UpdateDomainSaleAccount` | COMMAND
PREMIUMCHANNEL | 1 | `SEDO` or `AFTERNIC` | TEXT
APIKEY | 0 | The Sedo API key for the user account | TEXT
X-AFTERNIC-USE-REGISTRAR-ACCOUNT | 0 | Enable customer to use our AfterNIC account for domain listing, default is `0` | `0` or `1`

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
549 | Channel error

----
## Example

### Command
To save/update the Sedo account API key:
```
[COMMAND]
COMMAND=UpdateDomainSaleAccount
PREMIUMCHANNEL=SEDO
APIKEY=afd12455606da
EOF
```

### Command
To enable customers to use our AfterNIC account to list domains: 
```
COMMAND = UpdateDomainSaleAccount
PREMIUMCHANNEL = AFTERNIC
X-AFTERNIC-USE-REGISTRAR-ACCOUNT = 1
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
