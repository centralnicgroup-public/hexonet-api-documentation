# QueryOrderList

## DESCRIPTION
This command allows to list the orders, made by a user.

## AVAILABILITY
All users have access to this command.

----
## COMMAND

Parameter | Min | Definition | Type
---- | ---- | ---- | ----
COMMAND | 1 | `QueryOrderList` | COMMAND
CLASS | 0 | List only orders, related to a given object class:<br>`DOMAIN`<br>`DOMAINAPPLICATION`<br>`SSLCERT`<br>`TMCHMARK` | TEXT or NULL
PAYMENTSTATUS | 0 | List only orders with a given status of the order payment:<br>`AUTOACCOUNT`<br>`AUTOINVOICE`<br>`PAID`<br>`UNPAID` | TEXT
USERDEPTH | 0 | Depth of the list:<br>`SELF` (default): return only orders of the user, executing the command | `SELF`, `SUBUSER` or `ALL`
OPERATIONTYPE | 0 | List only orders, related to the given operation type:<br>`CREATE`<br>`RENEW`<br>`RESTORE`<br>`TRADE`<br>`TRANSFER` | TEXT or NULL
OPERATIONTYPE[0..N] | 0 | List only orders, related to the given operation types | TEXT or NULL
ORDERID | 0 | List only orders with a given order ID | INT or NULL
FIRST | 0 | Response list offset | INT or NULL
LIMIT | 0 | Response list length limit | INT or NULL
NOTOTAL | 0 | If set to `1` the total number of found orders will not be returend. This will increase the response time of the command | `0` or `1`

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

Property | Min | Max | Definition | Type
---- | ---- | ---- | ---- | ----
FIRST | 1 | 1 | Index of the first item in the response list | INT
LAST | 1 | 1 | Index of the last item in the response list | INT
COUNT | 1 | 1 | Response list length | INT
TOTAL | 0 | 1 | Total number of records, returned by the query | INT
LIMIT | 1 | 1 | Response list length limit | INT
ACCOUNTINGTYPE[0..N] | 0 | N | Order operation accounting type | TEXT
ACTION[0..N] | 0 | N | Order operation action | TEXT
AMOUNT[0..N] | 0 | N | Number of operations in the respective order | DECIMAL
CREATEDDATE[0..N] | 0 | N | Order creation date | DATETIME
CURRENCY[0..N] | 0 | N | Order currency code | TEXT
CURRENCYCONVERSIONRATE[0..N] | 0 | N | Conversion rate from RELATIONCURRENCY to CURRENCY | DECIMAL
DESCRIPTION[0..N] | 0 | N | Order description | TEXT
ERRORCOUNT[0..N] | 0 | N | Number of failed attempts to execute the respective order; not yet supported by all commands | INT
EXPIRATIONDATE[0..N] | 0 | N | Order expiration date | DATETIME
GROSSPRICE[0..N] | 0 | N | Order gross price | DECIMAL
INVALIDPARAMETERS[0..N] | 0 | N | Command parameters that have been detected as invalid in the respective order | TEXT
LASTRESPONSE[0..N] | 0 | N | Response of the last command, executed according to the respective order | TEXT
LASTRESPONSECODE[0..N] | 0 | N | Response code of the last command, executed according to the respective order  | INT
LASTRESPONSEDESCRIPTION[0..N] | 0 | N | Response description of the last command, executed according to the respective order  | TEXT
MISSINGPARAMETERS[0..N] | 0 | N | Command parameters that have been detected as missing in the respective order | TEXT
OBJECTCLASS[0..N] | 0 | N | Class of the object, related to the order | TEXT
OBJECTID[0..N] | 0 | N | ID of the object, related to the order | TEXT
OPERATIONTYPE[0..N] | 0 | N | Type of the operation, related to the order | TEXT
ORDERCOMMAND[0..N] | 0 | N | API command, related to the order, and its parameters | TEXT
ORDERID[0..N] | 0 | N | Order ID | INT
ORDERSTATUS[0..N] | 0 | N | Order status | TEXT
PAYMENTSTATUS[0..N] | 0 | N | Order payment status | TEXT
PRICE[0..N] | 0 | N | Order price | DECIMAL
PROCESSINGSTATUS[0..N] | 0 | N | Order processing status | TEXT
RELATIONCURRENCY[0..N] | 0 | N | Currency code of the respective relation's price | TEXT
RELATIONGROSSPRICE[0..N] | 0 | N | Respective relation's gross price | DECIMAL
RELATIONPRICE[0..N] | 0 | N | Respective relation's price | DECIMAL
REPOSITORY[0..N] | 0 | N | Respective repository | TEXT
UPDATEDDATE[0..N] | 0 | N | Date of the last order modification | DATETIME
USER[0..N] | 0 | N | Account ID of the respective user | TEXT
VAT[0..N] | 0 | N | VAT in percent | DECIMAL

----
## Example

### Command

```
[COMMAND]
COMMAND = QueryOrderList
LIMIT = 2
EOF
```
### Response

