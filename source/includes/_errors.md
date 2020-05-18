# Cash Bank

This module majorly deals with the money in the Bank for the SCM transaction, simply, these are the banks which are working with the stakeholders, the cash is wired to accounts in these banks.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
cashBankName | string | the id of the customer
description | string | details regarding the bank
isDeleted | boolean | checks whether a transaction is deleted or not
deleterUserId | int | the id of the user who deletes a case
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the transaction was created
creatorUserId | int | the id of the user who created that transaction
id | int | the id of the transaction

## Create Cash Bank

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "cashBankName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"cashBankName\": \" \",\n    \"description\": \" \", \n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"cashBankName\": \" \",\n    \"description\": \" \", \n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "cashBankName": "",
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
  "cashBankName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-14T19:33:04.454Z",
  "lastModificationTime": "2020-05-14T19:33:04.454Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-14T19:33:04.454Z",
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
This endpoint creates a bank transaction.

### HTTP Request

`POST /api/services/app/Case/CreateAsync/`

## Delete

This endpoint allows you to delete particular transaction from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/CashBank/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "cashBankName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T07:55:15.984Z",
  "lastModificationTime": "2020-05-15T07:55:15.984Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T07:55:15.984Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the transaction to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "cashBankName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-15T07:57:13.553Z",
    "lastModificationTime": "2020-05-15T07:57:13.553Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T07:57:13.553Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/CashBank/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"cashBankName\": \"moroto\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"cashBankName\": \"moroto\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "cashBankName": "moroto",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T07:58:43.022Z",
  "lastModificationTime": "2020-05-15T07:58:43.022Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T07:58:43.022Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Comments

In this section, a tenant is able to view comments regarding the use of the SCM service provision. It has the following field parameters.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
comment | string | the comment which has been posted by the user(s)
isRead | bool | shows if the comment has been read or not
isDeleted | boolean | checks whether a comment is deleted or not
deleterUserId | int | the id of the user who deletes a comment
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the comment was created
creatorUserId | int | the id of the user who created that comment
id | int | the id of the comment

## Create Comment

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "comment": " ", "isRead": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"comment\": \" \",\n    \"isRead\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"comment\": \" \",\n    \"isRead\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "comment": " ",
    "isRead": true,
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
  "comment": "string",
  "isRead": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T09:45:34.822Z",
  "lastModificationTime": "2020-05-15T09:45:34.822Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T09:45:34.822Z",
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
This endpoint creates a comment.

### HTTP Request

`POST /api/services/app/Comments/CreateAsync/`


## Delete Comment

This endpoint allows you to delete particular comment from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Comments/Delete`

## Get Comment By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "comment": "string",
  "isRead": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T10:00:40.547Z",
  "lastModificationTime": "2020-05-15T10:00:40.547Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T10:00:40.547Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the comment to retrieve

## List All Comments

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "comment": "string",
    "isRead": true,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-15T10:03:14.140Z",
    "lastModificationTime": "2020-05-15T10:03:14.140Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T10:03:14.140Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the comments.

### HTTP Request

`POST /api/services/app/Comments/ListAll/`

## Update Comments

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"2\",\n    \"comment\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"2\",\n    \"comment\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 2,
  "comment": "nothing",
  "isRead": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T10:04:36.588Z",
  "lastModificationTime": "2020-05-15T10:04:36.588Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T10:04:36.588Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Configuration

This endpoint allows a user to change a theme for the User Interface.

### HTTP Request

`/api/services/app/Configuration/ChangeUiTheme/`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
theme | the new theme to be used

# Country

This module contains details of the country where the user resides. It has the following field parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
countryName | string | the name of the country
countryZone | string | the zone for the country
isDeleted | boolean | checks whether a country is deleted or not
deleterUserId | int | the id of the user who deletes a country
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the country was created/ added in the DB
creatorUserId | int | the id of the user who created that case
id | int | the id of the country

## Create Country

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "countryName": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"countryName\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"countryName\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "countryName": "string",
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
  "countryName": "string",
  "countryZone": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T12:28:50.683Z",
  "lastModificationTime": "2020-05-15T12:28:50.683Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T12:28:50.683Z",
  "creatorUserId": 0,
  "id": 0
}
```

