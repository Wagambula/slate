
# Branch

This is a section for Branches. It has the following fields;

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
branchName | string | the name of the branch
description | string | details regarding the branch
currencyId | int | the id of the currency
address | string | the branch's address
city | string | the city where the branch is located
state | string | the state where this city is found (Read only)
zipcode | string | State of the branch in ISO 3166-2:IN format (https://en.wikipedia.org/wiki/ISO_3166-2:IN)
phone | string | the branch's contact
email | string | the email for the branch
contactPerson | string | the details for the person to contact at the branch
isDeleted | boolean | checks whether a branch is deleted or not
deleterUserId | int | the id of the user who deletes a branch
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the branch was created
creatorUserId | int | the id of the user who created that branch
id | int | the id of the branch

## Create Branch

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

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"branchName\": \" \",\n    \"description\": \" \",\n    \"currencyId\": \" \",\n    \"address\": \" \",\n    \"city\": \" \",\n    \"state\": \" \",\n    \"zipcode\": \" \",\n    \"phone\": \" \",\n    \"email\": \" \",\n    \"contactPerson\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"branchName\": \" \",\n    \"description\": \" \",\n    \"currencyId\": \" \",\n    \"address\": \" \",\n    \"city\": \" \",\n    \"state\": \" \",\n    \"zipcode\": \" \",\n    \"phone\": \" \",\n    \"email\": \" \",\n    \"contactPerson\":  \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "branchName": " ",
    "description": " ",
    "currencyId": 0,
    "address": " ",
    "city": " ",
    "state": " ",
    "zipCode": " ",
    "phone": " ",
    "email": " ",
    "contactPerson": " ",
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
  "deletionTime": "2020-05-13T21:36:06.507Z",
  "lastModificationTime": "2020-05-13T21:36:06.507Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T21:36:06.507Z",
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

`POST /api/services/app/Branch/CreateAsync/`
## Delete Branch

This endpoint allows you to delete particular branch from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Branch/Delete`

## Get Branch By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
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
  "deletionTime": "2020-05-13T22:05:02.324Z",
  "lastModificationTime": "2020-05-13T22:05:02.324Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T22:05:02.324Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Branch to retrieve

## List All Branches

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
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
    "deletionTime": "2020-05-13T22:01:49.678Z",
    "lastModificationTime": "2020-05-13T22:01:49.678Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-13T22:01:49.678Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the branches.

### HTTP Request

`POST /api/services/app/Branch/ListAll/`

## Update Branch

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"northern\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Branch/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \"5\",\n    \"description\": \"northern\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
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
  "deletionTime": "2020-05-13T21:57:18.917Z",
  "lastModificationTime": "2020-05-13T21:57:18.917Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T21:57:18.917Z",
  "creatorUserId": 0,
  "id": 0
}
```
# Case

This will deal with different instances or scenarios for the flow of events in the SCM transaction process. It has the following fields:

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
customerId | int | the id of the customer
description | string | details regarding the branch
subject | string | the subject of the case
resolution | string | the Case's resolution
assignedTo | int | *the person it's assigned to
Priority | int | the priority of the Case
status | bool | the status of the Case
CaseType | int | the type of the Case
tag | string | the tag for the case
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a case
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the branch was created
creatorUserId | int | the id of the user who created that case
id | int | the id of the case


## Create case

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "customerId": " ", "subject": " ", "description": " ", "resolution": " ", "assignedTo": " ", "priority": " ", "status": " ", "caseType": " ", "tag": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"customerId\": \" \",\n    \"subject\": \" \",\n    \"description\": \" \",\n    \"resolution\": \" \",\n    \"assignedTo\": \" \",\n    \"priority\": \" \",\n    \"status\": \" \",\n    \"caseType\": \" \",\n    \"tag\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"customerId\": \" \",\n    \"subject\": \" \",\n    \"description\": \" \",\n    \"resolution\": \" \",\n    \"assignedTo\": \" \",\n    \"priority\": \" \",\n    \"status\": \" \",\n    \"caseType\": \" \",\n    \"tag\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "customerId": 0,
    "subject": " ",
    "description": " ",
    "resolution": " ",
    "assignedTo": 0,
    "priority": 1,
    "status": 1,
    "caseType": 1,
    "tag": "string",
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
  "customerId": 0,
  "subject": "string",
  "description": "string",
  "resolution": "string",
  "assignedTo": 0,
  "priority": 1,
  "status": 1,
  "caseType": 1,
  "tag": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T23:10:43.315Z",
  "lastModificationTime": "2020-05-13T23:10:43.315Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T23:10:43.315Z",
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

`POST /api/services/app/Case/CreateAsync/`

## Delete Case

This endpoint allows you to delete particular Case from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Case/Delete`

## Get Case By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "customerId": 0,
  "subject": "string",
  "description": "string",
  "resolution": "string",
  "assignedTo": 0,
  "priority": 1,
  "status": 1,
  "caseType": 1,
  "tag": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T23:38:40.130Z",
  "lastModificationTime": "2020-05-13T23:38:40.130Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T23:38:40.131Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Case to retrieve

## List All Cases

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "customerId": 0,
    "subject": "string",
    "description": "string",
    "resolution": "string",
    "assignedTo": 0,
    "priority": 1,
    "status": 1,
    "caseType": 1,
    "tag": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-13T23:36:26.516Z",
    "lastModificationTime": "2020-05-13T23:36:26.516Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-13T23:36:26.516Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/Case/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"customerId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"customerId\": \"5\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "customerId": 5,
  "subject": "string",
  "description": "nothing",
  "resolution": "string",
  "assignedTo": 0,
  "priority": 1,
  "status": 1,
  "caseType": 1,
  "tag": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-13T23:33:24.635Z",
  "lastModificationTime": "2020-05-13T23:33:24.635Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-13T23:33:24.635Z",
  "creatorUserId": 0,
  "id": 0
}
```

## Get Priority Case

This endpoint will retrieve the Case with the highest priority.

### HTTP Request

`POST /api/services/app/Case/GetPriority/`

## Get Case Type

This endpoint will retrieve the Case Category.

### HTTP Request

`POST /api/services/app/Case/GetCaseType/`

## Get Case Status

This endpoint will retrieve the Case Status.

### HTTP Request

`POST /api/services/app/Case/GetCaseStatus/`