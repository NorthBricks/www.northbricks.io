# transaction

Transaction operations

## GET /transactions

> Code samples

```shell
# You can also use wget
curl -X GET http://api.northbricks.io/api/v1/transactions?userId=string \
  -H 'Accept: application/json'

```

```http
GET http://api.northbricks.io/api/v1/transactions?userId=string HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://api.northbricks.io/api/v1/transactions',
  method: 'get',
  data: '?userId=string',
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

fetch('http://api.northbricks.io/api/v1/transactions?userId=string',
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

result = RestClient.get 'http://api.northbricks.io/api/v1/transactions',
  params: {
  'userId' => 'string'
}, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://api.northbricks.io/api/v1/transactions', params={
  'userId': 'string'
}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://api.northbricks.io/api/v1/transactions?userId=string");
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
userId|query|string|true|ID of user to get transactions from



> Example responses

```json
[
  {
    "id": 0,
    "amount": 0,
    "description": "string"
  }
]
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid userId supplied|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>


## GET /transactions/{transactionId}

> Code samples

```shell
# You can also use wget
curl -X GET http://api.northbricks.io/api/v1/transactions/{transactionId} \
  -H 'Accept: application/json'

```

```http
GET http://api.northbricks.io/api/v1/transactions/{transactionId} HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://api.northbricks.io/api/v1/transactions/{transactionId}',
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

fetch('http://api.northbricks.io/api/v1/transactions/{transactionId}',
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

result = RestClient.get 'http://api.northbricks.io/api/v1/transactions/{transactionId}',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://api.northbricks.io/api/v1/transactions/{transactionId}', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("http://api.northbricks.io/api/v1/transactions/{transactionId}");
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
transactionId|path|integer(int64)|true|ID of the transaction to get



> Example responses

```json
{
  "id": 0,
  "amount": 0,
  "description": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Transaction](#schematransaction)
400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid userId supplied|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
None
</aside>





