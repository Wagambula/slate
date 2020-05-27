# Invoice

By definition, an invoice is a list of goods sent or services provided, with a statement of the sum due for these. In the SCM application, it contains the following parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
invoiceName | string | the name of the invoice
shipmentId | int | the id of the shipment
invoiceDate | datestring | the date of issuance the invoice
invoiceDueDate | datestring | the date in which the invoice payment is due
invoiceTypeId | int | the id of the invoice type
remarks | string | the remarks regarding the invoice
isDeleted | boolean | checks whether a invoice is deleted or not
deleterUserId | int | the id of the user who deletes an invoice
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the invoice was created
creatorUserId | int | the id of the user who created that invoice
id | int | the id of the invoice

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "invoiceName": " ", "shipmentId": " ", "invoiceDate": " ", "invoiceDueDate": " ", "invoiceTypeId": " ", "remarks": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"invoiceName\": \" \",\n    \"shipmentId\": \" \",\n    \"invoiceDate\": \" \",\n    \"invoiceDueDate\": \" \",\n    \"invoiceTypeId\": \" \",\n    \"remarks\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"invoiceName\": \" \",\n    \"shipmentId\": \" \",\n    \"invoiceDate\": \" \",\n    \"invoiceDueDate\": \" \",\n    \"invoiceTypeId\": \" \",\n    \"remarks\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "invoiceName": " ",
    "shipmentId": 0,
    "invoiceDate": " ",
    "invoiceDueDate": " ",
    "invoiceTypeId": 0,
    "remarks": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "invoiceName": "string",
  "shipmentId": 0,
  "invoiceDate": "2020-05-20T10:58:52.176Z",
  "invoiceDueDate": "2020-05-20T10:58:52.177Z",
  "invoiceTypeId": 0,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T10:58:52.177Z",
  "lastModificationTime": "2020-05-20T10:58:52.177Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T10:58:52.177Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/Invoice/CreateAsync/`

## Delete

This endpoint allows you to delete particular invoice from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Invoice/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "invoiceName": "string",
  "shipmentId": 0,
  "invoiceDate": "2020-05-20T11:09:15.084Z",
  "invoiceDueDate": "2020-05-20T11:09:15.084Z",
  "invoiceTypeId": 0,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T11:09:15.084Z",
  "lastModificationTime": "2020-05-20T11:09:15.084Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T11:09:15.084Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the invoice to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "invoiceName": "string",
    "shipmentId": 0,
    "invoiceDate": "2020-05-20T11:14:16.286Z",
    "invoiceDueDate": "2020-05-20T11:14:16.286Z",
    "invoiceTypeId": 0,
    "remarks": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T11:14:16.286Z",
    "lastModificationTime": "2020-05-20T11:14:16.286Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T11:14:16.286Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the invoices.

### HTTP Request

`POST /api/services/app/Invoice/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"invoiceName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Invoice/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"invoiceName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "invoiceName": "nothing",
  "shipmentId": 0,
  "invoiceDate": "2020-05-20T11:14:11.294Z",
  "invoiceDueDate": "2020-05-20T11:14:11.294Z",
  "invoiceTypeId": 0,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T11:14:11.294Z",
  "lastModificationTime": "2020-05-20T11:14:11.294Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T11:14:11.294Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Invoice Type

The invoice Type section shows the various types of invoices.

### Field

Parameter | Type | Description
--------- | ------- | --------
invoiceTypeName | string | the name of the invoice type
description | string | details regarding the invoice type
isDeleted | boolean | checks whether an invoice type is deleted or not
deleterUserId | int | the id of the user who deletes an invoice type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the invoice type was created
creatorUserId | int | the id of the user who created the invoice type
id | int | the id of the invoice type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"InvoiceType": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"invoiceTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"invoiceTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "invoiceTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "invoiceTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T11:25:09.553Z",
  "lastModificationTime": "2020-05-20T11:25:09.553Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T11:25:09.553Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates the invoice type.

### HTTP Request

`POST /api/services/app/InvoiceType/CreateAsync/`

## Delete

This endpoint allows you to delete particular invoice type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/InvoiceType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "invoiceTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T11:25:09.312Z",
  "lastModificationTime": "2020-05-20T11:25:09.312Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T11:25:09.312Z",
  "creatorUserId": 0,
  "id": 0
}
``

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the invoice type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "invoiceTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T11:25:09.317Z",
    "lastModificationTime": "2020-05-20T11:25:09.317Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T11:25:09.317Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the invoice types.

### HTTP Request

`POST /api/services/app/InvoiceType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"invoiceTypeName\": \"nothing\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/InvoiceType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"invoiceTypeName\": \"nothing\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "invoiceTypeName": "nothing",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T11:11:22.404Z",
  "lastModificationTime": "2020-05-20T11:11:22.404Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T11:11:22.404Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Loan Details

