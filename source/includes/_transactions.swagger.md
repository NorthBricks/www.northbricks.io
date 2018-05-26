<h1 id="Northbricks-Transaction-API-Transactions">Transactions</h1>

Transaction operations

## Get all transactions

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/accounts/{accountId}/transactions`

Returns all transactions for the user

<h3 id="get-all-transactions-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|
|accountId|path|string|true|ID of account|

> Example responses

> 200 Response

```json
{
  "transactions": [
    {
      "id": "string",
      "description": "string",
      "bookingDate": "2018-05-26T21:48:25Z",
      "valueDate": "2018-05-26T21:48:25Z",
      "amount": {
        "value": 0,
        "currency": "string"
      },
      "relatedParty": {
        "name": "string"
      }
    }
  ]
}
```

<h3 id="get-all-transactions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bank account not found on user|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<h3 id="get-all-transactions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» transactions|[[Transaction](#schematransaction)]|false|none|none|
|»» id|string|false|none|none|
|»» description|string|false|none|none|
|»» bookingDate|string(date-time)|false|none|none|
|»» valueDate|string(date-time)|false|none|none|
|»» amount|object|false|none|none|
|»»» value|number(double)|false|none|none|
|»»» currency|string|false|none|none|
|»» relatedParty|object|false|none|none|
|»»» name|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: transaction:read )
</aside>

## Get transaction

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/accounts/{accountId}/transactions/{transactionId}`

Returns all information about a transaction

<h3 id="get-transaction-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|ID of bank|
|accountId|path|string|true|ID of account|
|transactionId|path|string|true|ID of transaction|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "description": "string",
  "bookingDate": "2018-05-26T21:48:25Z",
  "valueDate": "2018-05-26T21:48:25Z",
  "amount": {
    "value": 0,
    "currency": "string"
  },
  "relatedParty": {
    "name": "string"
  }
}
```

<h3 id="get-transaction-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Transaction](#schematransaction)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bank account not found on user|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: transaction:read )
</aside>
