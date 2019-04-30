# CreateWebsiteUser

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateWebsiteUser` | COMMAND
CLASS | 1 | Must be WEEBLY | TEXT
X-ACCEPT-WEEBLY-TAC | 1 | Set to `1` to confirm already having signed the End User agreement for Weebly | `1` or NULL
EMAIL | 1 | Email Address | EMAIL
LANGUAGE | 0 | The website user's language (default is `EN`) | TEXT or NULL

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
540 | Attribute value is not unique
541 | Invalid attribute value

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
WEBSITEUSERID | 1 | 1 | The ID of the website user | TEXT

## Example

### Command

```
[COMMAND]
COMMAND = CreateWebsiteUser
EMAIL = test@example.com
CLASS = WEEBLY
X-ACCEPT-WEEBLY-TAC = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[WEBSITEUSERID][0] = 123522904
EOF
```

----
