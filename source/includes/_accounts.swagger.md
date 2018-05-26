<h1 id="Northbricks-Account-API-Accounts">Accounts</h1>

Account operations

## Get all accounts

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/accounts',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/accounts', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/accounts");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/accounts", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/accounts`

Returns accounts in a bank for the user

<h3 id="get-all-accounts-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|Id of the bank.|

> Example responses

> 200 Response

```json
{
  "accounts": [
    {
      "id": "string",
      "iban": "string",
      "type": "string",
      "status": "string",
      "currency": "string",
      "balance": 0,
      "owner": {
        "name": "string"
      }
    }
  ]
}
```

<h3 id="get-all-accounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Accounts in the bank|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bank not found on user|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<h3 id="get-all-accounts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» accounts|[[Account](#schemaaccount)]|false|none|none|
|»» id|string|false|none|none|
|»» iban|string|false|none|none|
|»» type|string|false|none|none|
|»» status|string|false|none|none|
|»» currency|string|false|none|none|
|»» balance|number(double)|false|none|none|
|»» owner|object|false|none|none|
|»»» name|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: account:read )
</aside>

## Get account

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}',
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

fetch('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}',
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

r = requests.get('https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}");
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
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /banks/{bankId}/accounts/{accountId}`

Returns the account

<h3 id="get-account-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bankId|path|string|true|Id of the bank.|
|accountId|path|string|true|Id of the account.|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "iban": "string",
  "type": "string",
  "status": "string",
  "currency": "string",
  "balance": 0,
  "owner": {
    "name": "string"
  }
}
```

<h3 id="get-account-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The account|[Account](#schemaaccount)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Account not found on user|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: account:read )
</aside>
