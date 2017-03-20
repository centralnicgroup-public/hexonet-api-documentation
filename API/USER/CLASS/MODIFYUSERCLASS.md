# ModifyUserClass

## DESCRIPTION
Create, modify or delete a UserClass. If the UserClass name does not exist, the UserClass is created. If the UserClass has no relations, it is deleted.

## AVAILABILITY
All users have access to this command. This command does not make sense if the executing account does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `ModifyUserClass` | COMMAND
USERCLASS | 1 | Name of the user class | TEXT
FLUSHRELATIONS | 0 | If set to `1`: delete all existing relations | `0` or `1`
RELATION[0..N] | 0 | Relations for the user class | TEXT
ADDRELATION[0..N] | 0 | Adds a specific relation to the user class | TEXT
DELRELATION[0..N] | 0 | Removes a specific relation from the user class| TEXT

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
541 | Invalid attribute value

No properties are returned.

----
## Example

### Command

```
[COMMAND]
COMMAND = ModifyUserClass
RELATION0 = PRICE_CLASS_DOMAIN_COM_ANNUAL:10.00
RELATION1 = PRICE_CLASS_DOMAIN_COM_CURRENCY:USD
RELATION2 = PRICE_CLASS_DOMAIN_COM_RESTORE:50.00
RELATION3 = PRICE_CLASS_DOMAIN_COM_SETUP:0.00
RELATION4 = PRICE_CLASS_DOMAIN_COM_TRANSFER:10.00
USERCLASS = MYNEWPRICECLASS1
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
