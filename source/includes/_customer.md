
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

```shell

```

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

## Create 

## ## Delete

## Get By Id

## List All

## Update