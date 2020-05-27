---
title: SCM API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL
  - ruby: Ruby
  - php: PHP
  - csharp: C#
  - javascript: NodeJS

includes:

  - errors   

search: true
---

# Introduction

Welcome to the SCM API! You can use our API to access SCM API endpoints, which can get information on various details such as Invoice, products, among others in our database.

We have language bindings in Shell, Ruby, PHP, and JavaScript! You can read this for proper usage of our Supply Chain Management System.

Thi API documentation page was created with [Nmicros](https://nmicros.com/). Feel free to check out other services that we offer.
First things first we have to [Sign in](https://nmicrosscmweb.azurewebsites.net/Account/Login?ReturnUrl=%2F) to the SCM website in order to use our API Endpoints. The API endpoint for SCM can be found by clicking the link [here](https://nmicrosscmapi.azurewebsites.net/)

In order to access the api, from the api endpoint, click authorize and login with your details. Note that you've to be registered for the supply chain application.

# Account

This deals with authorization of tenants

## Register Tenant

To register a tenant, make a POST request with the given endpoint with the attributes below.

Attribute | Type | Description
-----|------|-------------
Name | string | Name of the tenant
Surname | string | Surname of the tenant
Username | string | User name of the tenant
email Address | string | the tenant's email address
password | string | the password of the tenant

> To register a tenant in the database, use the code below:

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Account/Register \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json' 
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Account/Register")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Account/Register/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
IRestResponse response = client.Execute(request);
```

> The above code returns example values structured like this:

```json
{
  "name": "string",
  "surname": "string",
  "userName": "string",
  "emailAddress": "string",
  "password": "string",
  "captchaResponse": "string"
}
```

## Confirm existance of a tenant

This endpoint will check whether the supplied tenant's name exist in the system

### HTTP Request

`POST /api/services/app/Account/IsTenantAvailable`

# Accounts

This is a detailed section about accounts with the following arguments.

Argument | Description
--------- | ----------
Customer ID | The id of the customer
parent Account ID | The ID of the parent account
Tenant ID | The tenant's identification
Customer Name | The name of the customer
Customer Type ID | The identification of the customer type
Address | The customer's address
City | The city where the customer lives
State | The state where the city is located
Zipcode | Customer's postal code
Phone | Telephone number of the customer
Email | Customer's email address
Contact Person | The person to contact in case of emergency

## Creat Async

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/CreateAsync \
  --header 'cache-control: no-cache'
```
```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
response = http.request(request)
puts response.read_body
```
```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
IRestResponse response = client.Execute(request);
```
```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json'
));


try {
  $response = $request->send();

  //echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```
> The above code returns JSON structured like this:

```json
{
  "customerId": 0,
  "parentAccountId": 0,
  "tenantId": 0,
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
      "deletionTime": "2020-05-11T17:27:37.041Z",
      "lastModificationTime": "2020-05-11T17:27:37.041Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-11T17:27:37.041Z",
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
        "deletionTime": "2020-05-11T17:27:37.042Z",
        "lastModificationTime": "2020-05-11T17:27:37.042Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-11T17:27:37.042Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-11T17:27:37.042Z",
    "lastModificationTime": "2020-05-11T17:27:37.042Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-11T17:27:37.042Z",
    "creatorUserId": 0,
    "id": 0
  },
  "totalLoanAmount": 0,
  "totalAmountPaid": 0,
  "balance": 0,
  "is_Open": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-11T17:27:37.042Z",
  "lastModificationTime": "2020-05-11T17:27:37.042Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-11T17:27:37.042Z",
  "creatorUserId": 0,
  "id": 0
}
```

### HTTP Request

`POST /api/services/app/Accounts/CreateAsync`

## Delete Accounts

This end point gives you the opportunity to delete a customer's account from our DB. Please note that all the information related to the account in question will be removed and that the process is irreversible.
### HTTP Request

`DELETE /api/services/app/Accounts/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```
```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/GetById/ \
  --header 'cache-control: no-cache'
```
```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above code returns JSON structured like this:

```json
{
  "customerId": 0,
  "parentAccountId": 0,
  "tenantId": 0,
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
      "deletionTime": "2020-05-11T20:04:15.229Z",
      "lastModificationTime": "2020-05-11T20:04:15.229Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-11T20:04:15.229Z",
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
        "deletionTime": "2020-05-11T20:04:15.230Z",
        "lastModificationTime": "2020-05-11T20:04:15.230Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-11T20:04:15.230Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-11T20:04:15.230Z",
    "lastModificationTime": "2020-05-11T20:04:15.230Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-11T20:04:15.230Z",
    "creatorUserId": 0,
    "id": 0
  },
  "totalLoanAmount": 0,
  "totalAmountPaid": 0,
  "balance": 0,
  "is_Open": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-11T20:04:15.230Z",
  "lastModificationTime": "2020-05-11T20:04:15.230Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-11T20:04:15.230Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the account to retrieve

## List all

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/ListAll")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/ListAll/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/ListAll/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```
> The above command returns JSON structured like this:

```json
[
  {
    "customerId": 0,
    "parentAccountId": 0,
    "tenantId": 0,
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
        "deletionTime": "2020-05-11T20:13:34.057Z",
        "lastModificationTime": "2020-05-11T20:13:34.057Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-11T20:13:34.057Z",
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
          "deletionTime": "2020-05-11T20:13:34.057Z",
          "lastModificationTime": "2020-05-11T20:13:34.057Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-11T20:13:34.057Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-11T20:13:34.057Z",
      "lastModificationTime": "2020-05-11T20:13:34.057Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-11T20:13:34.057Z",
      "creatorUserId": 0,
      "id": 0
    },
    "totalLoanAmount": 0,
    "totalAmountPaid": 0,
    "balance": 0,
    "is_Open": true,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-11T20:13:34.057Z",
    "lastModificationTime": "2020-05-11T20:13:34.057Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-11T20:13:34.057Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

## Update Accounts
```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n\t\"password\": \"password\"\n}"

response = http.request(request)
puts response.read_body
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/Update/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json'
));

