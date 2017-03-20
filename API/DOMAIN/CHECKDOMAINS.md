# CheckDomains

## DESCRIPTION
Check a list of domain names for availability.

## AVAILABILITY
Your account must have the TLDs of the domain names within the relations.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `CheckDomains` | COMMAND
DOMAIN[0..N] | 1 | Names of the domains | TEXT
X-IDN-LANGUAGE | 0 | If the domain is a IDN domain, you have to submit the IDN language tag with this parameter (e.g. `DE` for German IDN domains) | TEXT or NULL
DOMAINCHECKMODE | 0 | Switch the mode of doing availability checks. <br>`AUTH` will check against the registry. <br> `DNS` and `RAWDNS` will use the DNS to check but can have false positives.<br> The default is `AUTH`. | `AUTH`, `DNS`, `RAWDNS` or NULL
PHASE | 0 | When stating `claims` in this parameter the command will return if there are claims for this domain. | `claims`, `sunrise` or NULL
PREMIUMCHANNELS | 0 | To check the availability and query further information of premium domains this parameter has to be set to `*` or the respective premium channel | TEXT


----
## RESPONSE

Code | Description
---- | ----
200 | Command completed successfully
420 | Command failed due to server error. Server closing connection
421 | Command failed due to server error. Client should try again
423 | Command failed due to server error. Client should try again (Could not get session)
425	| Service temporarily locked; usage exceeded
503 | Invalid attribute name
505 | Invalid attribute value syntax
530 | Authentication failed
531	| Authorization failed
541	| Invalid attribute value
549 | Command Failed

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
CLASS[0..N] | 0 | N | The class of the domain name if it is a premium domain<br>This class has to be stated when registering the domain | TEXT
CURRENCY[0..N] | 0 | N | The currency of the price for the domain name | TEXT
DOMAINCHECK[0..N] | 1 | N | The result for the N-th domain, in the format:<br>`<code><space><description>` | TEXT
DOMAINCHECKTIME[0..N] | 1 | N | The checktime for the N-th domain | TEXT
PREMIUMCHANNELS[0..N] | 0 | N | The premium channel of the N-th domain | TEXT
PRICE[0..N] | 0 | N | The price of the N-th domain | TEXT
REASON[0..N] | 1 | N | The reason for the availability/unavailability of the domain | TEXT

----
## Example

### Command

```
[COMMAND]
COMMAND = CheckDomains
DOMAIN0 = premium.guru
DOMAIN1 = nonpremium.guru
PREMIUMCHANNELS = *
EOF

```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[CLASS][0] = PREMIUM_DONUTS_Price Category A
PROPERTY[CLASS][1] =
PROPERTY[CURRENCY][0] = USD
PROPERTY[CURRENCY][1] =
PROPERTY[DOMAINCHECK][0] = 211 Premium Domain name available [PREMIUM]
PROPERTY[DOMAINCHECK][1] = 210 Available
PROPERTY[DOMAINCHECKTIME][0] = 0.173
PROPERTY[DOMAINCHECKTIME][1] = 0.173
PROPERTY[PREMIUMCHANNEL][0] = DONUTS
PROPERTY[PREMIUMCHANNEL][1] =
PROPERTY[PRICE][0] = 999.99
PROPERTY[PRICE][1] =
PROPERTY[REASON][0] = Premium Domain Name
PROPERTY[REASON][1] =
EOF
```

----
