# transactions

Transaction operations

## GET /banks/{bankId}/accounts/{accountId}/transactions

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

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
  'Accept':'application/json'

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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
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

*List transactions*

Returns all transactions for the user

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|ID of bank
accountId|path|string|true|ID of account



> Example responses

```json
[
  {
    "id": "string",
    "description": "string",
    "bookingDate": "2017-10-17T07:03:36Z",
    "valueDate": "2017-10-17T07:03:36Z",
    "amount": {
      "value": 0,
      "currency": "string"
    },
    "relatedParty": {
      "name": "string"
    }
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|Inline

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: transaction:read )
</aside>


## GET /banks/{bankId}/accounts/{accountId}/transactions/{transactionId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId} \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

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
  'Accept':'application/json'

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
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/banks/{bankId}/accounts/{accountId}/transactions/{transactionId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
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

*Returns a transaction*

Returns all information about a transaction

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|ID of bank
accountId|path|string|true|ID of account
transactionId|path|string|true|ID of transaction



> Example responses

```json
{
  "id": "string",
  "description": "string",
  "bookingDate": "2017-10-17T07:03:36Z",
  "valueDate": "2017-10-17T07:03:36Z",
  "amount": {
    "value": 0,
    "currency": "string"
  },
  "relatedParty": {
    "name": "string"
  }
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Transaction](#schematransaction)
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Transaction not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: transaction:read )
</aside>