$request->setBody('{
	"password": "password"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n\t\"password\": \"password\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "customerId": 0,
  "parentAccountId": 0,
  "tenantId": 0,
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
      "deletionTime": "2020-05-11T20:18:19.031Z",
      "lastModificationTime": "2020-05-11T20:18:19.031Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-11T20:18:19.031Z",
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
        "deletionTime": "2020-05-11T20:18:19.032Z",
        "lastModificationTime": "2020-05-11T20:18:19.032Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-11T20:18:19.032Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-11T20:18:19.032Z",
    "lastModificationTime": "2020-05-11T20:18:19.032Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-11T20:18:19.032Z",
    "creatorUserId": 0,
    "id": 0
  },
  "totalLoanAmount": 0,
  "totalAmountPaid": 0,
  "balance": 0,
  "is_Open": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-11T20:18:19.032Z",
  "lastModificationTime": "2020-05-11T20:18:19.032Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-11T20:18:19.032Z",
  "creatorUserId": 0,
  "id": 0
}
```


# Activities

This section contains an description of the flow of events as tenants interact with suppliers and all other stakeholders. Table below shows the arguments used.

Argument | Type | Description
---- | -------- | ----------
Tenant ID | Int | The id of the tenant
Activity Name | string | The name of the activity
Description | string | The details of the activity

## Create Async

> To create an activity, use this code:

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/CreateAsync");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
IRestResponse response = client.Execute(request);
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "nmicrosscmapi.azurewebsites.net",
  "port": null,
  "path": "/api/services/app/Activities/CreateAsync",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({ tenantId: '9',
  activityName: '',
  description: '',
  isDeleted: '',
  deleterUserId: '',
  deletionTime: '',
  lastModificationTime: '',
  creationTime: '',
  creatorUserId: '',
  id: ''  }));
req.end();
```
> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "activityName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-12T14:30:48.782Z",
  "lastModificationTime": "2020-05-12T14:30:48.782Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-12T14:30:48.782Z",
  "creatorUserId": 0,
  "id": 0
}
```
## Delete

This endpoint ebables us to delete a particular activity.

### HTTP Request

`DELETE /api/services/app/Activities/Delete`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the activity to retrieve

## Get activity by id

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/GetById \
  --header 'cache-control: no-cache'
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "activityName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-12T20:31:02.328Z",
  "lastModificationTime": "2020-05-12T20:31:02.328Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-12T20:31:02.328Z",
  "creatorUserId": 0,
  "id": 0
}
```

## List All

### HTTP Request

`POST /api/services/app/Activities/ListAll`

This endpoint lists all the activities in the SCM application

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json'
request["cache-control"] = 'no-cache'
request.body = "{\n\t\"password\": \"password\"\n}"

response = http.request(request)
puts response.read_body
```
```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/Update/');
$request->setMethod(HTTP_METH_PUT);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json'
));

