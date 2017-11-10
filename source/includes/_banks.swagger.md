---
title: Northbricks Bank API v1.0.0-SNAPSHOT
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
toc_footers: []
includes: []
search: true
highlight_theme: darkula
---

# Northbricks Bank API v1.0.0-SNAPSHOT

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.



Base URLs:

* <a href="https://api.northbricks.io/api/v1">https://api.northbricks.io/api/v1</a>







# Authentication





- oAuth2 authentication. This API uses OAuth 2 with the authorization code flow.

    - Flow: authorizationCode
    - Authorization URL = [https://api.northbricks.io/oauth/authorize](https://api.northbricks.io/oauth/authorize)
    - Token URL = [https://api.northbricks.io/oauth/token](https://api.northbricks.io/oauth/token)

|Scope|Scope Description|
|---|---|
|read|Grants read access|






# banks

Bank operations

## GET /banks

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://api.northbricks.io/api/v1/banks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.northbricks.io/api/v1/banks', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Information about banks*

Returns available banks

> Example responses

```json
[
  {
    "id": "string",
    "shortName": "string",
    "fullName": "string",
    "logo": "string",
    "website": "string"
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Available banks|Inline
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>


## GET /banks/{bankId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId} \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://api.northbricks.io/api/v1/banks/{bankId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Information about the bank*

Returns bank

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|Id of the bank to get.



> Example responses

```json
{
  "id": "string",
  "shortName": "string",
  "fullName": "string",
  "logo": "string",
  "website": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bank|[Bank](#schemabank)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>


## GET /me/banks

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/me/banks HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://api.northbricks.io/api/v1/me/banks',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.northbricks.io/api/v1/me/banks', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Information about current user banks*

Returns current user banks

> Example responses

```json
[
  {
    "id": "string",
    "shortName": "string",
    "fullName": "string",
    "logo": "string",
    "website": "string"
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Current user banks|Inline
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>


## GET /me/banks/{bankId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks/{bankId} \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/me/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://api.northbricks.io/api/v1/me/banks/{bankId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.northbricks.io/api/v1/me/banks/{bankId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks/{bankId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Get current user bank*

Returns current user bank

> Example responses

```json
[
  {
    "id": "string",
    "shortName": "string",
    "fullName": "string",
    "logo": "string",
    "website": "string"
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Current user bank|Inline
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>


## POST /me/banks/{bankId}

> Code samples

```shell
# You can also use wget
curl -X POST https://api.northbricks.io/api/v1/me/banks/{bankId} \
  -H 'Accept: application/json'

```

```http
POST https://api.northbricks.io/api/v1/me/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('https://api.northbricks.io/api/v1/me/banks/{bankId}',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.northbricks.io/api/v1/me/banks/{bankId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks/{bankId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Adds bank to current user*

Adds the bank to current user

> Example responses

```json
[
  {
    "id": "string",
    "shortName": "string",
    "fullName": "string",
    "logo": "string",
    "website": "string"
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Current user banks|Inline
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None
409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Current user already has the bank|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>


## DELETE /me/banks/{bankId}

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.northbricks.io/api/v1/me/banks/{bankId}

```

```http
DELETE https://api.northbricks.io/api/v1/me/banks/{bankId} HTTP/1.1
Host: api.northbricks.io



```

```javascript

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  method: 'delete',


  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');


fetch('https://api.northbricks.io/api/v1/me/banks/{bankId}',
{
  method: 'DELETE'


})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

```ruby
require 'rest-client'
require 'json'



result = RestClient.delete 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  params: {
  }

p JSON.parse(result)
```

```python
import requests

r = requests.delete('https://api.northbricks.io/api/v1/me/banks/{bankId}', params={

)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks/{bankId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());
```

*Removes bank from current user*

Removes the bank from current user

### Responses

Status|Meaning|Description|Schema
---|---|---|---|
204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Bank removed from user|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>