The loan detail shows any information concerning the procedures to acquire a loan, terms and conditions...

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
loanId | int | the id of the loan
productId | int | the id of the product
unitPrice | double | the price for a unit quantity of a product
amount | double | the amount for the loan
loan | class | entails details regarding the loan
isDeleted | boolean | checks whether the loan detail is deleted or not
deleterUserId | int | the id of the user who deletes the loan detail
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the loan detail was created
creatorUserId | int | the id of the user who created that loan detail
id | int | the id of the loan detail

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "loanId": " ", "productId": " ", "unitPrice": " ", "amount": " ", "loans": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"loanId\": \" \",\n    \"productId\": \" \",\n    \"unitPrice\": \" \",\n    \"amount\": \" \",\n    \"loans\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"loanId\": \" \",\n    \"productId\": \" \",\n    \"unitPrice\": \" \",\n    \"amount\": \" \",\n    \"loans\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "loanId": 0,
    "productId": 0,
    "unitPrice": " ",
    "amount": " ",
    "loans": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "loanId": 0,
  "productId": 0,
  "unitPrice": 0,
  "amount": 0,
  "loans": {
    "tenantId": 0,
    "loanDate": "2020-05-20T12:53:25.708Z",
    "totalAmount": 0,
    "dueDate": "2020-05-20T12:53:25.708Z",
    "customerId": 0,
    "customer": {
      "tenantId": 0,
      "customerName": "string",
      "customerTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "idNumber": "string",
      "idType": "string",
      "accountType": "string",
      "xcoordinate": 0,
      "ycoordinate": 0,
      "accountNumber": 0,
      "referenceNumber": 0,
      "imagelocation": "string",
      "website": "string",
      "industry": "string",
      "rating": "string",
      "phoneAlternative": "string",
      "countryId": 0,
      "country": {
        "tenantId": 0,
        "countryName": "string",
        "countryZone": "string",
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T12:53:25.709Z",
        "lastModificationTime": "2020-05-20T12:53:25.709Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T12:53:25.709Z",
        "creatorUserId": 0,
        "id": 0
      },
      "parent_CustomerId_Id": 0,
      "email2": "string",
      "ownership": "string",
      "taxId": "string",
      "vatNo": "string",
      "gender": "string",
      "accounts": [
        {
          "customerId": 0,
          "parentAccountId": 0,
          "tenantId": 0,
          "totalLoanAmount": 0,
          "totalAmountPaid": 0,
          "balance": 0,
          "is_Open": true,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T12:53:25.709Z",
          "lastModificationTime": "2020-05-20T12:53:25.709Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T12:53:25.709Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T12:53:25.709Z",
      "lastModificationTime": "2020-05-20T12:53:25.709Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T12:53:25.709Z",
      "creatorUserId": 0,
      "id": 0
    },
    "loanDetails": [
      {
        "tenantId": 0,
        "loanId": 0,
        "productId": 0,
        "unitPrice": 0,
        "amount": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T12:53:25.710Z",
        "lastModificationTime": "2020-05-20T12:53:25.710Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T12:53:25.710Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T12:53:25.710Z",
    "lastModificationTime": "2020-05-20T12:53:25.710Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T12:53:25.710Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T12:53:25.710Z",
  "lastModificationTime": "2020-05-20T12:53:25.710Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T12:53:25.710Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/LoanDetails/CreateAsync/`

## Delete

This endpoint allows you to delete particular loan detail from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/LoanDetail/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "loanId": 0,
  "productId": 0,
  "unitPrice": 0,
  "amount": 0,
  "loans": {
    "tenantId": 0,
    "loanDate": "2020-05-20T13:13:03.207Z",
    "totalAmount": 0,
    "dueDate": "2020-05-20T13:13:03.207Z",
    "customerId": 0,
    "customer": {
      "tenantId": 0,
      "customerName": "string",
      "customerTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "idNumber": "string",
      "idType": "string",
      "accountType": "string",
      "xcoordinate": 0,
      "ycoordinate": 0,
      "accountNumber": 0,
      "referenceNumber": 0,
      "imagelocation": "string",
      "website": "string",
      "industry": "string",
      "rating": "string",
      "phoneAlternative": "string",
      "countryId": 0,
      "country": {
        "tenantId": 0,
        "countryName": "string",
        "countryZone": "string",
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:13:03.207Z",
        "lastModificationTime": "2020-05-20T13:13:03.207Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:13:03.207Z",
        "creatorUserId": 0,
        "id": 0
      },
      "parent_CustomerId_Id": 0,
      "email2": "string",
      "ownership": "string",
      "taxId": "string",
      "vatNo": "string",
      "gender": "string",
      "accounts": [
        {
          "customerId": 0,
          "parentAccountId": 0,
          "tenantId": 0,
          "totalLoanAmount": 0,
          "totalAmountPaid": 0,
          "balance": 0,
          "is_Open": true,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T13:13:03.208Z",
          "lastModificationTime": "2020-05-20T13:13:03.208Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T13:13:03.208Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:13:03.208Z",
      "lastModificationTime": "2020-05-20T13:13:03.208Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:13:03.208Z",
      "creatorUserId": 0,
      "id": 0
    },
    "loanDetails": [
      {
        "tenantId": 0,
        "loanId": 0,
        "productId": 0,
        "unitPrice": 0,
        "amount": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:13:03.208Z",
        "lastModificationTime": "2020-05-20T13:13:03.208Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:13:03.208Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:13:03.208Z",
    "lastModificationTime": "2020-05-20T13:13:03.208Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:13:03.208Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T13:13:03.208Z",
  "lastModificationTime": "2020-05-20T13:13:03.208Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T13:13:03.208Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the loan detail to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "loanId": 0,
    "productId": 0,
    "unitPrice": 0,
    "amount": 0,
    "loans": {
      "tenantId": 0,
      "loanDate": "2020-05-20T13:13:00.719Z",
      "totalAmount": 0,
      "dueDate": "2020-05-20T13:13:00.719Z",
      "customerId": 0,
      "customer": {
        "tenantId": 0,
        "customerName": "string",
        "customerTypeId": 0,
        "address": "string",
        "city": "string",
        "state": "string",
        "zipCode": "string",
        "phone": "string",
        "email": "string",
        "contactPerson": "string",
        "idNumber": "string",
        "idType": "string",
        "accountType": "string",
        "xcoordinate": 0,
        "ycoordinate": 0,
        "accountNumber": 0,
        "referenceNumber": 0,
        "imagelocation": "string",
        "website": "string",
        "industry": "string",
        "rating": "string",
        "phoneAlternative": "string",
        "countryId": 0,
        "country": {
          "tenantId": 0,
          "countryName": "string",
          "countryZone": "string",
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T13:13:00.720Z",
          "lastModificationTime": "2020-05-20T13:13:00.720Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T13:13:00.720Z",
          "creatorUserId": 0,
          "id": 0
        },
        "parent_CustomerId_Id": 0,
        "email2": "string",
        "ownership": "string",
        "taxId": "string",
        "vatNo": "string",
        "gender": "string",
        "accounts": [
          {
            "customerId": 0,
            "parentAccountId": 0,
            "tenantId": 0,
            "totalLoanAmount": 0,
            "totalAmountPaid": 0,
            "balance": 0,
            "is_Open": true,
            "isDeleted": true,
            "deleterUserId": 0,
            "deletionTime": "2020-05-20T13:13:00.721Z",
            "lastModificationTime": "2020-05-20T13:13:00.721Z",
            "lastModifierUserId": 0,
            "creationTime": "2020-05-20T13:13:00.721Z",
            "creatorUserId": 0,
            "id": 0
          }
        ],
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:13:00.721Z",
        "lastModificationTime": "2020-05-20T13:13:00.721Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:13:00.721Z",
        "creatorUserId": 0,
        "id": 0
      },
      "loanDetails": [
        {
          "tenantId": 0,
          "loanId": 0,
          "productId": 0,
          "unitPrice": 0,
          "amount": 0,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T13:13:00.721Z",
          "lastModificationTime": "2020-05-20T13:13:00.721Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T13:13:00.721Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:13:00.721Z",
      "lastModificationTime": "2020-05-20T13:13:00.721Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:13:00.721Z",
      "creatorUserId": 0,
      "id": 0
    },
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:13:00.721Z",
    "lastModificationTime": "2020-05-20T13:13:00.721Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:13:00.721Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all records of loan details.

### HTTP Request

`POST /api/services/app/LoanDetails/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"loanId\": \"6\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/LoanDetails/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"loanId\": \"6\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "loanId": 6,
  "productId": 0,
  "unitPrice": 0,
  "amount": 0,
  "loans": {
    "tenantId": 0,
    "loanDate": "2020-05-20T13:12:44.430Z",
    "totalAmount": 0,
    "dueDate": "2020-05-20T13:12:44.430Z",
    "customerId": 0,
    "customer": {
      "tenantId": 0,
      "customerName": "string",
      "customerTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "idNumber": "string",
      "idType": "string",
      "accountType": "string",
      "xcoordinate": 0,
      "ycoordinate": 0,
      "accountNumber": 0,
      "referenceNumber": 0,
      "imagelocation": "string",
      "website": "string",
      "industry": "string",
      "rating": "string",
      "phoneAlternative": "string",
      "countryId": 0,
      "country": {
        "tenantId": 0,
        "countryName": "string",
        "countryZone": "string",
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:12:44.431Z",
        "lastModificationTime": "2020-05-20T13:12:44.431Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:12:44.431Z",
        "creatorUserId": 0,
        "id": 0
      },
      "parent_CustomerId_Id": 0,
      "email2": "string",
      "ownership": "string",
      "taxId": "string",
      "vatNo": "string",
      "gender": "string",
      "accounts": [
        {
          "customerId": 0,
          "parentAccountId": 0,
          "tenantId": 0,
          "totalLoanAmount": 0,
          "totalAmountPaid": 0,
          "balance": 0,
          "is_Open": true,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T13:12:44.431Z",
          "lastModificationTime": "2020-05-20T13:12:44.431Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T13:12:44.431Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:12:44.431Z",
      "lastModificationTime": "2020-05-20T13:12:44.431Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:12:44.431Z",
      "creatorUserId": 0,
      "id": 0
    },
    "loanDetails": [
      {
        "tenantId": 0,
        "loanId": 0,
        "productId": 0,
        "unitPrice": 0,
        "amount": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:12:44.431Z",
        "lastModificationTime": "2020-05-20T13:12:44.431Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:12:44.431Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:12:44.431Z",
    "lastModificationTime": "2020-05-20T13:12:44.431Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:12:44.431Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T13:12:44.431Z",
  "lastModificationTime": "2020-05-20T13:12:44.431Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T13:12:44.431Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Loans

In the loan section, we find details about a specific loan from a specific client

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
loanDate | datestring | the date on which the loan was issued
totalAmount | double | the total amount borrowed by the client
dueDate | datestring | the date on which the client is supposed to pay back the loan
customerId | int | the id of the customer
customer | class | entails details regarding the customer
isDeleted | boolean | checks whether the loan is deleted or not
deleterUserId | int | the id of the user who deletes the loan detail
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the loan  was created
creatorUserId | int | the id of the user who created that loan 
id | int | the id of the loan 

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "loanDate": " ", "totalAmount": " ", "dueDate": " ", "customerId": " ", "customer": " ",  "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"loanDate\": \" \",\n    \"totalAmount\": \" \",\n    \"dueDate\": \" \",\n    \"customerId\": \" \",\n    \"customer\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"loanDate\": \" \",\n    \"totalAmount\": \" \",\n    \"dueDate\": \" \",\n    \"customerId\": \" \",\n    \"customer\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "loanDate": " ",
    "totalAmount": " ",
    "dueDate": " ",
    "customerId": " ",
    "customer": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "loanDate": "2020-05-20T13:22:11.759Z",
  "totalAmount": 0,
  "dueDate": "2020-05-20T13:22:11.759Z",
  "customerId": 0,
  "customer": {
    "tenantId": 0,
    "customerName": "string",
    "customerTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "idNumber": "string",
    "idType": "string",
    "accountType": "string",
    "xcoordinate": 0,
    "ycoordinate": 0,
    "accountNumber": 0,
    "referenceNumber": 0,
    "imagelocation": "string",
    "website": "string",
    "industry": "string",
    "rating": "string",
    "phoneAlternative": "string",
    "countryId": 0,
    "country": {
      "tenantId": 0,
      "countryName": "string",
      "countryZone": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:22:11.760Z",
      "lastModificationTime": "2020-05-20T13:22:11.760Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:22:11.760Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "accounts": [
      {
        "customerId": 0,
        "parentAccountId": 0,
        "tenantId": 0,
        "totalLoanAmount": 0,
        "totalAmountPaid": 0,
        "balance": 0,
        "is_Open": true,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:22:11.760Z",
        "lastModificationTime": "2020-05-20T13:22:11.760Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:22:11.760Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:22:11.760Z",
    "lastModificationTime": "2020-05-20T13:22:11.760Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:22:11.760Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T13:22:11.760Z",
  "lastModificationTime": "2020-05-20T13:22:11.761Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T13:22:11.761Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/Loans/CreateAsync/`

## Delete

This endpoint allows you to delete particular loan from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Loans/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "loanDate": "2020-05-20T13:41:53.878Z",
  "totalAmount": 0,
  "dueDate": "2020-05-20T13:41:53.878Z",
  "customerId": 0,
  "customer": {
    "tenantId": 0,
    "customerName": "string",
    "customerTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "idNumber": "string",
    "idType": "string",
    "accountType": "string",
    "xcoordinate": 0,
    "ycoordinate": 0,
    "accountNumber": 0,
    "referenceNumber": 0,
    "imagelocation": "string",
    "website": "string",
    "industry": "string",
    "rating": "string",
    "phoneAlternative": "string",
    "countryId": 0,
    "country": {
      "tenantId": 0,
      "countryName": "string",
      "countryZone": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:41:53.878Z",
      "lastModificationTime": "2020-05-20T13:41:53.878Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:41:53.878Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "accounts": [
      {
        "customerId": 0,
        "parentAccountId": 0,
        "tenantId": 0,
        "totalLoanAmount": 0,
        "totalAmountPaid": 0,
        "balance": 0,
        "is_Open": true,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:41:53.879Z",
        "lastModificationTime": "2020-05-20T13:41:53.879Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:41:53.879Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:41:53.879Z",
    "lastModificationTime": "2020-05-20T13:41:53.879Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:41:53.879Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T13:41:53.879Z",
  "lastModificationTime": "2020-05-20T13:41:53.879Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T13:41:53.879Z",
  "creatorUserId": 0,
  "id": 0,
  "loanId": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the loan to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "loanDate": "2020-05-20T13:41:55.329Z",
    "totalAmount": 0,
    "dueDate": "2020-05-20T13:41:55.329Z",
    "customerId": 0,
    "customer": {
      "tenantId": 0,
      "customerName": "string",
      "customerTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "idNumber": "string",
      "idType": "string",
      "accountType": "string",
      "xcoordinate": 0,
      "ycoordinate": 0,
      "accountNumber": 0,
      "referenceNumber": 0,
      "imagelocation": "string",
      "website": "string",
      "industry": "string",
      "rating": "string",
      "phoneAlternative": "string",
      "countryId": 0,
      "country": {
        "tenantId": 0,
        "countryName": "string",
        "countryZone": "string",
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:41:55.329Z",
        "lastModificationTime": "2020-05-20T13:41:55.329Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:41:55.329Z",
        "creatorUserId": 0,
        "id": 0
      },
      "parent_CustomerId_Id": 0,
      "email2": "string",
      "ownership": "string",
      "taxId": "string",
      "vatNo": "string",
      "gender": "string",
      "accounts": [
        {
          "customerId": 0,
          "parentAccountId": 0,
          "tenantId": 0,
          "totalLoanAmount": 0,
          "totalAmountPaid": 0,
          "balance": 0,
          "is_Open": true,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-20T13:41:55.329Z",
          "lastModificationTime": "2020-05-20T13:41:55.329Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T13:41:55.329Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:41:55.329Z",
      "lastModificationTime": "2020-05-20T13:41:55.329Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:41:55.329Z",
      "creatorUserId": 0,
      "id": 0
    },
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:41:55.330Z",
    "lastModificationTime": "2020-05-20T13:41:55.330Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:41:55.330Z",
    "creatorUserId": 0,
    "id": 0,
    "loanId": 0
  }
]
```

This endpoint will list all the loans.

### HTTP Request

`POST /api/services/app/Loans/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"totalAmount\": \"500\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Loans/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"totalAmount\": \"500\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "loanDate": "2020-05-20T13:54:05.942Z",
  "totalAmount": 500,
  "dueDate": "2020-05-20T13:54:05.942Z",
  "customerId": 0,
  "customer": {
    "tenantId": 0,
    "customerName": "string",
    "customerTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "idNumber": "string",
    "idType": "string",
    "accountType": "string",
    "xcoordinate": 0,
    "ycoordinate": 0,
    "accountNumber": 0,
    "referenceNumber": 0,
    "imagelocation": "string",
    "website": "string",
    "industry": "string",
    "rating": "string",
    "phoneAlternative": "string",
    "countryId": 0,
    "country": {
      "tenantId": 0,
      "countryName": "string",
      "countryZone": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T13:54:05.943Z",
      "lastModificationTime": "2020-05-20T13:54:05.943Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T13:54:05.943Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "accounts": [
      {
        "customerId": 0,
        "parentAccountId": 0,
        "tenantId": 0,
        "totalLoanAmount": 0,
        "totalAmountPaid": 0,
        "balance": 0,
        "is_Open": true,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T13:54:05.943Z",
        "lastModificationTime": "2020-05-20T13:54:05.943Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T13:54:05.943Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T13:54:05.943Z",
    "lastModificationTime": "2020-05-20T13:54:05.943Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T13:54:05.943Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T13:54:05.943Z",
  "lastModificationTime": "2020-05-20T13:54:05.943Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T13:54:05.943Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Payment Receive

If payments for the products and services have been made, the information of the that transaction is stored in this section.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
paymentReceiveName | string | the name of the payment which has been effected
invoiceId | int | the id of the invoice
paymentDate | datestring | the date when payments are made
paymentTypeId | int | the id of the payment type
paymentAmount | double | the amount which has been paid
isFullPayment | bool | the flag showing if the amount has been paid in full
invoiceAmount | double | the amount of the invoice
isDeleted | boolean | checks whether a payment received record is deleted or not
deleterUserId | int | the id of the user who deletes a record of payment receieve
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the payment receive was created
creatorUserId | int | the id of the user who created that payment receive
id | int | the id of the payment receive

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "paymentReceiveName": " ", "invoiceId": " ", "paymentDate": " ", "paymentTypeId": " ", "paymentAmount": " ", "isFullPayment": " ", "invoiceAmount": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"paymentReceiveName\": \" \",\n    \"invoiceId\": \" \",\n    \"paymentDate\": \" \",\n    \"paymentTypeId\": \" \",\n    \"paymentAmount\": \" \",\n    \"isFullPayment\": \" \",\n    \"invoiceAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"paymentReceiveName\": \" \",\n    \"invoiceId\": \" \",\n    \"paymentDate\": \" \",\n    \"paymentTypeId\": \" \",\n    \"paymentAmount\": \" \",\n    \"isFullPayment\": \" \",\n    \"invoiceAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "paymentReceiveName": " ",
    "invoiceId": 0,
    "paymentDate": " ",
    "paymentTypeId": 0,
    "paymentAmount": 0,
    "isFullPayment": 1,
    "invoiceAmount": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "paymentReceiveName": "string",
  "invoiceId": 0,
  "paymentDate": "2020-05-20T17:35:14.645Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "isFullPayment": true,
  "invoiceAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T17:35:14.645Z",
  "lastModificationTime": "2020-05-20T17:35:14.645Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T17:35:14.645Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a record of payment receive.

### HTTP Request

`POST /api/services/app/PaymentReceive/CreateAsync/`

## Delete

This endpoint allows you to delete particular record of payment receive from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PaymentReceive/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "paymentReceiveName": "string",
  "invoiceId": 0,
  "paymentDate": "2020-05-20T17:35:36.391Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "isFullPayment": true,
  "invoiceAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T17:35:36.391Z",
  "lastModificationTime": "2020-05-20T17:35:36.391Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T17:35:36.391Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the payment receive to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "paymentReceiveName": "string",
    "invoiceId": 0,
    "paymentDate": "2020-05-20T17:35:36.397Z",
    "paymentTypeId": 0,
    "paymentAmount": 0,
    "isFullPayment": true,
    "invoiceAmount": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T17:35:36.397Z",
    "lastModificationTime": "2020-05-20T17:35:36.397Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T17:35:36.397Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the payment receive records.

### HTTP Request

`POST /api/services/app/PaymentReceive/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"50\",\n    \"paymentReceiveName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentReceive/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"50\",\n    \"paymentReceiveName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 50,
  "paymentReceiveName": "nothing",
  "invoiceId": 0,
  "paymentDate": "2020-05-20T17:35:36.744Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "isFullPayment": true,
  "invoiceAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T17:35:36.744Z",
  "lastModificationTime": "2020-05-20T17:35:36.744Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T17:35:36.744Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Payment Type

This section shows the types of payment for different transactions.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
paymentTypeName | string | the name of the payment type
description | string | details regarding the payment type
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a case
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the payment type was created
creatorUserId | int | the id of the user who created that payment type
id | int | the id of the payment type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "paymentTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"paymentTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"paymentTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "paymentTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "paymentTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:12:10.283Z",
  "lastModificationTime": "2020-05-20T18:12:10.283Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:12:10.283Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/PaymentType/CreateAsync/`

## Delete

This endpoint allows you to delete particular record of payment type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PaymentType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "paymentTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:13:07.445Z",
  "lastModificationTime": "2020-05-20T18:13:07.445Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:13:07.445Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Payment Type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "paymentTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T18:13:07.452Z",
    "lastModificationTime": "2020-05-20T18:13:07.452Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T18:13:07.452Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/PaymentType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "paymentTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:13:08.602Z",
  "lastModificationTime": "2020-05-20T18:13:08.602Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:13:08.602Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Payment Voucher

A payment voucher is a document which can be used as proof that a monetary transaction has occured between two parties. In business, it sometimes act as a receipt, indicates that an invoice has been approved for payment among other things.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
paymentVoucherName | string | the name of the payment voucher
billId | int | the id of the bill
paymentDate | datestring | the subject of the case
paymentTypeId | int | the id of the payment type
paymentAmount | double | the amount on the voucher
cashBankId | int | the id of the Cash bank
isFullPayment | bool | shows whether it's full payment or not
billAmount | double | the actual amount of the product or service on the voucher
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a case
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the branch was created
creatorUserId | int | the id of the user who created that case
id | int | the id of the case

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "paymentVoucherName": " ", "billId": " ", "paymentDate": " ", "paymentTypeId": " ", "paymentAmount": " ", "cashBankId": " ", "isFullPayment": " ", "billAmount": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"paymentVoucherName\": \" \",\n    \"billId\": \" \",\n    \"paymentDate\": \" \",\n    \"paymentTypeId\": \" \",\n    \"paymentAmount\": \" \",\n    \"cashBankId\": \" \",\n    \"isFullPayment\": \" \",\n    \"billAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"paymentVoucherName\": \" \",\n    \"billId\": \" \",\n    \"paymentDate\": \" \",\n    \"paymentTypeId\": \" \",\n    \"paymentAmount\": \" \",\n    \"cashBankId\": \" \",\n    \"isFullPayment\": \" \",\n    \"billAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "paymentVoucherName": " ",
    "billId": 0,
    "paymentDate": " ",
    "paymentTypeId": 0,
    "paymentAmount": 0,
    "cashBankId": 0,
    "isFullPayment": 1,
    "billAmount": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "paymentVoucherName": "string",
  "billId": 0,
  "paymentDate": "2020-05-20T18:53:14.544Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "cashBankId": 0,
  "isFullPayment": true,
  "billAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:53:14.544Z",
  "lastModificationTime": "2020-05-20T18:53:14.544Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:53:14.544Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/PaymentVoucher/CreateAsync/`

## Delete

This endpoint allows you to delete particular payment voucher from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PaymentVoucher/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "paymentVoucherName": "string",
  "billId": 0,
  "paymentDate": "2020-05-20T18:53:38.446Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "cashBankId": 0,
  "isFullPayment": true,
  "billAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:53:38.446Z",
  "lastModificationTime": "2020-05-20T18:53:38.446Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:53:38.446Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the voucher to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "paymentVoucherName": "string",
    "billId": 0,
    "paymentDate": "2020-05-20T18:53:38.452Z",
    "paymentTypeId": 0,
    "paymentAmount": 0,
    "cashBankId": 0,
    "isFullPayment": true,
    "billAmount": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T18:53:38.452Z",
    "lastModificationTime": "2020-05-20T18:53:38.452Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T18:53:38.452Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the payment vouchers.

### HTTP Request

`POST /api/services/app/PaymentVoucher/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"paymentVoucherName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PaymentVoucher/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"paymentVoucherName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "paymentVoucherName": "nothing",
  "billId": 0,
  "paymentDate": "2020-05-20T18:53:38.688Z",
  "paymentTypeId": 0,
  "paymentAmount": 0,
  "cashBankId": 0,
  "isFullPayment": true,
  "billAmount": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T18:53:38.688Z",
  "lastModificationTime": "2020-05-20T18:53:38.688Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T18:53:38.688Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Product

The products section contains details of the products provided by the supplier.

### Field

Parameter | Type | Description
--------- | ------- | --------
productName | string | the name of the product
productCode | string | the code of the product
barcode | string | the barcode for a specific product
description | string | the details of the product
productImageUrl | string | the path showing the location of the product's image
unitOfMeasureId | int | the id for the unit of measure
defaultBuyingPrice | double | the default buying price
defaultSellingPrice | double | the default selling price of the product
branchId | int | the id of the branch
currencyId | int | the id of the currency
productTypeId | int | the id of the product type
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a product
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the product record was created
creatorUserId | int | the id of the user who created the product record
id | int | the id of the product

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"productName": " ", "productCode": " ", "barCode": " ", "description": " ", "productImageUrl": " ", "unitOfMeasureId": " ", "defaultBuyingPrice": " ", "defaultSellingPrice": " ", "branchId": " ", "currencyId": " ", "productTypeId": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"productName\": \" \",\n    \"productCode\": \" \",\n    \"barCode\": \" \",\n    \"description\": \" \",\n    \"productImageUrl\": \" \",\n    \"unitOfMeasureId\": \" \",\n    \"defaultBuyingPrice\": \" \",\n    \"defaultSellingPrice\": \" \",\n    \"branchId\": \" \",\n    \"currencyId\": \" \",\n    \"productTypeId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"productName\": \" \",\n    \"productCode\": \" \",\n    \"barCode\": \" \",\n    \"description\": \" \",\n    \"productImageUrl\": \" \",\n    \"unitOfMeasureId\": \" \",\n    \"defaultBuyingPrice\": \" \",\n    \"defaultSellingPrice\": \" \",\n    \"branchId\": \" \",\n    \"currencyId\": \" \",\n    \"productTypeId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "productName": " ",
    "productCode": " ",
    "barcode": " ",
    "description": " ",
    "productImageUrl": " ",
    "unitOfMeasureId": 0,
    "defaultBuyingPrice": 0,
    "defaultSellingPrice": 0,
    "branchId": 0,
    "currencyId": 0,
    "productTypeId": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "productName": "string",
  "productCode": "string",
  "barcode": "string",
  "description": "string",
  "productImageUrl": "string",
  "unitOfMeasureId": 0,
  "defaultBuyingPrice": 0,
  "defaultSellingPrice": 0,
  "branchId": 0,
  "currencyId": 0,
  "productTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:23:27.065Z",
  "lastModificationTime": "2020-05-20T19:23:27.065Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:23:27.065Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/Product/CreateAsync/`

## Delete

This endpoint allows you to delete particular product from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Product/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "productName": "string",
  "productCode": "string",
  "barcode": "string",
  "description": "string",
  "productImageUrl": "string",
  "unitOfMeasureId": 0,
  "defaultBuyingPrice": 0,
  "defaultSellingPrice": 0,
  "branchId": 0,
  "currencyId": 0,
  "productTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:49:01.971Z",
  "lastModificationTime": "2020-05-20T19:49:01.971Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:49:01.971Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the product to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "productName": "string",
    "productCode": "string",
    "barcode": "string",
    "description": "string",
    "productImageUrl": "string",
    "unitOfMeasureId": 0,
    "defaultBuyingPrice": 0,
    "defaultSellingPrice": 0,
    "branchId": 0,
    "currencyId": 0,
    "productTypeId": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T19:49:01.977Z",
    "lastModificationTime": "2020-05-20T19:49:01.978Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T19:49:01.978Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the products.

### HTTP Request

`POST /api/services/app/Product/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"productName\": \"nothing\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Product/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"productName\": \"nothing\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "productName": "nothing",
  "productCode": "string",
  "barcode": "string",
  "description": "nothing",
  "productImageUrl": "string",
  "unitOfMeasureId": 0,
  "defaultBuyingPrice": 0,
  "defaultSellingPrice": 0,
  "branchId": 0,
  "currencyId": 0,
  "productTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:49:02.190Z",
  "lastModificationTime": "2020-05-20T19:49:02.190Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:49:02.190Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Product Type

This section contains the different types of products.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
productTypeName | string | the name of the product type
description | string | details regarding the product type
isDeleted | boolean | checks whether a record is deleted or not
deleterUserId | int | the id of the user who deletes a record of product type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the product type record was created
creatorUserId | int | the id of the user who created the product type
id | int | the id of the product type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "productTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"productTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"productTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "productTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "productTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:54:39.270Z",
  "lastModificationTime": "2020-05-20T19:54:39.270Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:54:39.270Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/ProductType/CreateAsync/`

## Delete

This endpoint allows you to delete particular product type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/ProductType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "productTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:54:58.089Z",
  "lastModificationTime": "2020-05-20T19:54:58.089Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:54:58.089Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the product type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "productTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T19:54:58.097Z",
    "lastModificationTime": "2020-05-20T19:54:58.097Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T19:54:58.097Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/ProductType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ProductId/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "productTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T19:54:58.379Z",
  "lastModificationTime": "2020-05-20T19:54:58.379Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T19:54:58.379Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Purchase Order 

A purchase order is a commercial document and first official offer issued by a buyer to a seller indicating types, quantities, and agreed prices for products or services. It is used to control the purchasing of products and services from external suppliers.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
purchaseOrderName | string | the name of the purchase order
branchId | int | the id of the branch
vendorId | int | the id of the vendor
orderDate | datestring | the date of ordering the products
currencyId | int |the id of the currency
purchaseTypeId | int | the id of the purchase type
remarks | string | a section for any comments regarding the purchase order
amount | double | the total cost of the products being purchased
subTotal | int | the sub total of the products
discount | double | the discount on the products
tax | double | the amount to be paid as tax for the products
freight | int | the freight of the purchase order
total | double | the total quantity of products ordered
isDeleted | boolean | checks whether a purchase order is deleted or not
deleterUserId | int | the id of the user who deletes a purchase order
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the branch was created
creatorUserId | int | the id of the user who created that purchase order
id | int | the id of the purchase order

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "purchaseOrderName": " ", "branchId": " ", "branchId": " ", "vendorId": " ", "orderDate": " ", "deliveryDate": " ", "currencyId": " ", "purchaseTypeId": " ", "remarks": " ", "amount": " ", "subTotal": " ", "discount": " ", "tax": " ", "freight": " ", "total": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"purchaseOrderName\": \" \",\n    \"branchId\": \" \",\n    \"vendorId\": \" \",\n    \"orderDate\": \" \",\n    \"deliveryDate\": \" \",\n    \"currencyId\": \" \",\n    \"purchaseTypeId\": \" \",\n    \"remarks\": \" \",\n    \"amount\": \" \",\n    \"subTotal\": \" \",\n    \"discount\": \" \",\n    \"tax\": \" \",\n    \"freight\": \" \",\n    \"total\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"purchaseOrderName\": \" \",\n    \"branchId\": \" \",\n    \"vendorId\": \" \",\n    \"orderDate\": \" \",\n    \"deliveryDate\": \" \",\n    \"currencyId\": \" \",\n    \"purchaseTypeId\": \" \",\n    \"remarks\": \" \",\n    \"amount\": \" \",\n    \"subTotal\": \" \",\n    \"discount\": \" \",\n    \"tax\": \" \",\n    \"freight\": \" \",\n    \"total\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "purchaseOrderName": " ",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": " ",
    "deliveryDate": " ",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": " ",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "purchaseOrderName": "string",
  "branchId": 0,
  "vendorId": 0,
  "orderDate": "2020-05-20T20:24:21.272Z",
  "deliveryDate": "2020-05-20T20:24:21.272Z",
  "currencyId": 0,
  "purchaseTypeId": 0,
  "remarks": "string",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T20:24:21.272Z",
  "lastModificationTime": "2020-05-20T20:24:21.272Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T20:24:21.272Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/PurchaseOrder/CreateAsync/`

## Delete

This endpoint allows you to delete particular purchase order from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PurchaseOrder/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "purchaseOrderName": "string",
  "branchId": 0,
  "vendorId": 0,
  "orderDate": "2020-05-20T20:24:52.330Z",
  "deliveryDate": "2020-05-20T20:24:52.330Z",
  "currencyId": 0,
  "purchaseTypeId": 0,
  "remarks": "string",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T20:24:52.330Z",
  "lastModificationTime": "2020-05-20T20:24:52.330Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T20:24:52.330Z",
  "creatorUserId": 0,
  "id": 0,
  "purchaseOrderId": 0,
  "vendor": {
    "tenantId": 0,
    "vendorId": 0,
    "vendorName": "string",
    "vendorTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T20:24:52.330Z",
    "lastModificationTime": "2020-05-20T20:24:52.330Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T20:24:52.330Z",
    "creatorUserId": 0,
    "id": 0
  },
  "currency": {
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T20:24:52.330Z",
    "lastModificationTime": "2020-05-20T20:24:52.330Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T20:24:52.330Z",
    "creatorUserId": 0,
    "id": 0
  },
  "purchaseType": {
    "tenantId": 0,
    "purchaseTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T20:24:52.330Z",
    "lastModificationTime": "2020-05-20T20:24:52.330Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T20:24:52.330Z",
    "creatorUserId": 0,
    "id": 0
  },
  "branch": {
    "tenantId": 0,
    "branchName": "string",
    "description": "string",
    "currencyId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T20:24:52.331Z",
    "lastModificationTime": "2020-05-20T20:24:52.331Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T20:24:52.331Z",
    "creatorUserId": 0,
    "id": 0
  }
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the purchase order to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "purchaseOrderName": "string",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": "2020-05-20T21:08:23.536Z",
    "deliveryDate": "2020-05-20T21:08:23.536Z",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T21:08:23.536Z",
    "lastModificationTime": "2020-05-20T21:08:23.536Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T21:08:23.536Z",
    "creatorUserId": 0,
    "id": 0,
    "purchaseOrderId": 0,
    "vendor": {
      "tenantId": 0,
      "vendorId": 0,
      "vendorName": "string",
      "vendorTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T21:08:23.536Z",
      "lastModificationTime": "2020-05-20T21:08:23.536Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T21:08:23.536Z",
      "creatorUserId": 0,
      "id": 0
    },
    "currency": {
      "tenantId": 0,
      "currencyName": "string",
      "currencyCode": "string",
      "description": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T21:08:23.537Z",
      "lastModificationTime": "2020-05-20T21:08:23.537Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T21:08:23.537Z",
      "creatorUserId": 0,
      "id": 0
    },
    "purchaseType": {
      "tenantId": 0,
      "purchaseTypeName": "string",
      "description": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T21:08:23.537Z",
      "lastModificationTime": "2020-05-20T21:08:23.537Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T21:08:23.537Z",
      "creatorUserId": 0,
      "id": 0
    },
    "branch": {
      "tenantId": 0,
      "branchName": "string",
      "description": "string",
      "currencyId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T21:08:23.537Z",
      "lastModificationTime": "2020-05-20T21:08:23.537Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T21:08:23.537Z",
      "creatorUserId": 0,
      "id": 0
    }
  }
]
```

This endpoint will list all the purchase orders.

### HTTP Request

`POST /api/services/app/PurchaseOrder/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"remarks\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrder/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"remarks\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "purchaseOrderName": "string",
  "branchId": 0,
  "vendorId": 0,
  "orderDate": "2020-05-20T20:24:46.595Z",
  "deliveryDate": "2020-05-20T20:24:46.595Z",
  "currencyId": 0,
  "purchaseTypeId": 0,
  "remarks": "nothing",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T20:24:46.595Z",
  "lastModificationTime": "2020-05-20T20:24:46.595Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T20:24:46.595Z",
  "creatorUserId": 0,
  "id": 0
}
```

## Print

This section displays the purchase orders.

### HTTP Request

`POST /api/services/app/PurchaseOrder/Print/`

> The above endpoint returns JSON structured like this:

```json
{
  "purchaseOrder": {
    "tenantId": 0,
    "purchaseOrderName": "string",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": "2020-05-20T21:15:58.997Z",
    "deliveryDate": "2020-05-20T21:15:58.997Z",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "purchaseOrderLines": [
      {
        "tenantId": 0,
        "purchaseOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T21:15:58.997Z",
        "lastModificationTime": "2020-05-20T21:15:58.997Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T21:15:58.998Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T21:15:58.998Z",
    "lastModificationTime": "2020-05-20T21:15:58.998Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T21:15:58.998Z",
    "creatorUserId": 0,
    "id": 0
  },
  "branch": {
    "tenantId": 0,
    "branchName": "string",
    "description": "string",
    "currencyId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T21:15:58.998Z",
    "lastModificationTime": "2020-05-20T21:15:58.998Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T21:15:58.998Z",
    "creatorUserId": 0,
    "id": 0
  },
  "vendor": {
    "tenantId": 0,
    "vendorId": 0,
    "vendorName": "string",
    "vendorTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T21:15:58.998Z",
    "lastModificationTime": "2020-05-20T21:15:58.998Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T21:15:58.998Z",
    "creatorUserId": 0,
    "id": 0
  },
  "currency": {
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T21:15:58.998Z",
    "lastModificationTime": "2020-05-20T21:15:58.998Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T21:15:58.998Z",
    "creatorUserId": 0,
    "id": 0
  },
  "lines": [
    {
      "product": {
        "productName": "string",
        "productCode": "string",
        "barcode": "string",
        "description": "string",
        "productImageUrl": "string",
        "unitOfMeasureId": 0,
        "defaultBuyingPrice": 0,
        "defaultSellingPrice": 0,
        "branchId": 0,
        "currencyId": 0,
        "productTypeId": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T21:15:58.998Z",
        "lastModificationTime": "2020-05-20T21:15:58.998Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T21:15:58.998Z",
        "creatorUserId": 0,
        "id": 0
      },
      "purchaseOrderLine": {
        "tenantId": 0,
        "purchaseOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-20T21:15:58.998Z",
        "lastModificationTime": "2020-05-20T21:15:58.998Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T21:15:58.999Z",
        "creatorUserId": 0,
        "id": 0
      }
    }
  ]
}
```

# Purchase Order Line

Purchase order line (POL) is an individual order which includes all the details of the order. A purchase order is what is sent to the vendor; it could be one or multiple purchase order lines. It has the following field parameters.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
purchaseOrderId | int | the id of the purchase order
purchaseOrder | class | details regarding the purchase order
productId | int | the id of the product
description | string | the details of the product being purchased
quantity | int | the quantity of the products
price | double | the price of the products
discountPercentage | float | the percentage of the discount for the purchase
discountAmount | float | the amount deducted as discount for the products on POL
isDeleted | boolean | checks whether a purchase order line is deleted or not
deleterUserId | int | the id of the user who deletes a purchase order line
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the purchase order line was created
creatorUserId | int | the id of the user who created that purchase order line
id | int | the id of the purchase order line

## Create


```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"tenantId": " ", "purchaseOrderId": " ", "purchaseOrder": " ", "productId": " ", "description": " ", "quantity": " ", "price": " ", "discountPercentage": " ", "discountAmount": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"purchaseOrderId\": \" \",\n    \"purchaseOrder\": \" \",\n    \"productId\": \" \",\n    \"description\": \" \",\n    \"quantity\": \" \",\n    \"price\": \" \",\n    \"discountPercentage\": \" \",\n    \"discountAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"purchaseOrderId\": \" \",\n    \"purchaseOrder\": \" \",\n    \"productId\": \" \",\n    \"description\": \" \",\n    \"quantity\": \" \",\n    \"price\": \" \",\n    \"discountPercentage\": \" \",\n    \"discountAmount\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "purchaseOrderId": " ",
    "purchaseOrder": " ",
    "productId": 0,    
    "description": " ",
    "quantity": 0,
    "price": 0,
    "discountPercentage": " ",
    "discountAmount": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "purchaseOrderId": 0,
  "purchaseOrder": {
    "tenantId": 0,
    "purchaseOrderName": "string",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": "2020-05-22T05:52:17.742Z",
    "deliveryDate": "2020-05-22T05:52:17.742Z",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "purchaseOrderLines": [
      {
        "tenantId": 0,
        "purchaseOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T05:52:17.743Z",
        "lastModificationTime": "2020-05-22T05:52:17.743Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T05:52:17.743Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T05:52:17.743Z",
    "lastModificationTime": "2020-05-22T05:52:17.743Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T05:52:17.743Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T05:52:17.743Z",
  "lastModificationTime": "2020-05-22T05:52:17.743Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T05:52:17.743Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a purchase order line.

### HTTP Request

`POST /api/services/app/PurchaseOrderLine/CreateAsync/`

## Delete

This endpoint allows you to delete particular POL from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PurchaseOrderLine/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "purchaseOrderId": 0,
  "purchaseOrder": {
    "tenantId": 0,
    "purchaseOrderName": "string",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": "2020-05-22T06:52:11.511Z",
    "deliveryDate": "2020-05-22T06:52:11.511Z",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "purchaseOrderLines": [
      {
        "tenantId": 0,
        "purchaseOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T06:52:11.511Z",
        "lastModificationTime": "2020-05-22T06:52:11.511Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T06:52:11.511Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T06:52:11.511Z",
    "lastModificationTime": "2020-05-22T06:52:11.511Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T06:52:11.511Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T06:52:11.511Z",
  "lastModificationTime": "2020-05-22T06:52:11.511Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T06:52:11.511Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the POL to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "purchaseOrderId": 0,
    "purchaseOrder": {
      "tenantId": 0,
      "purchaseOrderName": "string",
      "branchId": 0,
      "vendorId": 0,
      "orderDate": "2020-05-22T06:52:11.528Z",
      "deliveryDate": "2020-05-22T06:52:11.528Z",
      "currencyId": 0,
      "purchaseTypeId": 0,
      "remarks": "string",
      "amount": 0,
      "subTotal": 0,
      "discount": 0,
      "tax": 0,
      "freight": 0,
      "total": 0,
      "purchaseOrderLines": [
        {
          "tenantId": 0,
          "purchaseOrderId": 0,
          "productId": 0,
          "description": "string",
          "quantity": 0,
          "price": 0,
          "amount": 0,
          "discountPercentage": 0,
          "discountAmount": 0,
          "subTotal": 0,
          "taxPercentage": 0,
          "taxAmount": 0,
          "total": 0,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-22T06:52:11.528Z",
          "lastModificationTime": "2020-05-22T06:52:11.528Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-22T06:52:11.528Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T06:52:11.528Z",
      "lastModificationTime": "2020-05-22T06:52:11.528Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T06:52:11.529Z",
      "creatorUserId": 0,
      "id": 0
    },
    "productId": 0,
    "description": "string",
    "quantity": 0,
    "price": 0,
    "amount": 0,
    "discountPercentage": 0,
    "discountAmount": 0,
    "subTotal": 0,
    "taxPercentage": 0,
    "taxAmount": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T06:52:11.529Z",
    "lastModificationTime": "2020-05-22T06:52:11.529Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T06:52:11.529Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the POLs.

### HTTP Request

`POST /api/services/app/PurchaseOrderLine/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"purchaseOrderId\": \"5\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseOrderLine/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \"5\",\n    \"purchaseOrderId\": \"5\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "purchaseOrderId": 5,
  "purchaseOrder": {
    "tenantId": 0,
    "purchaseOrderName": "string",
    "branchId": 0,
    "vendorId": 0,
    "orderDate": "2020-05-22T06:52:11.778Z",
    "deliveryDate": "2020-05-22T06:52:11.778Z",
    "currencyId": 0,
    "purchaseTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "purchaseOrderLines": [
      {
        "tenantId": 0,
        "purchaseOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T06:52:11.778Z",
        "lastModificationTime": "2020-05-22T06:52:11.778Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T06:52:11.778Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T06:52:11.778Z",
    "lastModificationTime": "2020-05-22T06:52:11.778Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T06:52:11.778Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T06:52:11.779Z",
  "lastModificationTime": "2020-05-22T06:52:11.779Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T06:52:11.779Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Purchase Type

There are four primary types of purchase orders, which differ according to how much information is known at the time the order is made.
These are:

* Standard Purchase Orders
* Planned Purchase Orders (PPO)
* Blanket Purchase Orders (BPO)
* Contract Purchase Orders (CPO)

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
purchaseTypeName | string | the name of the purchase type
description | string | details regarding the purchase type
isDeleted | boolean | checks whether a purchase type is deleted or not
deleterUserId | int | the id of the user who deletes a purchase type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the purchase type was created
creatorUserId | int | the id of the user who created that purchase type
id | int | the id of the purchase type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "purchaseTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"purchaseTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"purchaseTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "purchaseTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "purchaseTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:22:02.024Z",
  "lastModificationTime": "2020-05-22T07:22:02.024Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:22:02.024Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/PurchaseType/CreateAsync/`

## Delete

This endpoint allows you to delete particular purchase type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/PurchaseType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "purchaseTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:22:24.935Z",
  "lastModificationTime": "2020-05-22T07:22:24.935Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:22:24.935Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the purchase type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "purchaseTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T07:22:24.939Z",
    "lastModificationTime": "2020-05-22T07:22:24.939Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T07:22:24.939Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Purchase types.

### HTTP Request

`POST /api/services/app/PurchaseType/ListAll/`

## Update


```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/PurchaseType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "purchaseTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:22:25.197Z",
  "lastModificationTime": "2020-05-22T07:22:25.197Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:22:25.197Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Ratings

This section shows the ratings by customers using the service.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
ratingName | string | the name of the rating
description | string | details regarding the rating
isDeleted | boolean | checks whether the rating is deleted or not
deleterUserId | int | the id of the user who deletes rating
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the rating was created
creatorUserId | int | the id of the user who created that rating
id | int | the id of the rating

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "ratingName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"ratingName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"ratingName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "ratingName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "ratingName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:39:49.775Z",
  "lastModificationTime": "2020-05-22T07:39:49.775Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:39:49.775Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/Ratings/CreateAsync/`

## Delete

This endpoint allows you to delete particular rating from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Ratings/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "ratingName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:40:12.617Z",
  "lastModificationTime": "2020-05-22T07:40:12.617Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:40:12.617Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the rating to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "ratingName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T07:40:12.656Z",
    "lastModificationTime": "2020-05-22T07:40:12.656Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T07:40:12.656Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the ratings.

### HTTP Request

`POST /api/services/app/Ratings/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Ratings/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "ratingName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T07:40:12.901Z",
  "lastModificationTime": "2020-05-22T07:40:12.901Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T07:40:12.901Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Role

Each user in the database will have a role. It's the following field parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
name | string | the name of the role
displayName | string | the name displayed on the screen
normalizeName | string | the name in a normalized format
description | string | the details on the role
grantedPermissions | list | shows the different permissions for each role

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Create/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"name": " ", "displayName": " ", "normalizeName": " ", "description": " ", "grantedPermissions": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Create/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"name\": \" \",\n    \"displayName\": \" \",\n    \"normalizeName\": \" \",\n    \"description\": \" \",\n    \"grantedPermissions\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Create/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"name\": \" \",\n    \"displayName\": \" \",\n    \"normalizeName\": \" \",\n    \"description\": \" \",\n    \"grantedPermissions\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Create/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "name": " ",
    "displayName": " ",
    "normalizeName": " ",
    "description": " ",
    "grantedPermissions": " "
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "name": "string",
  "displayName": "string",
  "normalizedName": "string",
  "description": "string",
  "grantedPermissions": [
    "string"
  ]
}
```

> Response: Example Value | Value

```json
{
  "name": "string",
  "displayName": "string",
  "normalizedName": "string",
  "description": "string",
  "grantedPermissions": [
    "string"
  ],
  "id": 0
}
```
This endpoint creates a role.

### HTTP Request

`POST /api/services/app/Role/Create/`

## Get Roles

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRolesAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRolesAsync/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRolesAsync/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "items": [
    {
      "name": "string",
      "displayName": "string",
      "isStatic": true,
      "isDefault": true,
      "creationTime": "2020-05-22T08:21:31.821Z",
      "id": 0
    }
  ]
}
```

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"name\": \"nothing\",\n    \"displayName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"name\": \"nothing\",\n    \"displayName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "name": "nothing",
  "displayName": "nothing",
  "normalizedName": "string",
  "description": "string",
  "grantedPermissions": [
    "string"
  ],
  "id": 0
}
```

## Delete

This endpoint allows you to delete particular role from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Role/Delete`

## Get All Permissions

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAllPermissions/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAllPermissions/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAllPermissions/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "items": [
    {
      "name": "string",
      "displayName": "string",
      "description": "string",
      "id": 0
    }
  ]
}
```

## Get Role for Edit

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRoleForEdit/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRoleForEdit/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetRoleForEdit/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "role": {
    "name": "string",
    "displayName": "string",
    "description": "string",
    "isStatic": true,
    "id": 0
  },
  "permissions": [
    {
      "name": "string",
      "displayName": "string",
      "description": "string"
    }
  ],
  "grantedPermissionNames": [
    "string"
  ]
}
```

## Get

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Get/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Get/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/Get/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "name": "string",
  "displayName": "string",
  "normalizedName": "string",
  "description": "string",
  "grantedPermissions": [
    "string"
  ],
  "id": 0
}
```


### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the role to retrieve

## Get All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAll/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Role/GetAll/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "totalCount": 0,
  "items": [
    {
      "name": "string",
      "displayName": "string",
      "normalizedName": "string",
      "description": "string",
      "grantedPermissions": [
        "string"
      ],
      "id": 0
    }
  ]
}
```


### URL Parameters

Parameter | Type | Description
--------- | ------- | -----------
Keyword | string | an essential work which acts as a clue
skipCount | integer | skip count
maxResultCount | integer | number of times to obtain maximum results

# Sales Order

The sales order, SO, is an order issued by a business or sole trader to a customer. It may be for products and/or services.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
salesOrderName | string | the name of the sales order
branchId | int | the id of the branch
customerId | int | the id of the customer
orderDate | datestring | the date when the order is made
deliveryDate | datestring | the date of delivering the products and/or services
currencyId | int | the id of the currency
customerRefNumber | string | the reference number of the customer
salesTypeId | int | the id of the sales type
remarks | string | extra comments by customers regarding the products or services
amount | double | the cost of the products or services ordered
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a case
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the branch was created
creatorUserId | int | the id of the user who created that case
id | int | the id of the case

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "salesOrderName": " ", "branchId": " ", "customerId": " ", "orderDate": " ", "deliveryDate": " ", "currencyId": " ", "customerRefNumber": " ", "salesTypeId": " ", "remarks": " ", "amount": " ", "subTotal": " ", "discount": " ", "tax": " ", "freight": " ", "total": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"salesOrderName\": \" \",\n    \"branchId\": \" \",\n    \"customerId\": \" \",\n    \"orderDate\": \" \",\n    \"deliveryDate\": \" \",\n    \"currencyId\": \" \",\n    \"customerRefNumber\": \" \",\n    \"salesTypeId\": \" \",\n    \"remarks\": \" \",\n    \"amount\": \" \",\n    \"subTotal\": \" \",\n    \"discount\": \" \",\n    \"tax\": \" \",\n    \"freight\": \" \",\n    \"total\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"salesOrderName\": \" \",\n    \"branchId\": \" \",\n    \"customerId\": \" \",\n    \"orderDate\": \" \",\n    \"deliveryDate\": \" \",\n    \"currencyId\": \" \",\n    \"customerRefNumber\": \" \",\n    \"salesTypeId\": \" \",\n    \"remarks\": \" \",\n    \"amount\": \" \",\n    \"subTotal\": \" \",\n    \"discount\": \" \",\n    \"tax\": \" \",\n    \"freight\": \" \",\n    \"total\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "salesOrderName": " ",
    "branchId": 0,
    "customerId": 0,
    "orderDate": " ",
    "deliveryDate": " ",
    "currencyId": 0,
    "customerRefNumber": 0,
    "salesTypeId": 0,
    "remarks": " ",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "salesOrderName": "string",
  "branchId": 0,
  "customerId": 0,
  "orderDate": "2020-05-22T10:26:06.800Z",
  "deliveryDate": "2020-05-22T10:26:06.800Z",
  "currencyId": 0,
  "customerRefNumber": "string",
  "salesTypeId": 0,
  "remarks": "string",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T10:26:06.800Z",
  "lastModificationTime": "2020-05-22T10:26:06.800Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T10:26:06.800Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a sales order.

### HTTP Request

`POST /api/services/app/SalesOrder/CreateAsync/`

## Delete

This endpoint allows you to delete particular sales order from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/SalesOrder/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "salesOrderName": "string",
  "branchId": 0,
  "customerId": 0,
  "orderDate": "2020-05-22T10:26:44.571Z",
  "deliveryDate": "2020-05-22T10:26:44.571Z",
  "currencyId": 0,
  "customerRefNumber": "string",
  "salesTypeId": 0,
  "remarks": "string",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T10:26:44.571Z",
  "lastModificationTime": "2020-05-22T10:26:44.571Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T10:26:44.571Z",
  "creatorUserId": 0,
  "id": 0,
  "salesOrderId": 0,
  "customer": {
    "tenantId": 0,
    "customerName": "string",
    "customerTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "idNumber": "string",
    "idType": "string",
    "accountType": "string",
    "xcoordinate": 0,
    "ycoordinate": 0,
    "accountNumber": 0,
    "referenceNumber": 0,
    "imagelocation": "string",
    "website": "string",
    "industry": "string",
    "rating": "string",
    "phoneAlternative": "string",
    "countryId": 0,
    "country": {
      "tenantId": 0,
      "countryName": "string",
      "countryZone": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T10:26:44.571Z",
      "lastModificationTime": "2020-05-22T10:26:44.571Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T10:26:44.571Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "accounts": [
      {
        "customerId": 0,
        "parentAccountId": 0,
        "tenantId": 0,
        "totalLoanAmount": 0,
        "totalAmountPaid": 0,
        "balance": 0,
        "is_Open": true,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:44.572Z",
        "lastModificationTime": "2020-05-22T10:26:44.572Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:44.572Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.572Z",
    "lastModificationTime": "2020-05-22T10:26:44.572Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.572Z",
    "creatorUserId": 0,
    "id": 0
  },
  "currency": {
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.572Z",
    "lastModificationTime": "2020-05-22T10:26:44.572Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.572Z",
    "creatorUserId": 0,
    "id": 0
  },
  "salesType": {
    "tenantId": 0,
    "salesTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.572Z",
    "lastModificationTime": "2020-05-22T10:26:44.572Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.572Z",
    "creatorUserId": 0,
    "id": 0
  },
  "branch": {
    "tenantId": 0,
    "branchName": "string",
    "description": "string",
    "currencyId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.572Z",
    "lastModificationTime": "2020-05-22T10:26:44.572Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.572Z",
    "creatorUserId": 0,
    "id": 0
  }
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the sales order to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T11:07:26.636Z",
    "deliveryDate": "2020-05-22T11:07:26.636Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T11:07:26.636Z",
    "lastModificationTime": "2020-05-22T11:07:26.636Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T11:07:26.636Z",
    "creatorUserId": 0,
    "id": 0,
    "salesOrderId": 0,
    "customer": {
      "tenantId": 0,
      "customerName": "string",
      "customerTypeId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "idNumber": "string",
      "idType": "string",
      "accountType": "string",
      "xcoordinate": 0,
      "ycoordinate": 0,
      "accountNumber": 0,
      "referenceNumber": 0,
      "imagelocation": "string",
      "website": "string",
      "industry": "string",
      "rating": "string",
      "phoneAlternative": "string",
      "countryId": 0,
      "country": {
        "tenantId": 0,
        "countryName": "string",
        "countryZone": "string",
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T11:07:26.636Z",
        "lastModificationTime": "2020-05-22T11:07:26.636Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T11:07:26.636Z",
        "creatorUserId": 0,
        "id": 0
      },
      "parent_CustomerId_Id": 0,
      "email2": "string",
      "ownership": "string",
      "taxId": "string",
      "vatNo": "string",
      "gender": "string",
      "accounts": [
        {
          "customerId": 0,
          "parentAccountId": 0,
          "tenantId": 0,
          "totalLoanAmount": 0,
          "totalAmountPaid": 0,
          "balance": 0,
          "is_Open": true,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-22T11:07:26.636Z",
          "lastModificationTime": "2020-05-22T11:07:26.636Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-22T11:07:26.636Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T11:07:26.636Z",
      "lastModificationTime": "2020-05-22T11:07:26.636Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T11:07:26.636Z",
      "creatorUserId": 0,
      "id": 0
    },
    "currency": {
      "tenantId": 0,
      "currencyName": "string",
      "currencyCode": "string",
      "description": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T11:07:26.636Z",
      "lastModificationTime": "2020-05-22T11:07:26.636Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T11:07:26.636Z",
      "creatorUserId": 0,
      "id": 0
    },
    "salesType": {
      "tenantId": 0,
      "salesTypeName": "string",
      "description": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T11:07:26.636Z",
      "lastModificationTime": "2020-05-22T11:07:26.636Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T11:07:26.636Z",
      "creatorUserId": 0,
      "id": 0
    },
    "branch": {
      "tenantId": 0,
      "branchName": "string",
      "description": "string",
      "currencyId": 0,
      "address": "string",
      "city": "string",
      "state": "string",
      "zipCode": "string",
      "phone": "string",
      "email": "string",
      "contactPerson": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T11:07:26.637Z",
      "lastModificationTime": "2020-05-22T11:07:26.637Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T11:07:26.637Z",
      "creatorUserId": 0,
      "id": 0
    }
  }
]
```

This endpoint will list all the sales orders.

### HTTP Request

`POST /api/services/app/SalesOrder/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"salesOrderName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"salesOrderName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "salesOrderName": "nothing",
  "branchId": 0,
  "customerId": 0,
  "orderDate": "2020-05-22T10:26:30.612Z",
  "deliveryDate": "2020-05-22T10:26:30.612Z",
  "currencyId": 0,
  "customerRefNumber": "string",
  "salesTypeId": 0,
  "remarks": "string",
  "amount": 0,
  "subTotal": 0,
  "discount": 0,
  "tax": 0,
  "freight": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T10:26:30.612Z",
  "lastModificationTime": "2020-05-22T10:26:30.612Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T10:26:30.612Z",
  "creatorUserId": 0,
  "id": 0
}
```

## Print

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/Print/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/Print/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
{
  "salesOrder": {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T10:26:44.623Z",
    "deliveryDate": "2020-05-22T10:26:44.623Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "salesOrderLines": [
      {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:44.624Z",
        "lastModificationTime": "2020-05-22T10:26:44.624Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:44.624Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.624Z",
    "lastModificationTime": "2020-05-22T10:26:44.624Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.624Z",
    "creatorUserId": 0,
    "id": 0
  },
  "branch": {
    "tenantId": 0,
    "branchName": "string",
    "description": "string",
    "currencyId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.624Z",
    "lastModificationTime": "2020-05-22T10:26:44.624Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.624Z",
    "creatorUserId": 0,
    "id": 0
  },
  "customer": {
    "tenantId": 0,
    "customerName": "string",
    "customerTypeId": 0,
    "address": "string",
    "city": "string",
    "state": "string",
    "zipCode": "string",
    "phone": "string",
    "email": "string",
    "contactPerson": "string",
    "idNumber": "string",
    "idType": "string",
    "accountType": "string",
    "xcoordinate": 0,
    "ycoordinate": 0,
    "accountNumber": 0,
    "referenceNumber": 0,
    "imagelocation": "string",
    "website": "string",
    "industry": "string",
    "rating": "string",
    "phoneAlternative": "string",
    "countryId": 0,
    "country": {
      "tenantId": 0,
      "countryName": "string",
      "countryZone": "string",
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T10:26:44.630Z",
      "lastModificationTime": "2020-05-22T10:26:44.630Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T10:26:44.630Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "accounts": [
      {
        "customerId": 0,
        "parentAccountId": 0,
        "tenantId": 0,
        "totalLoanAmount": 0,
        "totalAmountPaid": 0,
        "balance": 0,
        "is_Open": true,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:44.630Z",
        "lastModificationTime": "2020-05-22T10:26:44.630Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:44.631Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.631Z",
    "lastModificationTime": "2020-05-22T10:26:44.631Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.631Z",
    "creatorUserId": 0,
    "id": 0
  },
  "currency": {
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:44.631Z",
    "lastModificationTime": "2020-05-22T10:26:44.631Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:44.631Z",
    "creatorUserId": 0,
    "id": 0
  },
  "lines": [
    {
      "product": {
        "productName": "string",
        "productCode": "string",
        "barcode": "string",
        "description": "string",
        "productImageUrl": "string",
        "unitOfMeasureId": 0,
        "defaultBuyingPrice": 0,
        "defaultSellingPrice": 0,
        "branchId": 0,
        "currencyId": 0,
        "productTypeId": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:44.631Z",
        "lastModificationTime": "2020-05-22T10:26:44.631Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:44.631Z",
        "creatorUserId": 0,
        "id": 0
      },
      "salesOrderLine": {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:44.631Z",
        "lastModificationTime": "2020-05-22T10:26:44.631Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:44.631Z",
        "creatorUserId": 0,
        "id": 0
      }
    }
  ]
}
```

This endpoint print the sales order.

### HTTP Request

`POST /api/services/app/SalesOrder/Print/`

## Get Shipped Sakes Order

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetShippedSalesOrders/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetShippedSalesOrders/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrder/GetShippedSalesOrders/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T10:26:45.517Z",
    "deliveryDate": "2020-05-22T10:26:45.517Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "salesOrderLines": [
      {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T10:26:45.517Z",
        "lastModificationTime": "2020-05-22T10:26:45.517Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T10:26:45.517Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T10:26:45.517Z",
    "lastModificationTime": "2020-05-22T10:26:45.517Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T10:26:45.517Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

# Sales Order Line

The sales order line is where we specify the products, quantity, unit price, among others. The total value of all these sale order line items are shown in sales order.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
salesOrderId | int | the id of the sales order
salesOrder | class | details regarding the sales order
productId | int | the id of the product
description | string | the details about the product
quantity | int | the size of the products
price | double | the price of the products
isDeleted | boolean | checks whether a SOL is deleted or not
deleterUserId | int | the id of the user who deletes a SOL record
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the SOL record was created
creatorUserId | int | the id of the user who created that SOL record
id | int | the id of the SOL

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "salesOrderId": " ", "salesOrder": " " "productId": " ", "description": " ", "quantity": " ", "price": " ",  "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"salesOrderId\": \" \",\n    \"salesOrder\": \" \",\n    \"productId\": \" \",\n    \"description\": \" \",\n    \"quantity\": \" \",\n    \"price\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"salesOrderId\": \" \",\n    \"salesOrder\": \" \",\n    \"productId\": \" \",\n    \"description\": \" \",\n    \"quantity\": \" \",\n    \"price\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "salesOrderId": 0,
    "salesOrder": " ",
    "productId": " ",
    "description": " ",
    "quantity": 0,
    "price": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "salesOrderId": 0,
  "salesOrder": {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T11:20:47.500Z",
    "deliveryDate": "2020-05-22T11:20:47.500Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "salesOrderLines": [
      {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T11:20:47.501Z",
        "lastModificationTime": "2020-05-22T11:20:47.501Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T11:20:47.501Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T11:20:47.501Z",
    "lastModificationTime": "2020-05-22T11:20:47.501Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T11:20:47.501Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T11:20:47.501Z",
  "lastModificationTime": "2020-05-22T11:20:47.501Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T11:20:47.501Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/SalesOrderLine/CreateAsync/`

## Delete

This endpoint allows you to delete particular sales order line from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/SalesOrderLine/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "salesOrderId": 0,
  "salesOrder": {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T12:33:33.984Z",
    "deliveryDate": "2020-05-22T12:33:33.984Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "salesOrderLines": [
      {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T12:33:33.985Z",
        "lastModificationTime": "2020-05-22T12:33:33.985Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T12:33:33.985Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T12:33:33.985Z",
    "lastModificationTime": "2020-05-22T12:33:33.985Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T12:33:33.985Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T12:33:33.985Z",
  "lastModificationTime": "2020-05-22T12:33:33.985Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T12:33:33.985Z",
  "creatorUserId": 0,
  "id": 0,
  "product": {
    "productName": "string",
    "productCode": "string",
    "barcode": "string",
    "description": "string",
    "productImageUrl": "string",
    "unitOfMeasureId": 0,
    "defaultBuyingPrice": 0,
    "defaultSellingPrice": 0,
    "branchId": 0,
    "currencyId": 0,
    "productTypeId": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T12:33:33.986Z",
    "lastModificationTime": "2020-05-22T12:33:33.986Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T12:33:33.986Z",
    "creatorUserId": 0,
    "id": 0
  }
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the SOL to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "salesOrderId": 0,
    "salesOrder": {
      "tenantId": 0,
      "salesOrderName": "string",
      "branchId": 0,
      "customerId": 0,
      "orderDate": "2020-05-22T12:36:32.341Z",
      "deliveryDate": "2020-05-22T12:36:32.341Z",
      "currencyId": 0,
      "customerRefNumber": "string",
      "salesTypeId": 0,
      "remarks": "string",
      "amount": 0,
      "subTotal": 0,
      "discount": 0,
      "tax": 0,
      "freight": 0,
      "total": 0,
      "salesOrderLines": [
        {
          "tenantId": 0,
          "salesOrderId": 0,
          "productId": 0,
          "description": "string",
          "quantity": 0,
          "price": 0,
          "amount": 0,
          "discountPercentage": 0,
          "discountAmount": 0,
          "subTotal": 0,
          "taxPercentage": 0,
          "taxAmount": 0,
          "total": 0,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-22T12:36:32.342Z",
          "lastModificationTime": "2020-05-22T12:36:32.342Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-22T12:36:32.342Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T12:36:32.342Z",
      "lastModificationTime": "2020-05-22T12:36:32.342Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T12:36:32.342Z",
      "creatorUserId": 0,
      "id": 0
    },
    "productId": 0,
    "description": "string",
    "quantity": 0,
    "price": 0,
    "amount": 0,
    "discountPercentage": 0,
    "discountAmount": 0,
    "subTotal": 0,
    "taxPercentage": 0,
    "taxAmount": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T12:36:32.342Z",
    "lastModificationTime": "2020-05-22T12:36:32.342Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T12:36:32.342Z",
    "creatorUserId": 0,
    "id": 0,
    "product": {
      "productName": "string",
      "productCode": "string",
      "barcode": "string",
      "description": "string",
      "productImageUrl": "string",
      "unitOfMeasureId": 0,
      "defaultBuyingPrice": 0,
      "defaultSellingPrice": 0,
      "branchId": 0,
      "currencyId": 0,
      "productTypeId": 0,
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T12:36:32.342Z",
      "lastModificationTime": "2020-05-22T12:36:32.342Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T12:36:32.342Z",
      "creatorUserId": 0,
      "id": 0
    }
  }
]
```

This endpoint will list all the sales order lines.

### HTTP Request

`POST /api/services/app/SalesOrderLine/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"salesOrderId\": \"5\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"salesOrderId\": \"5\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "salesOrderId": 5,
  "salesOrder": {
    "tenantId": 0,
    "salesOrderName": "string",
    "branchId": 0,
    "customerId": 0,
    "orderDate": "2020-05-22T12:33:34.338Z",
    "deliveryDate": "2020-05-22T12:33:34.338Z",
    "currencyId": 0,
    "customerRefNumber": "string",
    "salesTypeId": 0,
    "remarks": "string",
    "amount": 0,
    "subTotal": 0,
    "discount": 0,
    "tax": 0,
    "freight": 0,
    "total": 0,
    "salesOrderLines": [
      {
        "tenantId": 0,
        "salesOrderId": 0,
        "productId": 0,
        "description": "string",
        "quantity": 0,
        "price": 0,
        "amount": 0,
        "discountPercentage": 0,
        "discountAmount": 0,
        "subTotal": 0,
        "taxPercentage": 0,
        "taxAmount": 0,
        "total": 0,
        "isDeleted": true,
        "deleterUserId": 0,
        "deletionTime": "2020-05-22T12:33:34.338Z",
        "lastModificationTime": "2020-05-22T12:33:34.338Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-22T12:33:34.338Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T12:33:34.338Z",
    "lastModificationTime": "2020-05-22T12:33:34.338Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T12:33:34.338Z",
    "creatorUserId": 0,
    "id": 0
  },
  "productId": 0,
  "description": "string",
  "quantity": 0,
  "price": 0,
  "amount": 0,
  "discountPercentage": 0,
  "discountAmount": 0,
  "subTotal": 0,
  "taxPercentage": 0,
  "taxAmount": 0,
  "total": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T12:33:34.338Z",
  "lastModificationTime": "2020-05-22T12:33:34.338Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T12:33:34.338Z",
  "creatorUserId": 0,
  "id": 0
}
```

## Get Sales Order Details

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetSalesOrderDetail/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetSalesOrderDetail/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesOrderLine/GetSalesOrderDetail/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "salesOrderId": 0,
    "salesOrder": {
      "tenantId": 0,
      "salesOrderName": "string",
      "branchId": 0,
      "customerId": 0,
      "orderDate": "2020-05-22T12:36:34.116Z",
      "deliveryDate": "2020-05-22T12:36:34.116Z",
      "currencyId": 0,
      "customerRefNumber": "string",
      "salesTypeId": 0,
      "remarks": "string",
      "amount": 0,
      "subTotal": 0,
      "discount": 0,
      "tax": 0,
      "freight": 0,
      "total": 0,
      "salesOrderLines": [
        {
          "tenantId": 0,
          "salesOrderId": 0,
          "productId": 0,
          "description": "string",
          "quantity": 0,
          "price": 0,
          "amount": 0,
          "discountPercentage": 0,
          "discountAmount": 0,
          "subTotal": 0,
          "taxPercentage": 0,
          "taxAmount": 0,
          "total": 0,
          "isDeleted": true,
          "deleterUserId": 0,
          "deletionTime": "2020-05-22T12:36:34.117Z",
          "lastModificationTime": "2020-05-22T12:36:34.117Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-22T12:36:34.117Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T12:36:34.117Z",
      "lastModificationTime": "2020-05-22T12:36:34.117Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T12:36:34.117Z",
      "creatorUserId": 0,
      "id": 0
    },
    "productId": 0,
    "description": "string",
    "quantity": 0,
    "price": 0,
    "amount": 0,
    "discountPercentage": 0,
    "discountAmount": 0,
    "subTotal": 0,
    "taxPercentage": 0,
    "taxAmount": 0,
    "total": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T12:36:34.117Z",
    "lastModificationTime": "2020-05-22T12:36:34.117Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T12:36:34.117Z",
    "creatorUserId": 0,
    "id": 0,
    "product": {
      "productName": "string",
      "productCode": "string",
      "barcode": "string",
      "description": "string",
      "productImageUrl": "string",
      "unitOfMeasureId": 0,
      "defaultBuyingPrice": 0,
      "defaultSellingPrice": 0,
      "branchId": 0,
      "currencyId": 0,
      "productTypeId": 0,
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-22T12:36:34.117Z",
      "lastModificationTime": "2020-05-22T12:36:34.117Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-22T12:36:34.118Z",
      "creatorUserId": 0,
      "id": 0
    }
  }
]
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the sales order to retrieve

### HTTP Request

`GET /api/services/app/Case/Delete`

This endpoint retrieves a list of products on the sales order.

# Sales Type

This is the section where the various types of sales are found.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
salesTyoeName | string | the name of the sales type
description | string | details regarding the sales type
isDeleted | boolean | checks whether a sales type is deleted or not
deleterUserId | int | the id of the user who deletes a sales type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the sale type was created
creatorUserId | int | the id of the user who created that sale type
id | int | the id of the sale type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "salesTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"salesTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"salesTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "customerId": 0,
    "salesTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "salesTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T13:14:24.858Z",
  "lastModificationTime": "2020-05-22T13:14:24.858Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T13:14:24.858Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a sales type.

### HTTP Request

`POST /api/services/app/SalesType/CreateAsync/`

## Delete

This endpoint allows you to delete particular sales type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/SalesType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "salesTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T13:14:44.327Z",
  "lastModificationTime": "2020-05-22T13:14:44.327Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T13:14:44.327Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the sales type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "salesTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-22T13:14:44.332Z",
    "lastModificationTime": "2020-05-22T13:14:44.332Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-22T13:14:44.332Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the types of sale there is in the database.

### HTTP Request

`POST /api/services/app/SalesType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/SalesType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "salesTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-22T13:14:44.457Z",
  "lastModificationTime": "2020-05-22T13:14:44.457Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-22T13:14:44.457Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Session

The api endpoint in this section will enable a user to get the current login information.

## Get the current login info

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Session/GetCurrentLoginInformations/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Session/GetCurrentLoginInformations/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Session/GetCurrentLoginInformations/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "application": {
    "version": "string",
    "releaseDate": "2020-05-22T13:41:06.466Z",
    "features": {
      "additionalProp1": true,
      "additionalProp2": true,
      "additionalProp3": true
    }
  },
  "user": {
    "name": "string",
    "surname": "string",
    "userName": "string",
    "emailAddress": "string",
    "id": 0
  },
  "tenant": {
    "tenancyName": "string",
    "name": "string",
    "id": 0
  }
}
```

# Shipment

Shipment contains detailed information about cargo on the ship. It has the following field parameters.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
shipmentName | string | the name of the shipment
salesOrderId | int | the id of the sales order
shipmentDate | datestring | the date of the shipment
shipmentTypeId | int | the id of the shipment type
warehouseId | int | the id of the warehouse
isFullShipment | bool | shows if the shipment is full or not
remarks | string | any extra information about the shipment
isDeleted | boolean | checks whether a shipment is deleted or not
deleterUserId | int | the id of the user who deletes a shipment
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the shipment was created
creatorUserId | int | the id of the user who created that shipment
id | int | the id of the shipment

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "shipmentName": " ", "salesOrderId": " ", "shipmentDate": " ", "shipmentTypeId": " ", "warehouseId": " ", "isFullShipment": " ", "remarks": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"shipmentName\": \" \",\n    \"salesOrderId\": \" \",\n    \"shipmentDate\": \" \",\n    \"shipmentTypeId\": \" \",\n    \"warehouseId\": \" \",\n    \"isFullShipment\": \" \",\n    \"remarks\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"shipmentName\": \" \",\n    \"salesOrderId\": \" \",\n    \"shipmentDate\": \" \",\n    \"shipmentTypeId\": \" \",\n    \"warehouseId\": \" \",\n    \"isFullShipment\": \" \",\n    \"remarks\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "shipmentName": " ",
    "salesOrderId": 0,
    "shipmentDate": " ",
    "shipmentTypeId": 0,
    "warehouseId": 0,
    "isFullShipment": 1,
    "remarks": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "shipmentName": "string",
  "salesOrderId": 0,
  "shipmentDate": "2020-05-25T06:18:19.420Z",
  "shipmentTypeId": 0,
  "warehouseId": 0,
  "isFullShipment": true,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:18:19.421Z",
  "lastModificationTime": "2020-05-25T06:18:19.421Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:18:19.421Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a case.

### HTTP Request

`POST /api/services/app/Shipment/CreateAsync/`

## Delete

This endpoint allows you to delete particular shipment from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/Shipment/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "shipmentName": "string",
  "salesOrderId": 0,
  "shipmentDate": "2020-05-25T06:28:16.349Z",
  "shipmentTypeId": 0,
  "warehouseId": 0,
  "isFullShipment": true,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:28:16.349Z",
  "lastModificationTime": "2020-05-25T06:28:16.349Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:28:16.349Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the shipment to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "shipmentName": "string",
    "salesOrderId": 0,
    "shipmentDate": "2020-05-25T06:40:50.240Z",
    "shipmentTypeId": 0,
    "warehouseId": 0,
    "isFullShipment": true,
    "remarks": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T06:40:50.240Z",
    "lastModificationTime": "2020-05-25T06:40:50.240Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T06:40:50.240Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the shipments.

### HTTP Request

`POST /api/services/app/Shipment/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"shipmentName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Shipment/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"shipmentName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "shipmentName": "nothing",
  "salesOrderId": 0,
  "shipmentDate": "2020-05-25T06:40:50.393Z",
  "shipmentTypeId": 0,
  "warehouseId": 0,
  "isFullShipment": true,
  "remarks": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:40:50.393Z",
  "lastModificationTime": "2020-05-25T06:40:50.393Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:40:50.393Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Shipment Type

In this section is where the user can see the types of shipment in use.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
shipmentTypeName | string | name of the shipment type
description | string | the details about the shipment type
isDeleted | boolean | checks whether a shipment type is deleted or not
deleterUserId | int | the id of the user who deletes a shipment type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the shipment type was created
creatorUserId | int | the id of the user who created that shipment type
id | int | the id of the shipment type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "shipmentTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"shipmentTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"shipmentTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "shipmentTypeName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "shipmentTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:44:33.511Z",
  "lastModificationTime": "2020-05-25T06:44:33.511Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:44:33.511Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a case.

### HTTP Request

`POST /api/services/app/ShipmentType/CreateAsync/`

## Delete

This endpoint allows you to delete particular shipment type from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/ShipmentType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "shipmentTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:45:06.523Z",
  "lastModificationTime": "2020-05-25T06:45:06.523Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:45:06.523Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the shipment type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "shipmentTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T06:45:06.529Z",
    "lastModificationTime": "2020-05-25T06:45:06.529Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T06:45:06.529Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/ShipmentType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/ShipmentType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "shipmentTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T06:45:06.652Z",
  "lastModificationTime": "2020-05-25T06:45:06.652Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T06:45:06.652Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Tenant

The tenant will be the person who uses our SCM application for service delivery and monitoring.

### Field

User attributes: 

Parameter | Type | Description
----- | ----- | --------
tenancyName | string | name of the tenancy
name | string | full name of the tenant
adminEmailAddress | string | the email address of the admin
connectionString | string | connecting the application to the DB
isActive | boolean | shows if tenant is active or not

## Create

>To create a user, use the code below:

This field will require you to enter the attributes listed in the table above. 

```csharp
var client = new RestClient("https://nmicrosscmweb.azurewebsites.net/api/services/app/Tenant/Create");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddParameter("application/json-patch+json", "{\n    \"userName\": \" \",\n    \"name\": \" \",\n    \"adminEmailAddress\": \" \",\n    \"connectionString\": \" \",\n    \"isActive\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```shell
curl --request POST \
  --url https://nmicrosscmweb.azurewebsites.net/api/services/app/Tenant/Create/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"userName": " ", "name": " ", "adminEmailAddress": " ", "connectionString": " ", "isActive": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmweb.azurewebsites.net/api/services/app/Tenant/Create/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"userName\": \" \",\n    \"name\": \" \",\n    \"adminEmailAddress\": \" \",\n    \"connectionString\": \" \",\n    \"isActive\": \" \"}"

response = http.request(request)
puts response.read_body
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "nmicrosscmweb.azurewebsites.net",
  "port": null,
  "path": "/api/services/app/Tenant/Create/",
  "headers": {
    "content-type": "application/json-patch+json",
    "cache-control": "no-cache"
  }
};

var req = http.request(options, function (res) {
  var chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    var body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.write(JSON.stringify({ tenancyName: ' ',
  name: ' ',
  surname: ' ',
  adminEmailAddress: ' ',
  connectionString: ' ',
  isActive: ' ' }));
req.end();
```
> The above command returns JSON structured like this:

```json
{
  "tenancyName": "string",
  "name": "string",
  "adminEmailAddress": "string",
  "connectionString": "string",
  "isActive": true
}

```

This endpoint creates a tenant.

### HTTP Request

`POST /api/services/app/Tenant/Create/`

<aside class="info"> since in our case we are just testing without inputting any parameters and not connected to the DB, definitely no tenant will be created.</aside>

## Delete

This endpoint allows you to delete particular tenant from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/Tenant/Delete`

## Get

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/Get/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/Get/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/Get/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenancyName": "string",
  "name": "string",
  "isActive": true,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the tenant to retrieve

## Get All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/GetAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/GetAll/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/GetAll/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "totalCount": 0,
  "items": [
    {
      "tenancyName": "string",
      "name": "string",
      "isActive": true,
      "id": 0
    }
  ]
}
```

This endpoint gets all the tenants in the database

### URL Parameters

Parameter | Description
--------- | ------- | -----------
keyWord | key word used in the search
isActive | flag showing active tenants
skipCount | shows how many times we skipped
maxResultCount | shows how to obtain maximum results

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"id\": \"5\",\n    \"tenancyName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Tenant/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"id\": \"5\",\n    \"tenancyName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenancyName": "nothing",
  "name": "string",
  "isActive": true,
  "id": 5
}
```

# Token Authentication

This is where a user gets permission to access the SCM application.

## Authenticate

> To authorize, use this code:

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/Authenticate/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"userNameOrEmailAddress\": \" \",\n    \"password\": \" \"\n,\n    \"rememberClient\": \" \"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```ruby
re 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/Authenticate/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"userNameOrEmailAddress\": \" \",\n    \"password\": \" \"\n,\n    \"rememberClient\": \" \"\n}"

response = http.request(request)
puts response.read_body
```

```shell
# With shell, you can just pass the user credentials to get the auth token
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/Authenticate/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"userNameOrEmailAddress": " ", "password": " ", "rememberClient": " "}'
```

> Make sure to fill the above fields that is `userNameOrEmailAddress`, `password`, and `rememberClient`  with your credentials.
> The above command returns JSON structured like this:
```json
{
  "accessToken": "string",
  "encryptedAccessToken": "string",
  "expireInSeconds": 0,
  "userId": 0
}
```

### HTTP Request

`POST https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/Authenticate/`

Name | Type | Description
-----|------|-------------
username | string | Username of the user
password | string | Password of the user

## Get External Authentication Providers

`GET /api/services/app/User/GetRoles`

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/GetExternalAuthenticationProviders 
   \
  --header 'cache-control: no-cache'
```

> The above code returns JSON structured like this:

```json
[
  {
    "name": "string",
    "clientId": "string"
  }
]
```
## External Authenticate

> To authorize, use this code:

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/ExternalAuthenticate/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"authProvider\": \" \",\n    \"providerKey\": \" \"\n,\n    \"providerAccessCode\": \" \"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```ruby
re 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/ExternalAuthenticate/")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"authProvider\": \" \",\n    \"providerKey\": \" \"\n,\n    \"providerAccessCode\": \" \"\n}"

response = http.request(request)
puts response.read_body
```

```shell
# With shell, you can just pass the user credentials to get the auth token
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/ExternalAuthenticate/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"authProvider": " ", "providerKey": " ", "providerAccessCode": " "}'
```

> Make sure to fill the above fields that is `authProvider`, `providerKey`, and `providerAccessCode`  with your access token provider.
> The above command returns JSON structured like this:
```json
{
  "accessToken": "string",
  "encryptedAccessToken": "string",
  "expireInSeconds": 0,
  "waitingForActivation": true
}
```

### HTTP Request

`POST https://nmicrosscmapi.azurewebsites.net/api/TokenAuth/ExternalAuthenticate/`

Model value | Type | Description
-----|------|-------------
authProvider | string | the authentication provider
providerKey | string | the key of the provider
providerAccessCode | string | the access code of the provider

# Unit of measure

Different products are measured in different standard units and this section will contain them.

### Field

Parameter | Type | Description
-------- | -------- | --------
tenantId | int | id of the tenant
unitOfMeasureName | string | name of the unit
description | string | details regarding the unit
isDeleted | boolean | checks whether a measurement unit is deleted or not
deleterUserId | int | the id of the user who deletes a unit of measurement
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the unit was created
creatorUserId | int | the id of the user who created that unit
id | int | the id of the unit

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "unitOfMeasureName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"unitOfMeasureName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"unitOfMeasureName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "unitOfMeasureName": " ",
    "description": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

> The above commands return JSON structured like this:

```json
{
  "tenantId": 0,
  "unitOfMeasureName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T11:49:13.032Z",
  "lastModificationTime": "2020-05-25T11:49:13.032Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T11:49:13.032Z",
  "creatorUserId": 0,
  "id": 0
}
```

> Response: Example Value | Value

```json
{
  "success": true,
  "message": "string",
  "data": {}
}
```
This endpoint creates a unit of measurement.

### HTTP Request

`POST /api/services/app/UnitOfMeasure/CreateAsync/`

## Delete

This endpoint allows you to delete particular unit from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/UnitOfMeasure/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "unitOfMeasureName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T11:49:43.445Z",
  "lastModificationTime": "2020-05-25T11:49:43.445Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T11:49:43.445Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the unit to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "unitOfMeasureName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T11:49:43.450Z",
    "lastModificationTime": "2020-05-25T11:49:43.450Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T11:49:43.450Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the standard units in the DB.

### HTTP Request

`POST /api/services/app/UnitOfMeasure/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UnitOfMeasure/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "unitOfMeasureName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T11:49:43.539Z",
  "lastModificationTime": "2020-05-25T11:49:43.539Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T11:49:43.539Z",
  "creatorUserId": 0,
  "id": 0
}
```



# Errors

The SCM API uses the following error codes:

Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
403 | Forbidden -- The endpoint requested is hidden for administrators only.
404 | Not Found -- The specified module could not be found.
405 | Method Not Allowed -- You tried to access a module with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The endpoint requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many modules! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
