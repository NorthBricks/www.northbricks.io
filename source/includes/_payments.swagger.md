<h1 id="Northbricks-Paymentn-API-Payments">Payments</h1>

Payment operations

## Get all payments

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bic}/payments \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bic}/payments HTTP/1.1
Host: api.northbricks.io
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bic}/payments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/banks/{bic}/payments',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bic}/payments',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bic}/payments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bic}/payments");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bic}/payments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bic}/payments`

*Get all payments*

Returns all payments for the user

<h3 id="get-all-payments-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bic|path|string|true|BIC of bank|

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

<h3 id="get-all-payments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid input|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Need to authenticate with the bank|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

<h3 id="get-all-payments-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» payments|[[Payment](#schemapayment)]|false|none|none|
|»» id|string|false|none|Unique payment identifier for payment|
|»» status|string|false|none|PAYMENT_STATUS_NOT_PROVIDED, PROCESSING, PENDING_CONFIRMATION, PENDING_USER_APPROVAL, ON_HOLD, CONFIRMED, REJECTED, PAID, INSUFFICIENT_FUNDS, LIMIT_EXCEEDED, USER_APPROVAL_FAILED, USER_APPROVAL_TIMEOUT, USER_APPROVAL_CANCELLED|
|»» creditorAccount|object|false|none|Creditor of the payment|
|»»» type|string|false|none|ACCOUNT_ID, IBAN, PGNR, BGNR|
|»»» account|string|false|none|Account number|
|»»» message|string|false|none|Message for the creditor to appear on their transaction|
|»» debtorAccount|object|false|none|Debtor of the payment|
|»»» type|string|false|none|ACCOUNT_ID, IBAN, PGNR, BGNR|
|»»» account|string|false|none|Account number|
|»»» message|string|false|none|Message for the debtor to appear on their transaction|
|»» amount|object|false|none|none|
|»»» value|number(double)|false|none|Monetary amount of the payment|
|»»» currency|string|false|none|Currency code according to ISO 4217|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: payment:read )
</aside>

## Initiate payment

> Code samples

```shell
# You can also use wget
curl -X POST https://api.northbricks.io/api/v1/banks/{bic}/payments \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.northbricks.io/api/v1/banks/{bic}/payments HTTP/1.1
Host: api.northbricks.io
Content-Type: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bic}/payments',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
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

fetch('https://api.northbricks.io/api/v1/banks/{bic}/payments',
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

result = RestClient.post 'https://api.northbricks.io/api/v1/banks/{bic}/payments',
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

r = requests.post('https://api.northbricks.io/api/v1/banks/{bic}/payments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bic}/payments");
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
    req, err := http.NewRequest("POST", "https://api.northbricks.io/api/v1/banks/{bic}/payments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /banks/{bic}/payments`

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

<h3 id="initiate-payment-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bic|path|string|true|BIC of bank|
|body|body|object|false|Bank to make the payment from|
|» creditorAccount|body|object|false|Creditor of the payment|
|»» type|body|string|false|ACCOUNT_ID, IBAN, PGNR, BGNR|
|»» account|body|string|false|Account number|
|»» message|body|string|false|Message for the creditor to appear on their transaction|
|» debtorAccount|body|object|false|Debtor of the payment|
|»» type|body|string|false|ACCOUNT_ID, IBAN, PGNR, BGNR|
|»» account|body|string|false|Account number|
|»» message|body|string|false|Message for the debtor to appear on their transaction|
|» amount|body|object|false|none|
|»» value|body|number(double)|false|Monetary amount of the payment|
|»» currency|body|string|false|Currency code according to ISO 4217|

<h3 id="initiate-payment-responses">Responses</h3>

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

## Get payment

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId} HTTP/1.1
Host: api.northbricks.io
Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bic}/payments/{paymentId}`

*Get payment*

Returns all information about a payment

<h3 id="get-payment-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bic|path|string|true|BIC of bank|
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

<h3 id="get-payment-responses">Responses</h3>

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

## Confirm payment

> Code samples

```shell
# You can also use wget
curl -X PUT https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId} \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId} HTTP/1.1
Host: api.northbricks.io

```

```javascript
var headers = {
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Authorization':'Bearer {access-token}'

};

fetch('https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
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

result = RestClient.put 'https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}");
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
    req, err := http.NewRequest("PUT", "https://api.northbricks.io/api/v1/banks/{bic}/payments/{paymentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /banks/{bic}/payments/{paymentId}`

*Confirm payment*

Confirm a previously initialized payment

<h3 id="confirm-payment-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bic|path|string|true|BIC of bank|
|paymentId|path|string|true|ID of payment|

<h3 id="confirm-payment-responses">Responses</h3>

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
