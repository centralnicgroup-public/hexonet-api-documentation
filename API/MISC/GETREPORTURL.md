# GetReportURL

## DESCRIPTION
This command allows to get different lists in CSV format, e.g. a daily created list of domain names or subusers. It returns a unique URL for each requested report, so the reports can be downloaded by the user. For security reasons the URL will only be accepted within a short period of time.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `GetReportURL` | COMMAND
FILE | 1 | Report name:<br>`domains.csv` - list of domain names, which belong to the user, executing the command, and its subusers. This list created on a daily basis<br>`users.csv` - subusers list of the user, executing the command. This list created on a daily basis | TEXT
USERDEPTH | 0 | Depth of the list, may be `SELF`, `SUBUSER` or `ALL` | `SELF`, `SUBUSER` or `ALL`

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
URL | 0 | 1 | Report download link | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = GetReportURL
FILE = domains.csv
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[URL][0] = https://reports.ispapi.net/dump/b89939772f8dfb6070064fe95569b41f/582c1656/test/659/domains.csv
EOF
```

----