$request->setBody('{
	"password": "password"
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json");
request.AddParameter("application/json", "{\n\t\"password\": \"password\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```javascript
var http = require("http");

var options = {
  "method": "PUT",
  "hostname": "nmicrosscmapi.azurewebsites.net",
  "port": null,
  "path": "/api/services/app/Activities/Update/",
  "headers": {
    "content-type": "application/json",
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

req.write(JSON.stringify({ password: 'password' }));
req.end();
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "activityName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-12T20:45:39.921Z",
  "lastModificationTime": "2020-05-12T20:45:39.921Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-12T20:45:39.921Z",
  "creatorUserId": 0,
  "id": 0
}
```

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
This endpoint creates a case.

### HTTP Request

`POST /api/services/app/Case/CreateAsync/`

## Delete Case

This endpoint allows you to delete particular Case from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/Case/Delete`

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

# Customer Type

The customer type module entails different categories of a customer with the following field parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
customerTypeName | string | the name of the customer type
description | string | details regarding the type of the customer
isDeleted | boolean | checks whether a customer type is deleted or not
deleterUserId | int | the id of the user who deletes this section
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the customer type was created
creatorUserId | int | the id of the user who created that customer type
id | int | the id for the customer type

## Create 

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "customerTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"customerTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"customerTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
  "tenantId": 0,
  "customerTypeName": " ",
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
  "customerTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T09:13:52.435Z",
  "lastModificationTime": "2020-05-19T09:13:52.435Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T09:13:52.435Z",
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
This endpoint creates a customer type.

### HTTP Request

`POST /api/services/app/CustomerType/CreateAsync/`

## Delete

This endpoint allows you to delete a customer type section from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/CustomerType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "customerTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T09:40:54.768Z",
  "lastModificationTime": "2020-05-19T09:40:54.768Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T09:40:54.768Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the Customer Type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "customerTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-19T09:44:07.797Z",
    "lastModificationTime": "2020-05-19T09:44:07.797Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-19T09:44:07.797Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Categories of customers in our DB.

### HTTP Request

`POST /api/services/app/CustomerType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"customerTypeName\": \"supplier\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CustomerType/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"customerTypeName\": \"supplier\",\n    \"description\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "customerTypeName": "supplier",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T09:46:27.672Z",
  "lastModificationTime": "2020-05-19T09:46:27.673Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T09:46:27.673Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Documents

The documents module is where you can find any details regarding the paper work involved for a successful transaction. It has the following fields.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
documentName | string | the name of the document
documentLocation | string | details regarding the path of the document
customer | string | the document is about which customer
parent_customerId_Id | string | the id of the customer's parent
email2 | string | the email on the document
ownership | string | the owner for the document
taxId | string | the tax identification of the customer
VatNo | string | the VAT number of the customer in the document
gendor | string | the sex for the customer
isDeleted | boolean | checks whether a document is deleted or not
deleterUserId | int | the id of the user who deletes a document
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the document was created
creatorUserId | int | the id of the user who created that document
id | int | the id of the document

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "documentName": " ", "documentLocation": " ", "documentType": " ", "customer": " ", "accounts": " ", "country": " ", "parent_customerId_id": " ", "email2": " ", "ownership": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{"tenantId": " ", "documentName": " ", "documentLocation": " ", "documentType": " ", "customer": " ", "accounts": " ", "country": " ", "parent_customerId_id": " ", "email2": " ", "ownership": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"customerId\": \" \",\n    \"subject\": \" \",\n    \"description\": \" \",\n    \"resolution\": \" \",\n    \"assignedTo\": \" \",\n    \"priority\": \" \",\n    \"status\": \" \",\n    \"caseType\": \" \",\n    \"tag\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/CreateAsync/');
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
  "documentName": "string",
  "documentLocation": "string",
  "documentTypes": 1,
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
      "deletionTime": "2020-05-19T10:06:38.571Z",
      "lastModificationTime": "2020-05-19T10:06:38.571Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-19T10:06:38.571Z",
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
        "deletionTime": "2020-05-19T10:06:38.571Z",
        "lastModificationTime": "2020-05-19T10:06:38.571Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-19T10:06:38.571Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-19T10:06:38.571Z",
    "lastModificationTime": "2020-05-19T10:06:38.571Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-19T10:06:38.571Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T10:06:38.572Z",
  "lastModificationTime": "2020-05-19T10:06:38.572Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T10:06:38.572Z",
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
This endpoint creates a document.

### HTTP Request

`POST /api/services/app/Documents/CreateAsync/`

## Delete
This endpoint allows you to delete particular document from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Case/Delete`

## Get Document By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "documentName": "string",
  "documentLocation": "string",
  "documentTypes": 1,
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
      "deletionTime": "2020-05-19T10:01:47.194Z",
      "lastModificationTime": "2020-05-19T10:01:47.194Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-19T10:01:47.194Z",
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
        "deletionTime": "2020-05-19T10:01:47.194Z",
        "lastModificationTime": "2020-05-19T10:01:47.194Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-19T10:01:47.194Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-19T10:01:47.194Z",
    "lastModificationTime": "2020-05-19T10:01:47.194Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-19T10:01:47.194Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T10:01:47.194Z",
  "lastModificationTime": "2020-05-19T10:01:47.194Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T10:01:47.194Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the document to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "documentName": "string",
    "documentLocation": "string",
    "documentTypes": 1,
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
        "deletionTime": "2020-05-19T09:57:17.650Z",
        "lastModificationTime": "2020-05-19T09:57:17.650Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-19T09:57:17.650Z",
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
          "deletionTime": "2020-05-19T09:57:17.650Z",
          "lastModificationTime": "2020-05-19T09:57:17.650Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-19T09:57:17.650Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-19T09:57:17.650Z",
      "lastModificationTime": "2020-05-19T09:57:17.650Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-19T09:57:17.650Z",
      "creatorUserId": 0,
      "id": 0
    },
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-19T09:57:17.650Z",
    "lastModificationTime": "2020-05-19T09:57:17.650Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-19T09:57:17.650Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/Documents/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"documentName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Documents/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"documentName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "documentName": "nothing",
  "documentLocation": "string",
  "documentTypes": 1,
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
      "deletionTime": "2020-05-19T09:51:26.091Z",
      "lastModificationTime": "2020-05-19T09:51:26.091Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-19T09:51:26.091Z",
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
        "deletionTime": "2020-05-19T09:51:26.091Z",
        "lastModificationTime": "2020-05-19T09:51:26.091Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-19T09:51:26.091Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-19T09:51:26.092Z",
    "lastModificationTime": "2020-05-19T09:51:26.092Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-19T09:51:26.092Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-19T09:51:26.092Z",
  "lastModificationTime": "2020-05-19T09:51:26.092Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-19T09:51:26.092Z",
  "creatorUserId": 0,
  "id": 0
}
```
# Goods Received Note

The GRN will act as internal proof of goods received to process and match against the supplier invoices or purchase orders. The goods receipt note is an internal document produced after inspecting delivery for proof of order receipt. It has the following field parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
goodsReceivedNoteName | string | the name of the GRN document
purchaseOrderId | int | the identification of the purchase order
grnDate | datestring | the date of issuance of the GRN
vendorDONumber | string | the vendor do number
warehouseId | int | the id of the warehouse
isFullReceive | bool | a flag showing whether goods are fully received or not
isDeleted | boolean | checks whether a GRN document is deleted or not
deleterUserId | int | the id of the user who deletes the GRN
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the GRN doc was created
creatorUserId | int | the id of the user who created that document
id | int | the id of the GRN

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "goodsReceivedNoteName": " ", "purchaseOrderId": " ", "grnDate": " ", "vendorDoNumber": " ", "vendorInvoiceNumber": " ", "warehouseId": " ", "isFullReceive": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"goodsReceivedNoteName\": \" \",\n    \"purchaseOrderId\": \" \",\n    \"grnDate\": \" \",\n    \"vendorDoNumber\": \" \",\n    \"vendorInvoiceNumber\": \" \",\n    \"warehouseId\": \" \",\n    \"isFullReceive\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"goodsReceivedNoteName\": \" \",\n    \"purchaseOrderId\": \" \",\n    \"grnDate\": \" \",\n    \"vendorDoNumber\": \" \",\n    \"vendorInvoiceNumber\": \" \",\n    \"warehouseId\": \" \",\n    \"isFullReceive\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "goodsReceivedNoteName": " ",
    "purchaseOrderId": 0,
    "grnDate": " ",
    "vendorDoNumber": " ",
    "vendorInvoiceNumber": " ",
    "warehouseId": 0,
    "isFullReceive": true,
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
  "goodsReceivedNoteName": "string",
  "purchaseOrderId": 0,
  "grnDate": "2020-05-20T06:32:14.607Z",
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "warehouseId": 0,
  "isFullReceive": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T06:32:14.608Z",
  "lastModificationTime": "2020-05-20T06:32:14.608Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T06:32:14.608Z",
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
This endpoint creates a GRN doc.

### HTTP Request

`POST /api/services/app/GoodsReceivedNote/CreateAsync/`

## Delete

This endpoint allows you to delete particular GRN document from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/GoodsReceivedNote/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "goodsReceivedNoteName": "string",
  "purchaseOrderId": 0,
  "grnDate": "2020-05-20T07:36:05.933Z",
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "warehouseId": 0,
  "isFullReceive": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T07:36:05.933Z",
  "lastModificationTime": "2020-05-20T07:36:05.933Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T07:36:05.933Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the document to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "goodsReceivedNoteName": "string",
    "purchaseOrderId": 0,
    "grnDate": "2020-05-20T07:38:02.601Z",
    "vendorDONumber": "string",
    "vendorInvoiceNumber": "string",
    "warehouseId": 0,
    "isFullReceive": true,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T07:38:02.601Z",
    "lastModificationTime": "2020-05-20T07:38:02.601Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T07:38:02.601Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the GRN docs.

### HTTP Request

`POST /api/services/app/GoodsReceivedNote/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"customerId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/GoodsReceivedNote/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"0\",\n    \"goodsReceivedNoteName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "goodsReceivedNoteName": "nothing",
  "purchaseOrderId": 0,
  "grnDate": "2020-05-20T07:39:38.416Z",
  "vendorDONumber": "string",
  "vendorInvoiceNumber": "string",
  "warehouseId": 0,
  "isFullReceive": true,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T07:39:38.416Z",
  "lastModificationTime": "2020-05-20T07:39:38.416Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T07:39:38.416Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Installments

Whenever a customer decides to pay in installments, the transaction records will be found in this section. Among the information includes the following parameters

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
customerId | int | the id of the customer paying in installments
ammount | int | the ammount being paid in installments
currentLoanAmmount | int | the ammount currently being owed by a customer
customer | string | the details of the customer paying in installments
email2 | string | the second email of the customer
ownership | string | the owner for the customer
taxId | string | the tax identification of the customer
VatNo | string | the VAT number of the customer 
gendor | string | the sex for the customer
isDeleted | boolean | checks whether an installment is deleted or not
deleterUserId | int | the id of the user who deletes a installment for one reason or another
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the installment was created
creatorUserId | int | the id of the user who created that installment
id | int | the id of the particular installment

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "customerId": " ", "amount": " ", "currentLoanAmount": " ", "customer": " ", "parent_customerId_Id": " ", "email2": " ", "ownership": " ", "taxId": " ", "accounts": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"customerId\": \" \",\n    \"amount\": \" \",\n    \"currentLoanAmount\": \" \",\n    \"customer\": \" \",\n    \"parent_customerId_Id\": \" \",\n    \"email2\": \" \",\n    \"ownership\": \" \",\n    \"taxId\": \" \",\n    \"accounts\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"customerId\": \" \",\n    \"amount\": \" \",\n    \"currentLoanAmount\": \" \",\n    \"customer\": \" \",\n    \"parent_customerId_Id\": \" \",\n    \"email2\": \" \",\n    \"ownership\": \" \",\n    \"taxId\": \" \",\n    \"accounts\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "customerId": 0,
    "amount": 0,
    "currentLoanAmount": 0,
    "customer": " ",
    "parent_customerId_Id": 0,
    "email2": 1,
    "ownership": 1,
    "taxId": 0,
    "accounts": "string",
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
  "amount": 0,
  "currentLoanAmount": 0,
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
      "deletionTime": "2020-05-20T07:43:36.668Z",
      "lastModificationTime": "2020-05-20T07:43:36.668Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T07:43:36.668Z",
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
        "deletionTime": "2020-05-20T07:43:36.668Z",
        "lastModificationTime": "2020-05-20T07:43:36.668Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T07:43:36.668Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T07:43:36.669Z",
    "lastModificationTime": "2020-05-20T07:43:36.669Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T07:43:36.669Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T07:43:36.669Z",
  "lastModificationTime": "2020-05-20T07:43:36.669Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T07:43:36.669Z",
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
This endpoint creates an installment.

### HTTP Request

`POST /api/services/app/Installments/CreateAsync/`

## Delete

This endpoint allows you to delete particular record of the installments from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/Installments/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "customerId": 0,
  "amount": 0,
  "currentLoanAmount": 0,
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
      "deletionTime": "2020-05-20T08:38:07.323Z",
      "lastModificationTime": "2020-05-20T08:38:07.323Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T08:38:07.323Z",
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
        "deletionTime": "2020-05-20T08:38:07.323Z",
        "lastModificationTime": "2020-05-20T08:38:07.323Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T08:38:07.323Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T08:38:07.323Z",
    "lastModificationTime": "2020-05-20T08:38:07.323Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T08:38:07.323Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T08:38:07.323Z",
  "lastModificationTime": "2020-05-20T08:38:07.323Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T08:38:07.323Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the installment to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "customerId": 0,
    "amount": 0,
    "currentLoanAmount": 0,
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
        "deletionTime": "2020-05-20T08:39:31.330Z",
        "lastModificationTime": "2020-05-20T08:39:31.330Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T08:39:31.330Z",
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
          "deletionTime": "2020-05-20T08:39:31.330Z",
          "lastModificationTime": "2020-05-20T08:39:31.330Z",
          "lastModifierUserId": 0,
          "creationTime": "2020-05-20T08:39:31.330Z",
          "creatorUserId": 0,
          "id": 0
        }
      ],
      "isDeleted": true,
      "deleterUserId": 0,
      "deletionTime": "2020-05-20T08:39:31.330Z",
      "lastModificationTime": "2020-05-20T08:39:31.330Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T08:39:31.330Z",
      "creatorUserId": 0,
      "id": 0
    },
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T08:39:31.330Z",
    "lastModificationTime": "2020-05-20T08:39:31.330Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T08:39:31.330Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/Installments/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"customerId\": \"5\",\n    \"currentLoanAmount\": \"500\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Installments/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"customerId\": \"5\",\n    \"currentLoanAmount\": \"500\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "customerId": 5,
  "amount": 0,
  "currentLoanAmount": 500,
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
      "deletionTime": "2020-05-20T08:42:23.772Z",
      "lastModificationTime": "2020-05-20T08:42:23.772Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-05-20T08:42:23.772Z",
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
        "deletionTime": "2020-05-20T08:42:23.772Z",
        "lastModificationTime": "2020-05-20T08:42:23.772Z",
        "lastModifierUserId": 0,
        "creationTime": "2020-05-20T08:42:23.772Z",
        "creatorUserId": 0,
        "id": 0
      }
    ],
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T08:42:23.772Z",
    "lastModificationTime": "2020-05-20T08:42:23.772Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T08:42:23.772Z",
    "creatorUserId": 0,
    "id": 0
  },
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T08:42:23.772Z",
  "lastModificationTime": "2020-05-20T08:42:23.772Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T08:42:23.772Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Installment Type

