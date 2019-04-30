# StatusWebsiteUser

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusWebsiteUser` | COMMAND
WEBSITEUSERID | 1 | ID from response of CreateWebsiteUser  | INT

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
545 | Object not found


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CLASS | 1 | 1 | Class of the object, returns `WEBSITE-USER` in case of a website user | TEXT
CREATEDDATE | 1 | 1 | The creation date of the website user | DATETIME
DESCRIPTION | 1 | 1 | The email address set for the website user | TEXT
EMAIL | 1 | 1 | The email address set for the website user | TEXT
ID | 1 | 1 | The ID of the website user | TEXT
LANGUAGE | 1 | 1 | The language set for the website user | TEXT
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
REPOSITORY | 1 | 1 | The website user's repository | TEXT
SUBCLASS | 1 | 1 | Subclass of the website user | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the website user| DATETIME
USER | 1 | 1 | The user that manages this website user| TEXT
WEBSITEUSERID | 1 | 1 | The ID of the website user | TEXT


## Example

### Command

```
[COMMAND]
COMMAND = StatusWebsiteUser
WEBSITEUSERID = 123958654
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ID][0] = 123958654
PROPERTY[CREATEDDATE][0] = 2019-01-15 13:16:26
PROPERTY[LANGUAGE][0] = en
PROPERTY[PEERUSER][0] =
PROPERTY[USER][0] = karches-weebly
PROPERTY[CLASS][0] = WEBSITE-USER
PROPERTY[SUBCLASS][0] = WEEBLY
PROPERTY[EMAIL][0] = update@dot.com
PROPERTY[REPOSITORY][0] = WEEBLY-LIVE-HEXONET
PROPERTY[UPDATEDDATE][0] = 2019-01-15 14:21:03
PROPERTY[DESCRIPTION][0] = update@dot.com
PROPERTY[WEBSITEUSERID][0] = 123958654
EOF
```

----
