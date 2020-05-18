---
title: SCM API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: cURL
  - ruby: Ruby
  - php: PHP
  - csharp: C#
  - javascript: NodeJS

includes:
  - accounts # includes activities
  - bill
  - branch # including case
  - cash_bank # including comments and configuration
  - country # including currency
  - customer # including customer type
  - documents
  - goodsReceivedNote
  - installments
  - invoice
  - loans
  - payments
  - product
  - purchase
  - ratings_role
  - sales
  - shipment # including sessions
  - tenant_tokenAuth # includes unit of measure
  - user
  - vendor # includes warehouse
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
## Creat Async
### HTTP Request

`POST /api/services/app/Accounts/CreateAsync`

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

## Delete Accounts

This end point gives you the opportunity to delete a customer's account from our DB. Please note that all the information related to the account in question will be removed and that the process is irreversible.
### HTTP Request

`DELETE /api/services/app/Accounts/Delete`

### URL Parameters

Parameter | Description
--------- | ------- | -----------
id | Unique Id of the account to retrieve

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