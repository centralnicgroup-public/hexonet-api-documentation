# UpgradeWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `UpgradeWebsite` | COMMAND
ID | 1 | ID of the website  | INT
CLASS | 1 | WEEBLY_FREE WEEBLY_STARTER WEEBLY_PRO WEEBLY_BUSINESS WEEBLY_PERFORMANCE | TEXT
PERIOD | 1 | Registration period:<br>`1Y` for 1 year<br>`1M` for 1 month<br>(please note that "Y" and "M" are case sensitive) | PERIOD
ORDER | 0 | Upgrade order action:<br>`CREATE` - create a registration order<br>`REPLACE` - replace a registration order<br>`UPDATE` - update a registration order | `CREATE`, `REPLACE` or `UPDATE`

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
546 | Credit limit exceeded

## Example

### Command

```
[COMMAND]
command=UpgradeWebsite
ID=668763115432430884
CLASS=WEEBLY_STARTER
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
