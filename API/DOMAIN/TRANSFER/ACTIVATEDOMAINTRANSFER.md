# ActivateDomainTransfer

## DESCRIPTION
There are several cases where the ActivateDomainTransfer command is used:<br>
1. To activate an incoming transfer of a gTLD which requires the approval of the registrant with the respective trigger code which was sent to the registrant by email.
2. To deny an outgoing transfer request of a gTLDs on behalf of the registrant providing the respective trigger code that was sent to the registrant by email.
3. To activate a change of ownership of a gTLD following the ICANN IRTP process.
4. To activate an incoming transfer of a ccTLD e.g. if a fax form is required. This option is only available for registrars using our RegistrarOC system.

If a gTLD transfer or change of ownership is requested and our system sends an email to the registrant then there are a confirmation link and a trigger code included. This link leads to a white-labelled web site which utilizes the ActivateDomainTransfer command to allow the registrant to either accept or reject the transfer request or to approve the change of ownership.

## AVAILABILITY
All users have access to this command. The command is not available for all TLD's.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ActivateDomainTransfer` | COMMAND
DOMAIN | 1 | Name of the domain | DOMAIN
ACTION | 1 | Action to be performed; allowed values are:<br>`REQUEST` Approve an incoming domain transfer request (the transfer will be requested at registry level)<br>`APPROVE` Approve a change of registrant<br>`DENY` Deny an outgoing domain transfer (it will be denied at registry level)  | TEXT
TRIGGER | 0 | trigger code | TEXT

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
506 | Invalid option value
530 | Authentication failed
531 | Authorization failed
541 | Invalid attribute value
545 | Object not found
549 | Command failed

No properties are returned

----
## Example

### Command

```
[COMMAND]
COMMAND = ActivateDomainTransfer
ACTION = REQUEST
DOMAIN = hexodns.com
TRIGGER = 3610360
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