This section is where the details regarding the type of installments are found with the following parameters.

### Fields

Arguments | Type | Description
-------- | ------ | --------
name | string | name of the installment type
no_of_days | int | the number of days until the next payment
no_of_months | int | the number of months
isDeleted | boolean | checks whether this record is deleted or not
deleterUserId | int | the id of the user who deletes an installment
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the installment type was created
creatorUserId | int | the id of the user who created the installment type
id | int | the id of the installment type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"name": " ", "no_Of_Days": " ", "no_Of_Months": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"name\": \" \",\n    \"no_Of_Days\": \" \",\n    \"no_Of_Months\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"name\": \" \",\n    \"no_Of_Days\": \" \",\n    \"no_Of_Months\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "name": " ",
    "no_of_Days": ,
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
  "name": "string",
  "no_Of_Days": 0,
  "no_Of_Months": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T09:51:13.736Z",
  "lastModificationTime": "2020-05-20T09:51:13.736Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T09:51:13.736Z",
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
This endpoint creates an installment type.

### HTTP Request

`POST /api/services/app/InstallmentTypes/CreateAsync/`

## Delete

This endpoint allows you to delete particular type of installment from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`/api/services/app/InstallmentTypes/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "name": "string",
  "no_Of_Days": 0,
  "no_Of_Months": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T10:10:36.263Z",
  "lastModificationTime": "2020-05-20T10:10:36.263Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T10:10:36.263Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the installment type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "name": "string",
    "no_Of_Days": 0,
    "no_Of_Months": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-20T10:13:58.726Z",
    "lastModificationTime": "2020-05-20T10:13:58.726Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-20T10:13:58.726Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the installment types.

### HTTP Request

`POST /api/services/app/InstallmentTypes/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/InstallmentTypes/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"name\": \"not\",\n    \"no_Of_Days\": \"5\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"name\": \"not\",\n    \"no_Of_Days\": \"5\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "name": "not",
  "no_Of_Days": 5,
  "no_Of_Months": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-20T10:15:34.543Z",
  "lastModificationTime": "2020-05-20T10:15:34.543Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-20T10:15:34.543Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Users
