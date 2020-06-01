# Users
Users API gives you access to get basic information about other users involved in the supply chain process.

<aside class="info">This endpoint protects the privacy of users. It is <strong>NOT</strong> possible to extract personal details of all the users from this endpoint. An admin however can extract the personal details using the Admin APIs.</aside>

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
IRestResponse response = client.Execute(request);
```
Doing this, you will have successfully created a user unless otherwise.

## Update user details

This field allows you to make changes to the user parameters

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

## Create

## Delete

## Get By Id

## List All

## Update
