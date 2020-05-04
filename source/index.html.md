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

# Users
Users API gives you access to get basic information about other users involved in the supply chain process.

<aside class="info">This endpoint protects the privacy of users. It is <strong>NOT</strong> possible to extract personal details of all the users from this endpoint. An admin however can extract the personal details using the Admin APIs.</aside>

The field below shows all possible parameters from user to vendor

### Fields

Name | Type | Description
-----|------|-------------
id   | int  | The user unique ID
url  | string | URL to get details of the user
username(Name) | string | Username of the user
first_name | string | First name of the user
last_name | string | Last name of the user
email | string | Email of the user
password | string | Password of the user entered while registering
birth_date | datestring | Birth date as provided by the user
gender | string | Gender as provided by the user. Can be "Male", "Female" or "Transgender"
address1 | string | Address provided by the user
address2 | string | Address provided by the user
city | string | City provided by the user
zip | string | Pincode provided by the user
state | string | State provided by the user
phone | string | Phone provided by the user

### Create User

To create a user, click add and then enter the following parameters:
* Email
* Full Name
* Name
* Surname
* User name
* Click the checkbox if user is active or not

### HTTP Request

`POST https://nmicrosscmweb.azurewebsites.net/api/services/app/User/Create`

### Role

A user can easily change roles only if they are logged in as admins.

### List all users

To view the list of all users, click on the link below

`POST https://nmicrosscmweb.azurewebsites.net/api/services/app/UnitOfMeasure/ListAll`

# Supplier APIs
This API provides access to all operations done by the supplier.



# Authentication

> To authorize, use this code:

```csharp
var client = new RestClient("https://nmicrosscmweb.azurewebsites.net/api/TokenAuth/Authenticate/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("content-type", "application/json-patch+json");
request.AddParameter("application/json-patch+json", "{\n    \"username\": \"admin\",\n    \"password\": \"password\"\n}", ParameterType.RequestBody);
IRestResponse response = client.Execute(request);
```

```shell
# With shell, you can just pass the user credentials to get the auth token
curl --request POST \
  --url https://nmicrosscmweb.azurewebsites.net/api/TokenAuth/Authenticate/ \
  --header 'cache-control: no-cache' \
  --header 'content-type: application/json-patch+json' \
  --data '{"username": "admin", "password": "password"}'
```
>The above command returns a JSON structured like this:

```json
[
  {
  "userNameOrEmailAddress": "string",
  "password": "string",
  "rememberClient": true
}
]
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://nmicrosscmweb.azurewebsites.net/api/TokenAuth/Authenticate/');
$request->setMethod(HTTP_METH_POST);


$request->setBody('-----011000010111000001101001
Content-Disposition: form-data; name="username"

password
-----011000010111000001101001
Content-Disposition: form-data; name="password"

password
-----011000010111000001101001--');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```
### HTTP Request

`POST https://nmicrosscmweb.azurewebsites.net/api/TokenAuth/Authenticate/`

Name | Type | Description
-----|------|-------------
username | string | Username of the user
password | string | Password of the user

# Vendor

This section contains the list of all customers using the SCM application

### Create a vendor

To create a vendor, click the link below

`POST https://nmicrosscmweb.azurewebsites.net/api/services/app/Vendor/CreateAsync`



