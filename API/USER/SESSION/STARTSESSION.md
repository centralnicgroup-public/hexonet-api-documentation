# StartSession

## DESCRIPTION
Starts a new session for the user executing this command.<br>
The session ID which is returned by this command can be used as the value for the HTTP API parameter 's_session'. Using 's_session' in the HTTP API replaces the otherwise mandatory authentication parameters 's_login' and 's_password'.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StartSession` | COMMAND
TYPE | 0 | The respective session type, default is `API` | TEXT
TIMEOUT | 0 | Defines the number of seconds of inactivity, until a session expires. (min = `60`, max = `3600`, default = `600`) | INT
MAXTTL | 0 | Defines the maximum lifetime of a session in seconds. (min = `60` , max = `86400`, default = `86400`) | INT

----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421	| Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
503 | Invalid attribute name
505 | Invalid attribute value syntax
530	| Authentication failed
531	| Authorization failed
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
SESSION | 1 | 1 | Session ID of the session created | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = StartSession
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[SESSION][0] = QkJUz3wjjLW2AQkJUz3wjjLW2AL55h0r1rMJR9ML55h0r1rMJR9MXvnJMs3Il0sV
EOF
```

----