Users API gives you access to get basic information about other users involved in the supply chain process.

<aside class="info">This endpoint protects the privacy of users. It is <strong>NOT</strong> possible to extract personal details of all the users from this endpoint. An admin however can extract the personal details using the Admin APIs.</aside>

### Field

User attributes: 

Parameter | Type | Description
----- | ----- | --------
userName | string | UserName of the user
name | string | full name of the user
surname | string | the Surname of the user
EmailAddress | string | Email of the user
isActive | boolean | shows if user is active or not
roleNames | string | shows the role a user plays
password | string | Password of the user entered while registering

## Create a user

>To create a user, use the code below:

This field will require you to enter the attributes listed in the table above. 

```csharp
var client = new RestClient("https://nmicrosscmweb.azurewebsites.net/api/services/app/User/Create");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddParameter("application/json-patch+json", "{\n    \"username\": \" \",\n    \"name\": \" \",\n    \"surname\": \" \",\n    \"emailAddress\": \" \",\n    \"isActive\": \" \",\n    \"roleNames\": \" \",\n    \"password\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```shell
curl --request POST \
  --url https://nmicrosscmweb.azurewebsites.net/api/services/app/User/Create/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"username": " ", "name": " ", "surname": " ", "emailAddress": " ", "isActive": " ", "roleNames": " ", "password": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmweb.azurewebsites.net/api/services/app/User/Create/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"userName\": \" \",\n    \"name\": \" \",\n    \"surname\": \" \",\n    \"emailAddress\": \" \",\n    \"isActive\": \" \",\n    \"roleNames\": \" \",\n    \"password\": \" \"}"

