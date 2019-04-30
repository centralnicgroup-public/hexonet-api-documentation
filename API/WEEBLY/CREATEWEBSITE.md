# CreateWebsite

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CreateWebsite` | COMMAND
DOMAIN | 1 | Name of the domain | DOMAIN
CLASS | 1 | WEEBLY_FREE WEEBLY_STARTER WEEBLY_PRO WEEBLY_BUSINESS WEEBLY_PERFORMANCE | TEXT
WEBSITEUSERID | 1 | ID from response of CreateWebsiteUser  | INT
PERIOD | 1 | Registration period:<br>`1Y` for 1 year<br>`1M` for 1 month<br>(please note that "Y" and "M" are case sensitive) | PERIOD
ORDER | 0 | Registration order action:<br>`CREATE` - create a registration order<br>`REPLACE` - replace a registration order<br>`UPDATE` - update a registration order | `CREATE`, `REPLACE` or `UPDATE`
TITLE | 0 | Title of the website | TEXT
UPGRADEURL | 0 | URL | TEXT
BRANDNAME | 0 | Name of the brand | TEXT
BRANDURL | 0 | URL of the brand | TEXT
REFERENCE | 0 | ID of the source website to be copied from   | INT

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
541 | Invalid attribute value
546 | Credit limit exceeded


Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
ASSIGNEDIP | 1 | 1 | The assigned IP of the website | TEXT
BRANDNAME | 1 | 1 | The name of the brand | TEXT
BRANDURL | 1 | 1 | The URL of the brand | TEXT
DOMAIN | 1 | 1 | The domain name | TEXT
ID | 1 | 1 | The ID of the website | TEXT
SECURE | 1 | 1 | The current secure status of the website | TEXT
STATUS | 1 | 1 | The current status of the website | TEXT
TITLE | 1 | 1 | The title of the website | TEXT
UPGRADEURL | 1 | 1 | The URL to upgrade the website | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND=CreateWebsite
DOMAIN=demowebsite.com
WEBSITEUSERID=125182340
PERIOD=1Y
CLASS=WEEBLY_FREE
TITLE=demowebsite
UPGRADEURL=http://www.demo-weebly.com
BRANDNAME=demo-brand
BRANDURL=http://www.demo-website.com
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[ID][0]=395985628735716414
PROPERTY[ASSIGNEDIP][0]=199.34.228.44
PROPERTY[BRANDNAME][0]=demo-brand
PROPERTY[STATUS][0]=UNPUBLISHED
PROPERTY[BRANDURL][0]=http://www.demo-website.com
PROPERTY[TITLE][0]=demowebsite
PROPERTY[UPGRADEURL][0]=http://www.demo-weebly.com
PROPERTY[DOMAIN][0]=www.demowebsite.com
PROPERTY[SECURE][0]=0
EOF
```

----
