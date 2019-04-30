# RestoreWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RestoreWebsite` | COMMAND
ID | 1 | ID of the website  | INT
PERIOD | 1 | Registration period:<br>`1Y` for 1 year<br>`1M` for 1 month<br>(please note that "Y" and "M" are case sensitive) | PERIOD
ORDER | 0 | Restore order action:<br>`CREATE` | `CREATE`

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
541 | Invalid attribute value
546 | Credit limit exceeded


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EXPIRATIONDATE | 0 | 1 | The new expiration date of the website | DATETIME

## Example

### Command

```
[COMMAND]
COMMAND = RestoreWebsite
ID = 729374580718016515
period=1Y
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EXPIRATIONDATE][0]=2021-04-11 12:33:10
EOF
```

----
