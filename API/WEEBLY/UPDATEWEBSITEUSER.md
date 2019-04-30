# UpdateWebsiteUser

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateWebsiteUser` | COMMAND
WEBSITEUSERID | 1 | ID from response of CreateWebsiteUser  | INT
EMAIL | 0 | Email Address | EMAIL
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
531 | Authorization failed
541 | Invalid attribute value

## Example

### Command

```
[COMMAND]
COMMAND = UpdateWebsiteUser
WEBSITEUSERID = 123958654
EMAIL = update@dot.com
LANGUAGE = en
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[LANGUAGE][0] = en
PROPERTY[EMAIL][0] = update@dot.com
PROPERTY[WEBSITEUSERID][0] = 123958654
EOF
```

----
