# payments

Payment operations

## GET /banks/{bankId}/payments

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/payments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/payments HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/payments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/payments");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/payments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/payments`

*List payments*

Returns all payments for the user

### Parameters

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|

> Example responses

> 200 Response

```json
{
  "payments": [
    {
      "id": "string",
      "status": "string",
      "creditorAccount": {
        "type": "string",
        "account": "string",
        "message": "string"
      },
      "debtorAccount": {
        "type": "string",
        "account": "string",
        "message": "string"
      },
      "amount": {
        "value": 0,
        "currency": "string"
      }
    }
  ]
}
```

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Need to authenticate with the bank|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

### Response Schema

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» payments|[[Payment](#schemapayment)]|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: payment:read )
</aside>

## POST /banks/{bankId}/payments

> Code samples

```shell
# You can also use wget
curl -X POST https://api.northbricks.io/api/v1/banks/{bankId}/payments \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.northbricks.io/api/v1/banks/{bankId}/payments HTTP/1.1
Host: api.northbricks.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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
  "creditorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "debtorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "amount": {
    "value": 0,
    "currency": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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

result = RestClient.post 'https://api.northbricks.io/api/v1/banks/{bankId}/payments',
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

r = requests.post('https://api.northbricks.io/api/v1/banks/{bankId}/payments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/payments");
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
    req, err := http.NewRequest("POST", "https://api.northbricks.io/api/v1/banks/{bankId}/payments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /banks/{bankId}/payments`

*Initiate payment*

Initiates a payment

> Body parameter

```json
{
  "creditorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "debtorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "amount": {
    "value": 0,
    "currency": "string"
  }
}
```

### Parameters

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|
|body|body|object|false|Bank to make the payment from|
|» creditorAccount|body|object|false|none|
|»» type|body|string|false|none|
|»» account|body|string|false|none|
|»» message|body|string|false|none|
|» debtorAccount|body|object|false|none|
|»» type|body|string|false|none|
|»» account|body|string|false|none|
|»» message|body|string|false|none|
|» amount|body|object|false|none|
|»» value|body|number(double)|false|none|
|»» currency|body|string|false|none|

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Payment initialized|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Need to authenticate with the bank|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|201|Location|string||Location of the initialized payment|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: payment:write )
</aside>

## GET /banks/{bankId}/payments/{paymentId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/payments/{paymentId}`

*Returns a payment*

Returns all information about a payment

### Parameters

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|
|paymentId|path|string|true|ID of payment|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "status": "string",
  "creditorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "debtorAccount": {
    "type": "string",
    "account": "string",
    "message": "string"
  },
  "amount": {
    "value": 0,
    "currency": "string"
  }
}
```

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Payment](#schemapayment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Need to authenticate with the bank|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Payment not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: payment:read )
</aside>

## PUT /banks/{bankId}/payments/{paymentId}

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId} \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId} HTTP/1.1
Host: api.northbricks.io

```

```javascript
var headers = {
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
  method: 'put',

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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
{
  method: 'PUT',

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

result = RestClient.put 'https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
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
    req, err := http.NewRequest("PUT", "https://api.northbricks.io/api/v1/banks/{bankId}/payments/{paymentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /banks/{bankId}/payments/{paymentId}`

*Confirm payment*

Confirm a previously initialized payment

### Parameters

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|
|paymentId|path|string|true|ID of payment|

### Responses

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|None|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Need to authenticate with the bank|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Payment not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: payment:write )
</aside>



