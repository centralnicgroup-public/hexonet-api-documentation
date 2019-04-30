# StatusWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `StatusWebsite` | COMMAND
ID | 1 | ID of the website  | INT

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
531 | Authorization failed
540 | Attribute value is not unique
541 | Invalid attribute value
545 | Object not found
549 | Command Failed


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ACCOUNTINGDATE | 1 | 1 | The website's accounting date | DATETIME
ACCOUNTINGPERIOD | 1 | 1 | The website's accounting period | TEXT
ASSIGNEDIP | 1 | 1 | The IP assigned to the website | TEXT
BRANDNAME | 0 | 1 | The name of the brand | TEXT
BRANDURL | 0 | 1 | The URL of the brand | TEXT
CLASS | 1 | 1 | Class of the object, returns `WEBSITE` in case of a website | TEXT
CREATEDDATE | 1 | 1 | The creation date of the website | DATETIME
DESCRIPTION | 1 | 1 | The URL of the website | TEXT
EXPIRATIONDATE | 1 | 1 | The expiration date of the website | DATETIME
FAILUREDATE | 1 | 1 | The website's failure date | DATETIME
FAILUREPERIOD | 1 | 1 | The website's failure period | TEXT
FINALIZATIONDATE | 1 | 1 | The website's finalization date | DATETIME
FINALIZATIONPERIOD | 1 | 1 | The website's finalization period | TEXT
ID | 1 | 1 | The ID of the website | TEXT
NEXTACTION | 1 | 1 | Indicates what will happen to the website next, e.g. `expire` when the website is set to AUTOEXPIRE | TEXT
NEXTACTIONDATE | 1 | 1 | The date when the next action will be taken | DATETIME
PEERUSER | 1 | 1 | String with all users in the user chain | TEXT
PREPAIDPERIOD | 1 | 1 | The website's prepaid period | TEXT
PAIDUNTILDATE | 1 | 1 | The date until the website is paid in the HEXONET renewal system | DATETIME
RENEWALMODE | 1 | 1 | Indicates how the website will be renewed | TEXT
RENEWALPERIOD | 1 | 1 | The website's renewal period | TEXT
REPOSITORY | 1 | 1 | The website's repository | TEXT
REPOSITORYPEERUSER | 0 | 1 | The repository peer user | TEXT
SECURE | 1 | 1 | The secure status of the website | TEXT
STATUS | 1 | N | The current registration status | TEXT
SUBCLASS | 1 | 1 | Subclass of the website | TEXT
TITLE | 1 | 1 | The title of the website | TEXT
UPDATEDDATE | 1 | 1 | Last modification date of the website | DATETIME
UPGRADEURL | 0 | 1 | The URL of the upgrade page | TEXT
USER | 1 | 1 | The user that manages this website | TEXT
WEBSITEUSERID | 1 | 1 | The ID of the website user | TEXT

## Example

### Command

```
[COMMAND]
COMMAND = StatusWebsite
ID = 395985628735716414
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CREATEDDATE][0]=2019-04-12 12:33:10
PROPERTY[FINALIZATIONDATE][0]=2021-04-10 12:33:10
PROPERTY[NEXTACTION][0]=expire
PROPERTY[STATUS][0]=UNPUBLISHED
PROPERTY[BRANDURL][0]=http://www.demo-website.com
PROPERTY[ACCOUNTINGPERIOD][0]=-7d
PROPERTY[FAILUREDATE][0]=2021-04-10 12:33:10
PROPERTY[RENEWALMODE][0]=AUTOEXPIRE
PROPERTY[USER][0]=karches-weebly
PROPERTY[SECURE][0]=0
PROPERTY[NEXTACTIONDATE][0]=2021-04-10 12:33:10
PROPERTY[FINALIZATIONPERIOD][0]=-1d
PROPERTY[EXPIRATIONDATE][0]=2021-04-11 12:33:10
PROPERTY[ASSIGNEDIP][0]=199.34.228.44
PROPERTY[SUBCLASS][0]=WEEBLY_FREE
PROPERTY[PREPAIDPERIOD][0]=0
PROPERTY[UPDATEDDATE][0]=2019-04-12 13:10:28
PROPERTY[TITLE][0]=demowebsite
PROPERTY[DESCRIPTION][0]=demowebsite.com
PROPERTY[WEBSITEUSERID][0]=125182340
PROPERTY[ID][0]=395985628735716414
PROPERTY[PEERUSER][0]=
PROPERTY[BRANDNAME][0]=demo-brand
PROPERTY[PAIDUNTILDATE][0]=2021-04-11 12:33:10
PROPERTY[UPGRADEURL][0]=http://www.demo-weebly.com
PROPERTY[RENEWALPERIOD][0]=1Y
PROPERTY[FAILUREPERIOD][0]=-1d
PROPERTY[CLASS][0]=WEBSITE
PROPERTY[ACCOUNTINGDATE][0]=2021-04-04 12:33:10
PROPERTY[REPOSITORY][0]=125182340
PROPERTY[REPOSITORYPEERUSER][0]=
EOF
```

----