response = http.request(request)
puts response.read_body
```

```javascript
var http = require("http");

var options = {
  "method": "POST",
  "hostname": "nmicrosscmweb.azurewebsites.net",
  "port": null,
  "path": "/api/services/app/User/Create/",
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

req.write(JSON.stringify({ username: ' ',
  name: ' ',
  surname: ' ',
  emailAddress: ' ',
  roleNames: ' ',
  password: ' ' }));
req.end();
```
> The above command returns JSON structured like this:

```json
{
  "userName": "string",
  "name": "string",
  "surname": "string",
  "emailAddress": "string",
  "isActive": true,
  "roleNames": [
    "string"
  ],
  "password": "string"
}

```

This endpoint creates a user.

### HTTP Request

`POST /api/services/app/User/Create/`

<aside class="info">Doing this, you will have successfully created a user unless otherwise. However, since in our case we are not inputting any parameters, definitely no user will be created.</aside>

## Update user details

This field allows you to make changes to the user parameters

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/User/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"userName\": \"nothing\",\n    \"name\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/User/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"userName\": \"nothing\",\n    \"name\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "userName": "nothing",
  "name": "nothing",
  "surname": "string",
  "emailAddress": "string",
  "isActive": true,
  "fullName": "string",
  "lastLoginTime": "2020-05-25T07:56:22.007Z",
  "creationTime": "2020-05-25T07:56:22.007Z",
  "roleNames": [
    "string"
  ],
  "id": 0
}
```

### HTTP Request

`PUT /api/services/app/User/Update`

### URL Parameters

These are the same parameters for creating a user

## Delete a User

To delete a user, click on the link below

`DELETE /api/services/app/User/Delete`

## Get User Roles

As we have seen, each user has a role and to get a user role, we can either click this HTTP request or 
use the shell code

### HTTP Request

`GET /api/services/app/User/GetRoles`

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/User/GetRoles 
   \
  --header 'cache-control: no-cache'
```

> The above code returns JSON structured like this:

```json
{
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
## Change Language

To change the language, use the http request below

`POST /api/services/app/User/ChangeLanguage`

## Change Password

You can change your user password by simply using the following HTTP Request

`POST /api/services/app/User/ChangePassword`

## ResetPassword

It's recommended to change your password periodically for security purposes. You can use the following request

`POST /api/services/app/User/ResetPassword`

## Get a User

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/User/Get");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/User/Get \
  --header 'cache-control: no-cache'
```

> The above code returns a JSON structured like this:

```json
{
  "userName": "string",
  "name": "string",
  "surname": "string",
  "emailAddress": "string",
  "isActive": true,
  "fullName": "string",
  "lastLoginTime": "2020-05-05T18:18:13.185Z",
  "creationTime": "2020-05-05T18:18:13.185Z",
  "roleNames": [
    "string"
  ],
  "id": 0
}
```

This endpoint retrieves details of a single user.

## Get All Users

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/User/GetAll")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/User/GetAll/ \  
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/User/GetAll/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "totalCount": 0,
  "items": [
    {
      "userName": "string",
      "name": "string",
      "surname": "string",
      "emailAddress": "string",
      "isActive": true,
      "fullName": "string",
      "lastLoginTime": "2020-05-05T18:27:03.720Z",
      "creationTime": "2020-05-05T18:27:03.720Z",
      "roleNames": [
        "string"
      ],
      "id": 0
    }
  ]
}
```

In this section, we retrieve a list of all users in the database

# User Profile

This section contains information regarding the user profiles.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
firstName | string | the first name of the user in the profile
lastName | string | the last name of the user
email | string | the email of the user
password | string | the password of the user
confirmPassword | string | a user enters the same password in this section for confirmation
oldPassword | string | the old password of the user
profilePicture | string | the profile picture of the user
applicationUserId | int | the id of the application user 
isDeleted | boolean | checks whether a profile is deleted or not
deleterUserId | int | the id of the user who deletes a user profile
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the profile was created
creatorUserId | int | the id of the user who created that profile
id | int | the id of the profile

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "firstName": " ", "lastName": " ", "email": " ", "password": " ", "confirmPassword": " ", "oldPassword": " ", "profilePicture": " ", "applicationUserId": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"firstName\": \" \",\n    \"lastName\": \" \",\n    \"email\": \" \",\n    \"password\": \" \",\n    \"confirmPassword\": \" \",\n    \"oldPassword\": \" \",\n    \"profilePicture\": \" \",\n    \"applicationUserId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"firstName\": \" \",\n    \"lastName\": \" \",\n    \"email\": \" \",\n    \"password\": \" \",\n    \"confirmPassword\": \" \",\n    \"oldPassword\": \" \",\n    \"profilePicture\": \" \",\n    \"applicationUserId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "firstName": " ",
    "lastName": " ",
    "email": " ",
    "password": " ",
    "confirmPassword": " ",
    "oldPassword": " ",
    "profilePicture": " ",
    "applicationUserId": 0,
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
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "password": "string",
  "confirmPassword": "string",
  "oldPassword": "string",
  "profilePicture": "string",
  "applicationUserId": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T12:14:03.030Z",
  "lastModificationTime": "2020-05-25T12:14:03.030Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T12:14:03.030Z",
  "creatorUserId": 0,
  "id": 0
}
```

This endpoint creates a case.

### HTTP Request

`POST /api/services/app/UserProfile/CreateAsync/`

## Delete

This endpoint allows you to delete particular user profile from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/UserProfile/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "password": "string",
  "confirmPassword": "string",
  "oldPassword": "string",
  "profilePicture": "string",
  "applicationUserId": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T12:16:41.004Z",
  "lastModificationTime": "2020-05-25T12:16:41.004Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T12:16:41.004Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the user profile to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "firstName": "string",
    "lastName": "string",
    "email": "string",
    "password": "string",
    "confirmPassword": "string",
    "oldPassword": "string",
    "profilePicture": "string",
    "applicationUserId": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T12:16:41.010Z",
    "lastModificationTime": "2020-05-25T12:16:41.010Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T12:16:41.010Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the Cases.

### HTTP Request

`POST /api/services/app/UserProfile/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"email\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/UserProfile/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"tenantId\": \"5\",\n    \"email\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 5,
  "firstName": "string",
  "lastName": "string",
  "email": "nothing",
  "password": "string",
  "confirmPassword": "string",
  "oldPassword": "string",
  "profilePicture": "string",
  "applicationUserId": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T12:16:41.093Z",
  "lastModificationTime": "2020-05-25T12:16:41.093Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T12:16:41.093Z",
  "creatorUserId": 0,
  "id": 0
}
```

# vendor

A vendor in this case is an enterprise that contributes goods and services.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
vendorId | int | the id of the vendor
vendorName | string | the name of the vendor
vendorTypeId | int | the id of the vendor type
address | string | the vendor's address
city | string | the city where the vendor operates from
state | string | the state of the vendor
zipCode | string | the zip code of the vendor
phone | string | the phone number of the vendor
email | string | the email address of the vendor
contactPerson | string | the person to contact in case of an issue
isDeleted | boolean | checks whether a vendor is deleted or not
deleterUserId | int | the id of the user who deletes a vendor
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the vendor was created
creatorUserId | int | the id of the user who created that vendor
id | int | the id of the vendor

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "vendorId": " ", "vendorName": " ", "vendorTypeId": " ", "address": " ", "city": " ", "state": " ", "zipCode": " ", "phone": " ", "email": " ", "contactPerson": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"vendorId\": \" \",\n    \"vendorName\": \" \",\n    \"vendorTypeId\": \" \",\n    \"address\": \" \",\n    \"city\": \" \",\n    \"state\": \" \",\n    \"zipCode\": \" \",\n    \"phone\": \" \",\n    \"email\": \" \",\n \"contactPerson\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"vendorId\": \" \",\n    \"vendorName\": \" \",\n    \"vendorTypeId\": \" \",\n    \"address\": \" \",\n    \"city\": \" \",\n    \"state\": \" \",\n    \"zipCode\": \" \",\n    \"phone\": \" \",\n    \"email\": \" \",\n \"contactPerson\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "vendorId": 0,
    "vendorName": " ",
    "vendorTypeId": 0,
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
  "deletionTime": "2020-05-25T13:02:15.636Z",
  "lastModificationTime": "2020-05-25T13:02:15.636Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T13:02:15.636Z",
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
This endpoint creates a vendor.

### HTTP Request

`POST /api/services/app/Vendor/CreateAsync/`

## Delete

This endpoint allows you to delete particular vendor from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/Vendor/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
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
  "deletionTime": "2020-05-25T13:02:40.984Z",
  "lastModificationTime": "2020-05-25T13:02:40.984Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T13:02:40.984Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the vendor to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
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
    "deletionTime": "2020-05-25T13:02:40.990Z",
    "lastModificationTime": "2020-05-25T13:02:40.990Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T13:02:40.990Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the vendors.

### HTTP Request

`POST /api/services/app/Vendor/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"vendorId\": \"5\",\n    \"vendorName\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Vendor/Update/");
var request = new RestRequest(Method.PUT);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"vendorId\": \"5\",\n    \"vendorName\": \"nothing\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

