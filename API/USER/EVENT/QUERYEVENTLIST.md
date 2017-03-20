# QueryEventList

## DESCRIPTION
Query a list of events.

## AVAILABILITY
All users have access to this command. This command does not make sense if your useraccount does not have any subusers.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryEventList` | COMMAND
WIDE | 0 | Returns some more properties if set to `1` | `1` or `0`
FIRST | 0 | Index of the first entry to be returned | INT
LIMIT | 0 | Max. number of entries to be returned, if set to `ONLYLAST` only the latest event will be returned | INT or `ONLYLAST`
CLASS | 0 | Event class, e.g. `DOMAIN_TRANSFER` | PATTERN
SUBCLASS | 0 | Event subclass, e.g. `TRANSFER_SUCCESSFUL` | PATTERN
MINDATE | 0 | First event date to be returned | NULL or TEXT
MAXDATE | 0 | Last event date to be returned | NULL or TEXT
ORDERBY | 0 | Order response by response parameters; switch order by adding `DESC` to response parameter, e.g.: `EVENTDATE` or `EVENTDATEDESC` | `EVENTDATE`, `EVENTDATEDESC` or NULL

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
541 | Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
COUNT | 1 | 1 | The number of entries returned | TEXT
FIRST | 1 | 1 | The index of the first entry | TEXT
LAST | 1 | 1 | The index of the last entry | TEXT
LIMIT | 1 | 1 | The query limit (max. number of entries returned) | TEXT
TOTAL | 1 | 1 | The total number of entries found | TEXT
EVENT[0..N]| 0 | N | The event ID | TEXT
EVENTCLASS[0..N] | 0 | N | The event class (returned if wide = 1) | TEXT
EVENTDATA0[0..N] | 0 | N | Line 1 of the event data (returned if wide = 1) | TEXT
EVENTDATA1[0..N] | 0 | N | Line 2 of the event data (returned if wide = 1) | TEXT
EVENTDATA2[0..N] | 0 | N | Line 3 of the event data (returned if wide = 1) | TEXT
EVENTDATA3[0..N] | 0 | N | Line 4 of the event data (returned if wide = 1) | TEXT
EVENTDATE[0..N] | 0 | N | The event date (returned if wide = 1) | TEXT
EVENTSUBCLASS[0..N] | 0 | N | The event subclass (returned if wide = 1) | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryEventList
LIMIT = 2
MIN_DATE = 2016-10-17 00:00:00
WIDE = 1
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 6
PROPERTY[LAST][0] = 7
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 8
PROPERTY[LIMIT][0] = 2
PROPERTY[EVENT][0] = 22473397
PROPERTY[EVENT][1] = 22473402
PROPERTY[EVENTCLASS][0] = DOMAIN_TRANSFER
PROPERTY[EVENTCLASS][1] = DOMAIN_TRANSFER
PROPERTY[EVENTDATA0][0] = domain:usertransferperiodtest.ag
PROPERTY[EVENTDATA0][1] = domain:usertransferperiodtest.com
PROPERTY[EVENTDATA1][0] =
PROPERTY[EVENTDATA1][1] =
PROPERTY[EVENTDATA2][0] =
PROPERTY[EVENTDATA2][1] =
PROPERTY[EVENTDATA3][0] =
PROPERTY[EVENTDATA3][1] =
PROPERTY[EVENTDATE][0] = 2016-10-17 08:27:40
PROPERTY[EVENTDATE][1] = 2016-10-17 08:29:28
PROPERTY[EVENTSUBCLASS][0] = TRANSFER_PENDING
PROPERTY[EVENTSUBCLASS][1] = TRANSFER_PENDING
EOF
```

----