```
[RESPONSE]
CODE = 200
DESCRIPTION = Command completed successfully
PROPERTY[FIRST][0] = 0
PROPERTY[LAST][0] = 1
PROPERTY[COUNT][0] = 2
PROPERTY[TOTAL][0] = 6
PROPERTY[LIMIT][0] = 2
PROPERTY[ACCOUNTINGTYPE][0] = ADD_DOMAIN
PROPERTY[ACCOUNTINGTYPE][1] = TRADE_DOMAIN
PROPERTY[ACTION][0] = EXECUTE
PROPERTY[ACTION][1] = EXECUTE
PROPERTY[AMOUNT][0] = 1.00
PROPERTY[AMOUNT][1] = 1.00
PROPERTY[CREATEDDATE][0] = 2016-11-08 18:00:46
PROPERTY[CREATEDDATE][1] = 2016-11-10 10:15:51
PROPERTY[CURRENCY][0] = EUR
PROPERTY[CURRENCY][1] = EUR
PROPERTY[CURRENCYCONVERSIONRATE][0] = 0.927902
PROPERTY[CURRENCYCONVERSIONRATE][1] = 1
PROPERTY[DESCRIPTION][0] = agapemate.com
PROPERTY[DESCRIPTION][1] = browseshare.info
PROPERTY[ERRORCOUNT][0] = 0
PROPERTY[ERRORCOUNT][1] = 0
PROPERTY[EXPIRATIONDATE][0] = 0000-00-00 00:00:00
PROPERTY[EXPIRATIONDATE][1] = 0000-00-00 00:00:00
PROPERTY[GROSSPRICE][0] = 0.00
PROPERTY[GROSSPRICE][1] = 0.00
PROPERTY[INVALIDPARAMETERS][0] =
PROPERTY[INVALIDPARAMETERS][1] =
PROPERTY[LASTRESPONSE][0] =
PROPERTY[LASTRESPONSE][1] = DESCRIPTION%3dMissing%20required%20attribute%3b%20X%2dCONFIRM%2dDA%2dNEW%2dREGISTRANT%0aQUEUETIME%3d0%0aCODE%3d504%0aRUNTIME%3d0%2e551%0a
PROPERTY[LASTRESPONSECODE][0] =
PROPERTY[LASTRESPONSECODE][1] = 504
PROPERTY[LASTRESPONSEDESCRIPTION][0] =
PROPERTY[LASTRESPONSEDESCRIPTION][1] = Missing required attribute; X-CONFIRM-DA-NEW-REGISTRANT
PROPERTY[MISSINGPARAMETERS][0] =
PROPERTY[MISSINGPARAMETERS][1] =
PROPERTY[OBJECTCLASS][0] = DOMAIN
PROPERTY[OBJECTCLASS][1] = DOMAIN
PROPERTY[OBJECTID][0] = agapemate.com
PROPERTY[OBJECTID][1] = browseshare.info
PROPERTY[OPERATIONTYPE][0] = CREATE
PROPERTY[OPERATIONTYPE][1] = TRADE
PROPERTY[ORDERCOMMAND][0] = OWNERCONTACT0%3dUSER%0aBILLINGCONTACT0%3dUSER%0aCOMMAND%3dAddDOMAIN%0aADMINCONTACT0%3dUSER%0aPERIOD%3d1Y%0aX%2dWHOIS%2dRSP%3dABC%2d123%0aNAMESERVER1%3dns2%2eispapi%2enet%0aTECHCONTACT0%3dUSER%0aINTERNALDNS%3d1%0aX%2dWDRP%2dRSP%3dTest%20GmbH%0aDOMAIN%3dagapemate%2ecom%0aX%2dWHOIS%2dURL%3dhttp%3a%2f%2fcp%2dote%2ehexonet%2enet%0aNAMESERVER0%3dns1%2eispapi%2enet
PROPERTY[ORDERCOMMAND][1] = REPOSITORY%3dINFO%2dOTE%2d1API1%0aREPOSITORYOWNER%3d0%0aACTION%3drequest%0aCOMMAND%3dTradeDomain%0aDOMAIN%3dbrowseshare%2einfo%0aOWNERCONTACT0%3dP%2dBAH1383762
PROPERTY[ORDERID][0] = 34236
PROPERTY[ORDERID][1] = 34278
PROPERTY[ORDERSTATUS][0] = PENDING
PROPERTY[ORDERSTATUS][1] = PENDING
PROPERTY[PAYMENTSTATUS][0] = UNPAID
PROPERTY[PAYMENTSTATUS][1] = UNPAID
PROPERTY[PRICE][0] = 0.00
PROPERTY[PRICE][1] = 0.00
PROPERTY[PROCESSINGSTATUS][0] = INACTIVE
PROPERTY[PROCESSINGSTATUS][1] = INACTIVE
PROPERTY[RELATIONCURRENCY][0] = USD
PROPERTY[RELATIONCURRENCY][1] =
PROPERTY[RELATIONGROSSPRICE][0] = 0.00
PROPERTY[RELATIONGROSSPRICE][1] = 0.00
PROPERTY[RELATIONPRICE][0] = 0.00
PROPERTY[RELATIONPRICE][1] = 0.00
PROPERTY[REPOSITORY][0] = COM-OTE-1API1
PROPERTY[REPOSITORY][1] = INFO-OTE-1API1
PROPERTY[UPDATEDDATE][0] = 2016-11-14 15:45:46
PROPERTY[UPDATEDDATE][1] = 0000-00-00 00:00:00
PROPERTY[USER][0] = test.user
PROPERTY[USER][1] = test.user
PROPERTY[VAT][0] = 19.00
PROPERTY[VAT][1] = 19.00
EOF
```

----
