# CreateWebsiteSession

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateWebsiteSession` | COMMAND
ID | 1 | ID of the website  | INT
ENTITY | 1 | Must be SITE | TEXT

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
URL | 1 | 1 | The URL of the session | TEXT

## Example

### Command

```
[COMMAND]
COMMAND = CreateWebsiteSession
ENTITY=SITE
ID = 729374580718016515
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[URL][0]=http://weebly.ispapi.net/editor/login.php?t=e86a8e009028e3e52dc89e678a7b35c5&redirect=http%3A%2F%2Fweebly.ispapi.net%2Feditor%2FtoSite.php%3Fsite%3D395985628735716414%26page%3D&user_type=reseller&domain=weebly.ispapi.net
EOF
```

----
