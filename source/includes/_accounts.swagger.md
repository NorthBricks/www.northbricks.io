# accounts

Account operations

## GET /banks/{bankId}/accounts

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

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
  'Accept':'application/json'

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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
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

*Information about accounts*

Returns accounts in a bank for the user

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|Id of the bank.



> Example responses

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
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Accounts in the bank|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bank not found on user|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: account:read )
</aside>


## GET /banks/{bankId}/accounts/{accountId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId} \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

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
  'Accept':'application/json'

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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
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

*Information about an account*

Returns the account

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|Id of the bank.
accountId|path|string|true|Id of the account.



> Example responses

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
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|The account|[Account](#schemaaccount)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Account not found on user|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: account:read )
</aside>





