# StatusUser

## DESCRIPTION
Query the status properties and relations of a user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusUser` | COMMAND
SUBUSER | 0 | User ID of a subuser for which StatUsuser information is needed.<br>If not provided, then the information related to the user, making the API call, along with all applicable relations will be returned.<br>If provided, then only information related to the indicated subuser will be returned, including its UserClass and only subuser's relations. | TEXT
STATS | 0 | `0` (default): Does not show extra information<br>`1`: Properties SUBUSERSDIRECT and SUBUSERSTOTAL are also shown in the response. | `0` or `1`
RELATIONS | 0 | `0`: The response will not include relations. This is useful if a faster response is needed and relations are not needed.<br>`1` (default): Relations will be returned. | `0` or `1`
PROPERTIES | 0 | `USERINDEX` : Show User Index<br>`PARENTUSERINDEX`: Show Parent Index<br>`USERINDEX PARENTUSERINDEX`: Show both User and Parent Indexes. | TEXT or NULL
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
545 | Object not found

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACCOUNTCREDIT | 1 | 1 | The credit limit for this user (money amount the user can spend bellow a balance of `0`) | DECIMAL
ACCOUNTCURRENCY | 1 | 1 | The currency of this account, e. g. `USD` | TEXT
ACCOUNTCURRENT | 1 | 1 | The current account balance | DECIMAL
ACCOUNTDEPOSIT | 1 | 1 | Amount of the reserved deposits | DECIMAL
ACCOUNTPAYMENT | 1 | 1 | Cumulative total of all payments, made by the user | DECIMAL
ACCOUNTTAXRATES | 1 | 1 | Type and percent of tax(es) | TEXT
ACCOUNTTEMPCREDIT | 1 | 1 | Temporary credit ammount for the user (extends) | DECIMAL
ACCOUNTVAT | 1 | 1 | The VAT for this account in percent (%), e. g. `19.00` | DECIMAL
ACCOUNTVOLUME | 1 | 1 | Cumulative total of all accountings (except of payments) of the user including tax | DECIMAL
ACTIVE | 1 | 1 | `0`: User is not active (cannot log in)<br>`1`: User is active | `0` or `1`
ALLOWEDIP[0..N] | 0 | N | Return a list of ip addresses or subnets which are allowed to access the respective user account. They can be added and managed with the AddUser and ModifyUser command | TEXT
COMMENT | 0 | 1 | Url encoded string which was previously added with the AddUser or ModifyUser command | LONGTEXT
CREATEDDATE | 1 | 1 | Timestamp of when this user was created | DATETIME
OTPSTATUS | 1 | 1 | `ACTIVE`: User has 2-factor authentication activated<br>`INACTIVE`: 2-factor authentication is not active for this user  | `ACTIVE` or `INACTIVE`
PARENTUSER | 1 | 1 | The user ID of the parent user | TEXT
PARENTUSERINDEX | 0 | 1 | 	The current user's parent index | INT
RELATIONDISABLED[0..N] | 0 | N | Type of the n-th user relation if this relation is disabled for the given user | TEXT
RELATIONTYPE[0..N] | 0 | N | Type of the n-th user relation | TEXT
RELATIONVALUE[0..N] | 0 | N | Value of the n-th user relation | TEXT
SUBUSERSDIRECT | 0 | 1 | The number of direct subusers | INT
SUBUSERSTOTAL | 0 | 1 | 	The number of all subusers | INT
UPDATEDDATE | 1 | 1 | Timestamp of when this user information was updated | DATETIME
USER | 1 | 1 | The user ID the information belongs to | TEXT
USERCLASS | 0 | 1 | The name of the price class that the user belongs to | TEXT or NULL
USERINDEX | 0 | 1 | 	The current user index | INT

----
## Example

### Command

```
[COMMAND]
COMMAND = StatusUser
RELATIONS = 0
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ACCOUNTCREDIT][0] = 1000000.00
PROPERTY[ACCOUNTCURRENCY][0] = EUR
PROPERTY[ACCOUNTCURRENT][0] = 218797.05
PROPERTY[ACCOUNTDEPOSIT][0] = 1624.71
PROPERTY[ACCOUNTPAYMENT][0] = 1428114.28
PROPERTY[ACCOUNTTAXRATES][0] = MwSt:19.00
PROPERTY[ACCOUNTTEMPCREDIT][0] = 0.00
PROPERTY[ACCOUNTVAT][0] = 19.00
PROPERTY[ACCOUNTVOLUME][0] = 2744424.67
PROPERTY[ACTIVE][0] = 1
PROPERTY[CREATEDDATE][0] = 2008-10-27 15:16:40
PROPERTY[OTPSTATUS][0] = INACTIVE
PROPERTY[PARENTUSER][0] = demo.hexonet.net
PROPERTY[UPDATEDDATE][0] = 2016-08-17 07:16:14
PROPERTY[USER][0] = test.user
EOF
```
