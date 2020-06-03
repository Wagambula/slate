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
curl -X POST "https://nmicrosscmapi.azurewebsites.net/api/services/app/Accounts/CreateAsync" -H "accept: application/json" -H "Content-Type: application/json-patch+json" -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4" -d "{ \"customerId\": 8, \"parentAccountId\": 0, \"tenantId\": 0, \"customer\": { \"tenantId\": 0, \"customerName\": \"any\", \"customerTypeId\": 0, \"address\": \"string\", \"city\": \"string\", \"state\": \"string\", \"zipCode\": \"string\", \"phone\": \"string\", \"email\": \"string\", \"contactPerson\": \"string\", \"idNumber\": \"string\", \"idType\": \"string\", \"accountType\": \"string\", \"xcoordinate\": 0, \"ycoordinate\": 0, \"accountNumber\": 0, \"referenceNumber\": 0, \"imagelocation\": \"string\", \"website\": \"string\", \"industry\": \"string\", \"rating\": \"string\", \"phoneAlternative\": \"string\", \"countryId\": 0, \"country\": { \"tenantId\": 0, \"countryName\": \"string\", \"countryZone\": \"string\", \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-01T20:44:12.099Z\", \"lastModificationTime\": \"2020-06-01T20:44:12.099Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-01T20:44:12.099Z\", \"creatorUserId\": 0, \"id\": 0 }, \"parent_CustomerId_Id\": 0, \"email2\": \"string\", \"ownership\": \"string\", \"taxId\": \"string\", \"vatNo\": \"string\", \"gender\": \"string\", \"accounts\": [ { \"customerId\": 0, \"parentAccountId\": 0, \"tenantId\": 0, \"totalLoanAmount\": 0, \"totalAmountPaid\": 0, \"balance\": 0, \"is_Open\": true, \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-01T20:44:12.099Z\", \"lastModificationTime\": \"2020-06-01T20:44:12.099Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-01T20:44:12.099Z\", \"creatorUserId\": 0, \"id\": 0 } ], \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-01T20:44:12.099Z\", \"lastModificationTime\": \"2020-06-01T20:44:12.099Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-01T20:44:12.099Z\", \"creatorUserId\": 0, \"id\": 0 }, \"totalLoanAmount\": 0, \"totalAmountPaid\": 0, \"balance\": 0, \"is_Open\": true, \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-01T20:44:12.099Z\", \"lastModificationTime\": \"2020-06-01T20:44:12.099Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-01T20:44:12.100Z\", \"creatorUserId\": 0, \"id\": 0}"
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

```shell
curl -X POST "https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/CreateAsync" -H "accept: application/json" -H "Content-Type: application/json-patch+json" -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4" -d "{ \"tenantId\": 0, \"activityName\": \"act\", \"description\": \"nothing\", \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-02T07:28:32.809Z\", \"lastModificationTime\": \"2020-06-02T07:28:32.809Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-02T07:28:32.809Z\", \"creatorUserId\": 0, \"id\": 0}"
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Activities/CreateAsync");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4");
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
    "authorization": "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4",
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
  activityName: 'act',
  description: 'nothing',
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
  "activityName": "act",
  "description": "nothing",
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

> With the following Response body

```json
{
  "result": null,
  "targetUrl": null,
  "success": true,
  "error": null,
  "unAuthorizedRequest": false,
  "__abp": true
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
