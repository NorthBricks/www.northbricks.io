<h1 id="Northbricks-Bank-API-Bank-auth">Bank-auth</h1>

Bank operations

## Authenticate to bank

> Code samples

```shell
# You can also use wget
curl -X GET https://api.northbricks.io/api/v1/me/banks/{bic}/auth?access_token=string \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.northbricks.io/api/v1/me/banks/{bic}/auth?access_token=string HTTP/1.1
Host: api.northbricks.io

```

```javascript
var headers = {
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: 'https://api.northbricks.io/api/v1/me/banks/{bic}/auth',
  method: 'get',
  data: '?access_token=string',
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

fetch('https://api.northbricks.io/api/v1/me/banks/{bic}/auth?access_token=string',
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
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.northbricks.io/api/v1/me/banks/{bic}/auth',
  params: {
  'access_token' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.northbricks.io/api/v1/me/banks/{bic}/auth', params={
  'access_token': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("https://api.northbricks.io/api/v1/me/banks/{bic}/auth?access_token=string");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.northbricks.io/api/v1/me/banks/{bic}/auth", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /me/banks/{bic}/auth`

*Authenticate to bank*

Open this URL in a browser. User authenticates and gives consent to Northbricks to access their assets.

<h3 id="authentication-to-bank-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|bic|path|string|true|BIC of the bank to get.|
|access_token|query|string|true|Access token to Northbricks.|

<h3 id="authentication-to-bank-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Authorization successful|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Wrong credentials|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Bank not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
OAuth2 ( Scopes: read )
</aside>
