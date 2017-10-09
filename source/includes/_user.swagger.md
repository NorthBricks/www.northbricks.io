# Authentication





- oAuth2 authentication. This API uses OAuth 2 with the authorization code flow.

    - Flow: authorizationCode
    - Authorization URL = [https://api.northbricks.io/oauth/authorize](https://api.northbricks.io/oauth/authorize)
    - Token URL = [https://api.northbricks.io/oauth/token](https://api.northbricks.io/oauth/token)

|Scope|Scope Description|
|---|---|
|read|Grants read access|
|account:read|Grants read access to accounts|
|transaction:read|Grants read access to transactions|






# user

User operations

## GET /me/user

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/user \
  -H 'Accept: application/json'

```

```http
GET https://api.northbricks.io/api/v1/me/user HTTP/1.1
Host: api.northbricks.io

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/user',
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

fetch('https://api.northbricks.io/api/v1/me/user',
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

result = RestClient.get 'https://api.northbricks.io/api/v1/me/user',
  params: {
  }, headers: headers


p JSON.parse(result)
```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.northbricks.io/api/v1/me/user', params={

}, headers = headers)

print r.json()
```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/user");
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

*Information about current user*

Returns user information

> Example responses

```json
{
  "id": "string",
  "username": "string",
  "oauth2Scope": "string",
  "firstName": "string",
  "lastName": "string",
  "email": "string",
  "phone": "string"
}
```
### Responses

Status|Meaning|Description|Schema
---|---|---|---|
200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|User information|[User](#schemauser)
401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
oauth2 ( Scopes: read )
</aside>