This endpoint creates a country in the database.

### HTTP Request

`POST /api/services/app/Country/CreateAsync/`

## Delete Country

This endpoint allows you to delete particular country from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Country/Delete`

## Get Country By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "countryName": "string",
  "countryZone": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T12:44:32.883Z",
  "lastModificationTime": "2020-05-15T12:44:32.883Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T12:44:32.883Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Country to retrieve


## List All Countries

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "countryName": "string",
    "countryZone": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-15T12:46:08.181Z",
    "lastModificationTime": "2020-05-15T12:46:08.181Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T12:46:08.181Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/Country/ListAll/`

## Update Country

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"countryName\": \"uganda\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"countryName\": \"uganda\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "countryName": "uganda",
  "countryZone": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T12:47:48.567Z",
  "lastModificationTime": "2020-05-15T12:47:48.567Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T12:47:48.567Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Currency

This field shows the various currencies which can be used to effect payments. Has the following field parameters;

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
currencyName | string | the name of the currency
currencyCode | string | the code for the currency
description | string | details regarding the currency, conversion rate,...
isDeleted | boolean | checks whether a currency is deleted or not
deleterUserId | int | the id of the user who deletes a currency
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the currency was created/ added in the DB
creatorUserId | int | the id of the user who created that currency
id | int | the id of the currency

## Create Currency

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "currenyName": " ", "currenyCode": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Country/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"currencyName\": \" \",\n    \"currencyCode\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"currencyName\": \" \",\n    \"currencyCode\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
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
  "currencyName": "string",
  "currencyCode": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T12:56:37.288Z",
  "lastModificationTime": "2020-05-15T12:56:37.288Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T12:56:37.288Z",
  "creatorUserId": 0,
  "id": 0
}
```

This endpoint creates a currency in the database.

### HTTP Request

`POST /api/services/app/Currency/CreateAsync/`

## Delete Currency
This endpoint allows you to delete particular currency from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Currency/Delete`

## Get Currency By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "currencyName": "string",
  "currencyCode": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T13:07:53.235Z",
  "lastModificationTime": "2020-05-15T13:07:53.235Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T13:07:53.235Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Currency to retrieve


## List All Currencies

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "currencyName": "string",
    "currencyCode": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-15T13:05:28.552Z",
    "lastModificationTime": "2020-05-15T13:05:28.552Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T13:05:28.552Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the currencies.

### HTTP Request

`POST /api/services/app/Currency/ListAll/`

## Update Currency

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"currencyName\": \"shillings\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Currency/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"currencyName\": \"shillings\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "currencyName": "shillings",
  "currencyCode": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T13:01:56.177Z",
  "lastModificationTime": "2020-05-15T13:01:56.177Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T13:01:56.177Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Customer

The customer module comprises of details about the customers. It has the following field parameters

### Fields

Name | Type | Description
-----|------|-------------
tenantId   | int  | The tenant unique ID
customerName | string | name of the user
customerTypeId  | int | id of the customer type
contactPerson | string | Username of the person to contact
idNumber | string | the Id number of the customer
idType | string | Type of the Id
accountType | string | type of the customer account
email | string | Email of the customer
accountNumber | int | customer' account number
referenceNumber | int | customer's reference number
imageLocation | string | location of the photo 
website | string | customer' website
industry | string | for the customer
rating | string | customer's rating for the services
phoneAlternative | string | alternative phone number for the customer
gender | string | Gender as provided by the customer. Can be "Male", "Female" or "Transgender"
address1 | string | Address provided by the customer
address2 | string | Address provided by the user
city | string | City provided by the customer
zipcode | string | Pincode provided by the customer
state | string | State provided by the customer
phone | string | Phone provided by the customer

