# UpdateWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpdateWebsite` | COMMAND
ID | 1 | ID of the website  | INT
TITLE | 0 | Title of the website | TEXT
UPGRADEURL | 0 | URL | TEXT
BRANDNAME | 0 | Name of the brand | TEXT
BRANDURL | 0 | URL of the brand | TEXT
PUBLISH | 0 | Set to `1` to publish the website | `0`, `1` or NULL
SUSPEND | 0 | Set to `1` to disable customer's access to Site Editor  | `0`, `1` or NULL
SECURE | 0 | Set to `1` to enable SSL certificate | `0`, `1` or NULL


----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
501 | Invalid command option
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
command=UpdateWebsite
ID=545623844885275836
UGRADEURL=http://www.hexonet.net
BRANDNAME=hexonet
BRANDURL=http://www.1api.net
SECURE=1
TITEL=WEEBLY-TEST
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
