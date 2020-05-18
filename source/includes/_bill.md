
# Bill

This section will deal with the billing process in the SCM transaction. It contains the following arguments

Argument | Type | Description
-------- | ------ | ---------
Tenant id | int | the id of the tenant
Bill id | int | the bill's unique number
Bill Name | string | the name of the bill
GoodsReceivedNote id | int | the id for GRN
VendorDONumber | string | the vendor's transaction number
VendorInvoiceNumber | string | the invoice number of the vendor
Bill Date | Date | the date of the billing
BillDueDate | Date | the date in which the bill is made promptly
BillTypeId | Int | the id of the bill type

## Create Bill

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"tenantId": " ", "billId": " ", "billName": " ", "goodsReceivedNoteId": " ", "vendorDONumber": " ", "vendorInvoiceNumber": " ", "billDate": " ", "billDueDate": " ", "billTypeId": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ", "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"billId\": \" \",\n    \"billName\": \" \",\n    \"goodsReceivedNoteId\": \" \",\n    \"vendorDONumber\": \" \",\n    \"vendorInvoiceNumber\": \" \",\n    \"billDate\": \" \",\n    \"billDueDate\": \" \",\n    \"billTypeId\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n \"deletionTime\": \" \",\n \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"billId\": \" \",\n    \"billName\": \" \",\n    \"goodsReceivedNoteId\": \" \",\n    \"vendorDONumber\": \" \",\n    \"vendorInvoiceNumber\": \" \",\n    \"billDate\": \" \",\n    \"billDueDate\": \" \",\n    \"billTypeId\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n \"deletionTime\": \" \",\n \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json'
));

$request->setBody('{
    "tenantId": "" ,
    "billId": "",
    "billName": " ",
    "goodsReceivedNoteId": " ",
    "vendorDONumber": " ",
    "vendorInvoiceNumber": " ",
    "billDate": " ",
    "billDueDate": " ",
    "billTypeId": 0,
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
  "billId": 0,
  "billName": "string",
  "goodsReceivedNoteId": 0,
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "billDate": "2020-05-13T16:33:51.472Z",
  "billDueDate": "2020-05-13T16:33:51.472Z",
  "billTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T16:33:51.472Z",
  "lastModificationTime": "2020-05-13T16:33:51.472Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T16:33:51.472Z",
  "creatorUserId": 0,
  "id": 0
}

```

This endpoint creates a bill.

### HTTP Request

`POST /api/services/app/Bill/CreateAsync/`

<aside class="info">All the responses in the <strong>POST</strong> data are just test examples, in fact, the API currently isn't connected to the DB so no data from the DB is being retrieved.</aside>

## Delete Bill

This endpoint allows you to delete particular bill. Please be aware this will delete all the data related to the bill. The operation is ir reversible

### HTTP Request

`/api/services/app/Bill/Delete`

## Get Bill By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "billId": 0,
  "billName": "string",
  "goodsReceivedNoteId": 0,
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "billDate": "2020-05-13T18:34:34.837Z",
  "billDueDate": "2020-05-13T18:34:34.837Z",
  "billTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T18:34:34.837Z",
  "lastModificationTime": "2020-05-13T18:34:34.837Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T18:34:34.837Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Bill to retrieve

## List All Bills
```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
[
  {
    "tenantId": 0,
    "billId": 0,
    "billName": "string",
    "goodsReceivedNoteId": 0,
    "vendorDONumber": "string",
    "vendorInvoiceNumber": "string",
    "billDate": "2020-05-13T18:43:39.953Z",
    "billDueDate": "2020-05-13T18:43:39.953Z",
    "billTypeId": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-13T18:43:39.953Z",
    "lastModificationTime": "2020-05-13T18:43:39.953Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-13T18:43:39.953Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the bills issued during for every transaction.

### HTTP Request

`POST /api/services/app/Bill/ListAll/`

## Update Bill

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"12\",\n    \"billTypeName\": \"Tissue\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \"12\",\n    \"billTypeName\": \"Tissue\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "billId": 0,
  "billName": "string",
  "goodsReceivedNoteId": 0,
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "billDate": "2020-05-13T19:47:06.904Z",
  "billDueDate": "2020-05-13T19:47:06.904Z",
  "billTypeId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T19:47:06.904Z",
  "lastModificationTime": "2020-05-13T19:47:06.904Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T19:47:06.904Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Bill Type

The bill type shows the type of bill being used by the tenant or user during the transaction. It has the following field arguments

### Fields

Name | Type | Description
-----|------|-------------
TenantId | int | The id of the tenant
BillTypeName | string | the name of the bill type
Description | string | the description of the bill type
isDeleted | boolean | a flag to show whether the bill type is deleted or not
deleterUserId | int | the id of the user who deletes the bill type
deletionTime | date | the date and time of deletion
lastModificationTime | date | the date and time during which it was last modified
lastModifierUserId | int | the id of the user who modified it last
creationTime | date | the time of creation of the bill type
creationUserId | int | the id of the user who created it
id | int | the id of the bill type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' \
  --data '{"tenantId": " ", "billTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"billTypeName\": \" \",\n    \"description\": \" \",\n    \"isDeleted\": \" \",\n    \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"billDate\": \" \",\n    \"billDueDate\": \" \",\n    \"billTypeId\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"billTypeName\": \" \",\n    \"description\": \" \",\n    \"isDeleted\": \" \",\n    \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"billDate\": \" \",\n    \"billDueDate\": \" \",\n    \"billTypeId\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Bill/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "billTypeName": " ",
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
  "billTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T19:49:04.554Z",
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

`POST /api/services/app/BillType/CreateAsync/`

## Delete

This endpoint allows you to delete particular bill type. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/BillType/Delete`

## Get by Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "billTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T21:11:46.588Z",
  "lastModificationTime": "2020-05-13T21:11:46.588Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T21:11:46.588Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the BillType to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "billTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-13T21:23:17.142Z",
    "lastModificationTime": "2020-05-13T21:23:17.142Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-13T21:23:17.143Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the bill types issued for every transaction.

### HTTP Request

`POST /api/services/app/BillType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"1\",\n    \"billTypeName\": \"nmicros\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/BillType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \"1\",\n    \"billTypeName\": \"nmicros\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "billTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T18:56:49.813Z",
  "lastModificationTime": "2020-05-13T18:56:49.813Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T18:56:49.813Z",
  "creatorUserId": 0,
  "id": 0
}
```
