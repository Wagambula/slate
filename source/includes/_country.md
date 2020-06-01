
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
