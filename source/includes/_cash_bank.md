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
curl -X POST "https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync" -H "accept: application/json" -H "Content-Type: application/json-patch+json" -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4" -d "{ \"tenantId\": 0, \"cashBankName\": \"string\", \"description\": \"string\", \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-02T08:29:21.919Z\", \"lastModificationTime\": \"2020-06-02T08:29:21.919Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-02T08:29:21.919Z\", \"creatorUserId\": 0, \"id\": 0}"
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["authorization"] = 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"cashBankName\": \" \",\n    \"description\": \" \", \n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/CashBank/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4");
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
  'authorization' => 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4',
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
  "result": {
    "success": true,
    "message": "Insert success.",
    "data": {
      "tenantId": 1,
      "cashBankName": "string",
      "description": "string",
      "isDeleted": false,
      "deleterUserId": null,
      "deletionTime": null,
      "lastModificationTime": "2020-06-02T08:29:21.919Z",
      "lastModifierUserId": 0,
      "creationTime": "2020-06-02T08:30:46.4045252+00:00",
      "creatorUserId": 1,
      "id": 11
    }
  },
  "targetUrl": null,
  "success": true,
  "error": null,
  "unAuthorizedRequest": false,
  "__abp": true
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
curl -X POST "https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/CreateAsync" -H "accept: application/json" -H "Content-Type: application/json-patch+json" -H "Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4" -d "{ \"tenantId\": 0, \"comment\": \"string\", \"isRead\": true, \"isDeleted\": true, \"deleterUserId\": 0, \"deletionTime\": \"2020-06-02T08:36:17.499Z\", \"lastModificationTime\": \"2020-06-02T08:36:17.499Z\", \"lastModifierUserId\": 0, \"creationTime\": \"2020-06-02T08:36:17.499Z\", \"creatorUserId\": 0, \"id\": 0}"
```

```ruby
require 'uri'
require 'net/http'

url = URI("https://nmicrosscmapi.azurewebsites.net/api/services/app/Comments/CreateAsync/")

http = Net::HTTP.new(url.host, url.port)

request = Net::HTTP::Post.new(url)
request["content-type"] = 'application/json-patch+json'
request["authorization"] = 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4'
request["cache-control"] = 'no-cache'
request.body = "{\n    \"tenantId\": \" \",\n    \"comment\": \" \",\n    \"isRead\": \" \",\n \"isDeleted\": \" \",\n \"deleterUserId\": \" \",\n    \"deletionTime\": \" \",\n    \"lastModificationTime\": \" \",\n \"lastModifierUserId\": \" \",\n \"creationTime\": \" \",\n \"creatorUserId\": \" \",\n \"id\": \" \"}"

response = http.request(request)
puts response.read_body
```

```csharp
var client = new RestClient("https://nmicrosscmapi.azurewebsites.net/api/services/app/Case/CreateAsync/");
var request = new RestRequest(Method.POST);
request.AddHeader("cache-control", "no-cache");
request.AddHeader("authorization", "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4");
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
  'authorization' => 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1laWRlbnRpZmllciI6IjEiLCJodHRwOi8vc2NoZW1hcy54bWxzb2FwLm9yZy93cy8yMDA1LzA1L2lkZW50aXR5L2NsYWltcy9uYW1lIjoiYWRtaW4iLCJBc3BOZXQuSWRlbnRpdHkuU2VjdXJpdHlTdGFtcCI6ImY0NjRhZjk2LTlhNTgtYzM0MS02YTYzLTM5ZjIxMWY0YzcxMyIsImh0dHA6Ly9zY2hlbWFzLm1pY3Jvc29mdC5jb20vd3MvMjAwOC8wNi9pZGVudGl0eS9jbGFpbXMvcm9sZSI6IkFkbWluIiwic3ViIjoiMSIsImp0aSI6IjEzM2M4OWUwLWZhMTUtNGU2Ni1iYzM5LWM3MGQ0YjA1MWU5YSIsImlhdCI6MTU5MTA4MDY3NSwibmJmIjoxNTkxMDgwNjc1LCJleHAiOjE1OTExNjcwNzUsImlzcyI6IlNDTSIsImF1ZCI6IlNDTSJ9.HJ1NdDtscJUn9W8xrVGUWey26KEI-9uFo_NqI1R9hF4',
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

> Response body: 

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
