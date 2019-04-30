# DeleteWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `DeleteWebsite` | COMMAND
ID | 1 | ID of the website  | INT
ORDER | 0 | Delete order action:<br>`CREATE` | `CREATE`

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
545 | Object not found

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
STATUS | 1 | 1 | The current status of the website | TEXT

## Example

### Command

```
[COMMAND]
COMMAND = DeleteWebsite
ID = 729374580718016515
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[STATUS][0]=PENDINGDELETE
EOF
```

----
