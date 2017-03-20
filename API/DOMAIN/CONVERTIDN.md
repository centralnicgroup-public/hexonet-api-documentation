# ConvertIDN

## DESCRIPTION
This command displays the given domainname(s) in IDN and in ACE.
The domain(s) can be given in both encodings.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ConvertIDN` | COMMAND
DOMAIN[0..N] | 1 | A list of domains which should be converted | TEXT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425 | Service temporarily locked; usage exceeded
503 | Invalid attribute name
504 | Missing required attribute
505 | Invalid attribute value syntax
530 | Authentication failed
531 | Authorization failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
IDN[0..N] | 1 | N | The n-th domain name displayed in Unicode | TEXT
ACE[0..N] | 1 | N | The n-th domain name displayed in ACE | DOMAIN

----
## Example

### Command

```
[COMMAND]
COMMAND = ConvertIdn
DOMAIN0 = äöütest.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACE][0] = xn--test-koa2iub.com
PROPERTY[IDN][0] = äöütest.com
EOF
```

----

