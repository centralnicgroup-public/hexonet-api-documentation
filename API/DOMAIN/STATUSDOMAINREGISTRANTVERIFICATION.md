# StatusDomainRegistrantVerification

## DESCRIPTION
This command shows the registrant verification status of a given domain name.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusDomainRegistrantVerification` | COMMAND
DOMAIN | 1 | Domain name | DOMAIN
NAME | 0 | Registrant name | TEXT
EMAIL | 0 | Registrant email address | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
500 | Invalid command name
504 | Missing required attribute
505 | Invalid attribute value syntax
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
EMAIL | 1 | 1 | Registrant email address | TEXT
LOG[0..N] | 0 | N | Verification log | TEXT
NAME | 1 | 1 | Registrant name | TEXT
STATUS | 1 | 1 | Verification status | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusDomainRegistrantVerification
DOMAIN = testdomain-001.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[EMAIL][0] = test@domain.com
PROPERTY[LOG][0] = 2015-07-07 12:30:52 [REQUESTED] Created new registrant verification for Test User <test@domain.com>
PROPERTY[LOG][1] = 2015-07-07 12:32:06 [SEND] verification email to <test@domain.com>
PROPERTY[LOG][2] = 2015-07-07 12:34:09 [SEND] verification email to <test@domain.com>
PROPERTY[LOG][3] = 2015-07-07 12:40:32 [SUCCESSFUL] registrant email verified from remote address 5.9.182.209:36134
PROPERTY[LOG][4] = 2015-07-07 12:41:01 [SUCCESSFUL] 1 domains verified successfully
PROPERTY[NAME][0] = Test User
PROPERTY[STATUS][0] = SUCCESSFUL
EOF
```

----
