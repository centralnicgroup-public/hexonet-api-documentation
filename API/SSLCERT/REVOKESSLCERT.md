# RevokeSSLCert

## DESCRIPTION
Revoke an SSL certificate making it invalid.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `RevokeSSLCert` | COMMAND
SSLCERTID | 1 | The unique object ID number in our system | TEXT
REASON | 1 | Reason why the certificate should be revoked | TEXT

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
COMMAND = RevokeSSLCert
REASON = key compromise
SSLCERTID = OZhy4GvisumSXvPCPMfC6
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