> The above command returns JSON structured like this:

```json
{
  "tenantId": 0,
  "vendorId": 5,
  "vendorName": "nothing",
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
  "deletionTime": "2020-05-25T13:02:41.064Z",
  "lastModificationTime": "2020-05-25T13:02:41.064Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T13:02:41.064Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Vendor Type

This section is where you can find details regarding the type of vendor. It is where we categorize vendors by definition.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
vendorTypeName | string | the name of the vendor type
description | string | details regarding the vendor type
isDeleted | boolean | checks whether a case is deleted or not
deleterUserId | int | the id of the user who deletes a vendor type
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the vendor type was created
creatorUserId | int | the id of the user who created that vendor type
id | int | the id of the vendor type

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "vendorTypeName": " ", "description": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"vendorTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"vendorTypeName\": \" \",\n    \"description\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "vendorTypeName": " ",
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
  "vendorTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:29:22.136Z",
  "lastModificationTime": "2020-05-25T17:29:22.136Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:29:22.136Z",
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
This endpoint creates a vendor type.

### HTTP Request

`POST /api/services/app/VendorType/CreateAsync/`

## Delete

This endpoint allows you to delete particular type of vendor from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/VendorType/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "vendorTypeName": "string",
  "description": "string",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:30:04.986Z",
  "lastModificationTime": "2020-05-25T17:30:04.986Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:30:04.986Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the vendor type to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "vendorTypeName": "string",
    "description": "string",
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T17:30:04.991Z",
    "lastModificationTime": "2020-05-25T17:30:04.991Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T17:30:04.991Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the vendor types.

### HTTP Request

`POST /api/services/app/VendorType/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/VendorType/Update/");
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
  "vendorTypeName": "string",
  "description": "nothing",
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:29:40.239Z",
  "lastModificationTime": "2020-05-25T17:29:40.239Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:29:40.239Z",
  "creatorUserId": 0,
  "id": 0
}
```

# Warehouse

This section contains details about the warehouses involved during the transaction.

### Field

Parameter | Type | Description
--------- | ------- | --------
tenantId | int | the id of the tenant
warehouseName | string | the name of the warehouse
description | string | details regarding the warehouse
branchId | int | the id of the branch
isDeleted | boolean | checks whether a warehouse is deleted or not
deleterUserId | int | the id of the user who deletes a warehouse
deletionTime | datestring | the time of deletion
lastModificationTime | datestring | the time when it was last modified
lastModifierUserId | int | the id of the user who modified last
creationTime | datestring | the time when the warehouse was created
creatorUserId | int | the id of the user who created that warehouse
id | int | the id of the warehouse

## Create

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/CreateAsync/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"tenantId": " ", "warehouseName": " ", "description": " ", "branchId": " ", "isDeleted": " ", "deleterUserId": " ", "deletionTime": " ",  "lastModificationTime": " ", "lastModifierUserId": " ", "creationTime": " ", "creatorUserId": " ", "id": " "}'
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"warehouseName\": \" \",\n    \"description\": \" \",\n    \"branchId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json", "{\n    \"tenantId\": \" \",\n    \"warehouseName\": \" \",\n    \"description\": \" \",\n    \"branchId\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/CreateAsync/');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'cache-control' => 'no-cache',
  'content-type' => 'application/json-patch+json'
));

$request->setBody('{
    "tenantId": 0,
    "warehouseName": " ",
    "description": " ",
    "branchId": 0,
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
  "warehouseName": "string",
  "description": "string",
  "branchId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:29:46.294Z",
  "lastModificationTime": "2020-05-25T17:29:46.294Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:29:46.294Z",
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
This endpoint creates a warehouse.

### HTTP Request

`POST /api/services/app/Warehouse/CreateAsync/`

## Delete

This endpoint allows you to delete particular warehouse record from the DB. Please be aware this will delete all the data related to it. The operation is ir reversible

### HTTP Request

`DELETE /api/services/app/Warehouse/Delete`

## Get By Id

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/GetById/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Get.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request GET \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/GetById/ \
  --header 'cache-control: no-cache'
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/GetById/");
var request = new RestRequest(Method.GET);
request.AddHeader("cache-control", "no-cache");
IRestResponse response = client.Execute(request);
```

