<h1 id="Northbricks-Bank-API-Banks">Banks</h1>

Bank operations

## Get all banks

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks`

Returns available banks

> Example responses

> 200 Response

```json
{
  "banks": [
    {
      "id": "string",
      "shortName": "string",
      "fullName": "string",
      "logo": "string",
      "website": "string"
    }
  ]
}
```

<h3 id="get-all-banks-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Available banks|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<h3 id="get-all-banks-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» banks|[[Bank](#schemabank)]|false|none|none|
|»» id|string|false|none|none|
|»» shortName|string|false|none|none|
|»» fullName|string|false|none|none|
|»» logo|string|false|none|none|
|»» website|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>

## Get bank

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}`

Returns bank

<h3 id="get-bank-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|Id of the bank to get.|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "shortName": "string",
  "fullName": "string",
  "logo": "string",
  "website": "string"
}
```

<h3 id="get-bank-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Bank|[Bank](#schemabank)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid bankId|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>

## Get all banks for current user

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/me/banks HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/me/banks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /me/banks`

Returns current user banks

> Example responses

> 200 Response

```json
{
  "banks": [
    {
      "id": "string",
      "shortName": "string",
      "fullName": "string",
      "logo": "string",
      "website": "string"
    }
  ]
}
```

<h3 id="get-all-banks-for-currentuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Current user banks|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<h3 id="get-all-banks-for-currentuser-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» banks|[[Bank](#schemabank)]|false|none|none|
|»» id|string|false|none|none|
|»» shortName|string|false|none|none|
|»» fullName|string|false|none|none|
|»» logo|string|false|none|none|
|»» website|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>

## Add bank to current user

> Code samples

```shell
# You can also use wget
curl -X POST https://api.northbricks.io/api/v1/me/banks \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.northbricks.io/api/v1/me/banks HTTP/1.1
Host: api.northbricks.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');
const inputBody = '{
  "bankId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/me/banks',
{
  method: 'POST',
  body: inputBody,
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
  'Content-Type' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.northbricks.io/api/v1/me/banks',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.northbricks.io/api/v1/me/banks', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks");
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.northbricks.io/api/v1/me/banks", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /me/banks`

Adds the bank to current user

> Body parameter

```json
{
  "bankId": "string"
}
```

<h3 id="add-bank-to-current-user-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Bank to add.|
|» bankId|body|string|false|none|

<h3 id="add-bank-to-current-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Bank added to user|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|
|409|[Conflict](https://tools.ietf.org/html/rfc7231#section-6.5.8)|Current user already has the bank|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Location|string||Location of the added bank|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>

## Get current user bank

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks/{bankId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/me/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/me/banks/{bankId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /me/banks/{bankId}`

Returns current user bank

<h3 id="get-current-user-bank-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|Id of the bank to get.|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "shortName": "string",
  "fullName": "string",
  "logo": "string",
  "website": "string"
}
```

<h3 id="get-current-user-bank-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Current user bank|[Bank](#schemabank)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid bankId|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>

## Remove bank from current user

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.northbricks.io/api/v1/me/banks/{bankId} \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://api.northbricks.io/api/v1/me/banks/{bankId} HTTP/1.1
Host: api.northbricks.io

```

```javascript
var headers = {
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const request = require('node-fetch');

const headers = {
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/me/banks/{bankId}',
{
  method: 'DELETE',

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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://api.northbricks.io/api/v1/me/banks/{bankId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://api.northbricks.io/api/v1/me/banks/{bankId}', params={

}, headers = headers)

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

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.northbricks.io/api/v1/me/banks/{bankId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /me/banks/{bankId}`

Removes the bank from current user

<h3 id="remove-bank-from-current-user-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|Id of the bank to delete.|

<h3 id="remove-bank-from-current-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|Bank removed from user|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid bankId|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>
