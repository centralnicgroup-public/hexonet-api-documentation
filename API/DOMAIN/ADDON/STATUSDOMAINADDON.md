# StatusDomainAddon

## DESCRIPTION
This command returns a list of all configuration parameters for a specific domain addon.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainAddon` | COMMAND
ADDONCLASS | 1 | Addon class | TEXT
ADDONID | 1 | Addon ID | TEXT
REPOSITORY | 1 | Repository name | TEXT

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
545 | Object not found
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
DISPUTEEMAIL | 1 | 1 | The dispute email address for the domain addon | TEXT or NULL
NOTIFICATIONEMAIL | 1 | 1 | The notification email address for the domain addon | TEXT or NULL
POLICYOWNERCHANGE | 1 | 1 | The policy regarding a change of ownership | TEXT
RENEWALGRACEPERIODSECONDS | 1 | 1 | The renewal grace period for the domain addon, displayed in seconds | INT
RENEWALPERIOD | 1 | 1 | The renewal period for the domain addon | TEXT
REPLACEPROPERTIES | 1 | 1 | The domain properties that are replaced by the addon | TEXT or NULL
REPOSITORY | 1 | 1 | The respective domain repository | TEXT
ZONE | 1 | 1 | List of zones of the domain addon | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainAddon
ADDONCLASS = PROXY
ADDONID = WHOISTRUSTEE_BIZ
REPOSITORY = BIZ-OTE-1API1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[DISPUTEEMAIL][0] =
PROPERTY[NOTIFICATIONEMAIL][0] =
PROPERTY[POLICYOWNERCHANGE][0] = IGNORE
PROPERTY[RENEWALGRACEPERIODSECONDS][0] = 0
PROPERTY[RENEWALPERIOD][0] = 1M
PROPERTY[REPLACEPROPERTIES][0] =
PROPERTY[REPOSITORY][0] = BIZ-OTE-1API1
PROPERTY[ZONE][0] = biz
EOF
```

----