> The above command returns JSON Response structured like this:

```json
{
  "tenantId": 0,
  "warehouseName": "string",
  "description": "string",
  "branchId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:30:05.011Z",
  "lastModificationTime": "2020-05-25T17:30:05.011Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:30:05.011Z",
  "creatorUserId": 0,
  "id": 0
}
```

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the warehouse to retrieve

## List All

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/ListAll/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["cache-control"] = 'no-cache'

response = http.request(request)
puts response.read_body
```

```shell
curl --request POST \
  --url https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/ListAll/ \
  --header 'cache-control: no-cache'
```

> The above command returns JSON Response structured like this:

```json
[
  {
    "tenantId": 0,
    "warehouseName": "string",
    "description": "string",
    "branchId": 0,
    "isDeleted": true,
    "deleterUserId": 0,
    "deletionTime": "2020-05-25T17:30:05.016Z",
    "lastModificationTime": "2020-05-25T17:30:05.016Z",
    "lastModifierUserId": 0,
    "creationTime": "2020-05-25T17:30:05.016Z",
    "creatorUserId": 0,
    "id": 0
  }
]
```

This endpoint will list all the warehouses.

### HTTP Request

`POST /api/services/app/Warehouse/ListAll/`

## Update

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/Update/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Put.new(url)
request["content-type"] = 'application/json-patch+json'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \"5\",\n    \"description\": \"nothing\"\n}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Warehouse/Update/");
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
  "warehouseName": "string",
  "description": "nothing",
  "branchId": 0,
  "isDeleted": true,
  "deleterUserId": 0,
  "deletionTime": "2020-05-25T17:30:05.077Z",
  "lastModificationTime": "2020-05-25T17:30:05.077Z",
  "lastModifierUserId": 0,
  "creationTime": "2020-05-25T17:30:05.077Z",
  "creatorUserId": 0,
  "id": 0
}
```
