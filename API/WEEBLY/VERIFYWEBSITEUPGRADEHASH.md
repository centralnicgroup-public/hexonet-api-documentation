# VerifyWebsiteUpgradeHash

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `VerifyWebsiteUpgradeHash` | COMMAND
WEBSITEUSERID | 1 | ID from response of CreateWebsiteUser  | INT
ID | 1 | ID of the website  | INT
CLASS | 1 | WEEBLY | TEXT
HASH | 1 | Hash to be verified | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed

## Example

### Command

```
[COMMAND]
COMMAND=VerifyWebsiteUpgradeHash
ID=12345678901234
WEBSITEUSERID=1234567890
CLASS=WEEBLY
HASH=0123456789012345678901234567890123456789
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
