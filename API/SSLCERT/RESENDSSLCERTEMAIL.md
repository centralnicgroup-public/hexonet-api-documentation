# ResendSSLCertEmail

## DESCRIPTION
Resend the order confirmation email.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ResendSSLCertEmail` | COMMAND
SSLCERTID | 1 | The unique object ID number in our system | TEXT
RESENDEMAILTYPE | 0 | Type of email that should be resent; can be `InviteEmail`, `ApproverEmail`, `PickUpEmail`, `FulfillmentEmail`, `PhoneAuthEmail`; the default is: `ApproverEmail` | TEXT or NULL
EMAIL | 0 | Email address to send the email to; if omitted the email address originally used will be used again | TEXT or NULL

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
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ResendSSLCertEmail
RESENDEMAILTYPE = ApproverEmail
SSLCERTID = O112S16YrWze9U9unMjDP
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
