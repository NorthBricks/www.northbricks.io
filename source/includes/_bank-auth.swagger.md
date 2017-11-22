# bank-auth

Bank operations

## GET /me/banks/{bankId}/auth

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks/{bankId}/auth?access_token=string

```

```http
GET https://api.northbricks.io/api/v1/me/banks/{bankId}/auth?access_token=string HTTP/1.1
Host: api.northbricks.io



```

```javascript

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bankId}/auth',
  method: 'get',
  data: '?access_token=string',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})
```

```javascript--nodejs
const request = require('node-fetch');


fetch('https://api.northbricks.io/api/v1/me/banks/{bankId}/auth?access_token=string',
{
  method: 'GET'


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



result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks/{bankId}/auth',
  params: {
  'access_token' => 'string'
}

p JSON.parse(result)
```

```python
import requests

r = requests.get('https://api.northbricks.io/api/v1/me/banks/{bankId}/auth', params={
  'access_token': 'string'
)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks/{bankId}/auth?access_token=string");
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

*User authorize Northbricks to access their assets*

User authenticates and gives consent to Northbricks to access their assets.

### Parameters

Parameter|In|Type|Required|Description
---|---|---|---|---|
bankId|path|string|true|Id of the bank to get.
access_token|query|string|true|Access token to Northbricks.



### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Authorization successful|None
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None
404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>





