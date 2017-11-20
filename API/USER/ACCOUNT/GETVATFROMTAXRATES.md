# GetVATFromTaxrates

## DESCRIPTION
Calculate total VAT from one or more tax rates. This is useful when several tax rates need to be combined (e.g. sales tax, county tax, and city tax).

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetVATFromTaxrates` | COMMAND
TAXRATES | 1 | One or more tax rates separated by `+` | TEXT or NULL

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
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
TAXRATESNAME[0..N] | 1 | N | Tax rate name | TEXT
TAXRATESNOMINALRATE[0..N] | 1 | N | Nominal tax rate if specified in `TAXRATES` parameter | TEXT or NULL
TAXRATESRATE[0..N] | 1 | N | Effective tax rate | DECIMAL
VAT | 1 | 1 | Total VAT | DECIMAL

----
## Example

### Command

```
[COMMAND]
COMMAND = GetVATFromTaxrates
TAXRATES = PST~E1.:3.00+GST~E2.:5.00
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[TAXRATESNAME][0] = PST
PROPERTY[TAXRATESNAME][1] = GST
PROPERTY[TAXRATESNOMINALRATE][0] = E1.
PROPERTY[TAXRATESNOMINALRATE][1] = E2.
PROPERTY[TAXRATESRATE][0] = 3.0000
PROPERTY[TAXRATESRATE][1] = 5.0000
PROPERTY[VAT][0] = 8.0000
EOF
```

----
