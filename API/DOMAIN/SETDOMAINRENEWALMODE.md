# SetDomainRenewalMode

## DESCRIPTION
Set the renewal mode of a single domain. With this command you can choose what is going to happen with the domain after the registration expiration date.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `SetDomainRenewalMode` | COMMAND
DOMAIN | 1 | Domain Name | DOMAIN
RENEWALMODE | 1 | `DEFAULT`: If default is chosen, `AUTORENEW` setting will be applied.<br>`AUTORENEW`: When the RegistrationPeriod for a domain expires, the domain is automatically renewed (on FinalizationDate) and the RegistrationPeriod is extended by the length of the RenewalPeriod for a particular domain (normally 1 year). <br>`AUTOEXPIRE`: Domain is deleted at the end of the RegistrationPeriod (on FailureDate), or is pushed to the registry for self management if the respective registry offers such functionality.<br>`AUTODELETE`: Domain is deleted at the end of the RegistrationPeriod (on FailureDate).<br>`AUTORENEWMONTHLY`: Behaves like AUTORENEW, but on a monthly cycle (currently only available for .DE domains). | `DEFAULT`, `AUTORENEW`, `AUTOEXPIRE`, `AUTODELETE` or `AUTORENEWMONTHLY`
PERIOD | 0 | DEFAULT (for the most domains: 1 year) <br> xY (for x years) <br> xM (for x months) <br> (please remark that "Y" and "M" are case sensitive!) <br> | TEXT, `1M` or NULL

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
500	| Invalid command name
503 | Invalid attribute name
505 | Invalid attribute value syntax
530	| Authentication failed
531	| Authorization failed
541	| Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
UNRENEW | 1 | 1 | Is set to `1` if the domain has been unrenewed | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = SetDomainRenewalMode
DOMAIN = example.com
RENEWALMODE = AUTODELETE
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[UNRENEW][0] = 0
EOF
```

----