## Create Customer

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
  "tenantId": 0,
  "customerName": " ",
  "customerTypeId": 0,
  "address": " ",
  "city": " ",
  "state": " ",
  "zipCode": " ",
  "phone": " ",
  "email": " ",
  "contactPerson": " ",
  "idNumber": " ",
  "idType": " ",
  "accountType": " ",
  "xcoordinate": 0,
  "ycoordinate": 0,
  "accountNumber": 0,
  "referenceNumber": 0,
  "imagelocation": " ",
  "website": " ",
  "industry": " ",
  "rating": " ",
  "phoneAlternative": " ",
  "countryId": 0,
  "country": {
    "tenantId": 0,
    "countryName": " ",
    "countryZone": " ",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": " ",
    "lastModificationTime": " ",
    "lastModifierUserId": 0,
    "creationTime": " ",
    "creatorUserId": 0,
    "id": 0
  },
  "parent_CustomerId_Id": 0,
  "email2": " ",
  "ownership": " ",
  "taxId": " ",
  "vatNo": " ",
  "gender": " ",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": " ",
  "lastModificationTime": " ",
  "lastModifierUserId": 0,
  "creationTime": "",
  "creatorUserId": 0,
  "id": 0
}
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
    "deletionTime": "2020-05-15T13:40:00.802Z",
    "lastModificationTime": "2020-05-15T13:40:00.802Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T13:40:00.802Z",
    "creatorUserId": 0,
    "id": 0
  },
  "parent_CustomerId_Id": 0,
  "email2": "string",
  "ownership": "string",
  "taxId": "string",
  "vatNo": "string",
  "gender": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T13:40:00.802Z",
  "lastModificationTime": "2020-05-15T13:40:00.802Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T13:40:00.802Z",
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

`POST /api/services/app/Customer/CreateAsync/`

## Delete Customer

This endpoint allows you to delete particular customer from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Customer/Delete`

## Get Customer By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
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
    "deletionTime": "2020-05-15T13:47:53.339Z",
    "lastModificationTime": "2020-05-15T13:47:53.339Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T13:47:53.339Z",
    "creatorUserId": 0,
    "id": 0
  },
  "parent_CustomerId_Id": 0,
  "email2": "string",
  "ownership": "string",
  "taxId": "string",
  "vatNo": "string",
  "gender": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T13:47:53.339Z",
  "lastModificationTime": "2020-05-15T13:47:53.339Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T13:47:53.339Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the customer to retrieve

## List All Customers

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
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
      "deletionTime": "2020-05-15T13:49:50.590Z",
      "lastModificationTime": "2020-05-15T13:49:50.590Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-15T13:49:50.590Z",
      "creatorUserId": 0,
      "id": 0
    },
    "parent_CustomerId_Id": 0,
    "email2": "string",
    "ownership": "string",
    "taxId": "string",
    "vatNo": "string",
    "gender": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-15T13:49:50.590Z",
    "lastModificationTime": "2020-05-15T13:49:50.590Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T13:49:50.590Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the customers.

### HTTP Request

`POST /api/services/app/Customer/ListAll/`

## Update Customer

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"customerName\": \" \",\n    \"customerTypeId\": \"v\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Customer/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"customerName\": \"\",\n    \"customerTypeId\": \" \"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
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
    "deletionTime": "2020-05-15T13:52:08.520Z",
    "lastModificationTime": "2020-05-15T13:52:08.521Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-15T13:52:08.521Z",
    "creatorUserId": 0,
    "id": 0
  },
  "parent_CustomerId_Id": 0,
  "email2": "string",
  "ownership": "string",
  "taxId": "string",
  "vatNo": "string",
  "gender": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-15T13:52:08.521Z",
  "lastModificationTime": "2020-05-15T13:52:08.521Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-15T13:52:08.521Z",
  "creatorUserId": 0,
  "id": 0
}
```

## Get Acc Type

### HTTP Request

`GET /api/services/app/Customer/GetAccType/`

<aside class="info">These fields don't take any parameters currently.</aside>

## Get Id Type

### HTTP Request

`GET /api/services/app/Customer/GetIdType/`

<aside class="info">These fields don't take any parameters currently.</aside>

## Get Gendor

### HTTP Request

`GET /api/services/app/Customer/GetGender/`

<aside class="info">These fields don't take any parameters currently.</aside>

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
