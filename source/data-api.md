---
title: Manatee Current Data-API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2
---

<h1 id="manatee-current-data-api">Manatee Current Data-API v0.0.1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

OpenAPI specs for Mindlab's manatee V3 data-api - Legecy version. Exact ins and outs may have changed

Base URLs:

* <a href="http://localhost:8080">http://localhost:8080</a>

<h1 id="manatee-current-data-api-experiment">Experiment</h1>

Experiments routes

## get__experiments

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/experiments \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/experiments HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiments',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiments',
{
  method: 'GET',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/experiments',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/experiments', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiments");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/experiments", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /experiments`

*[user] request list of all experiments*

> Body parameter

```json
{}
```

<h3 id="get__experiments-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Query to be match the experiments too|

> Example responses

> 200 Response

<h3 id="get__experiments-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Experiment successfully got|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="get__experiments-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Experiment](#schemaexperiment)]|false|none|none|
|» _id|string|true|none|none|
|» name|string|true|none|none|
|» elements|[[Element](#schemaelement)]|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» type|string|false|none|none|
|»»» content|object|false|none|none|
|»»» __v|integer|false|none|none|
|»» component|string|false|none|none|
|»» configuration|object|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|
|» resources|[[Resource](#schemaresource)]|false|none|none|
|» listening|array|false|none|none|
|»» *anonymous*|any|false|none|none|
|» created|string|false|none|none|
|» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## post__experiment

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/experiment \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST http://localhost:8080/experiment HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment',
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
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment',
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
  'Accept' => '*/*'
}

result = RestClient.post 'http://localhost:8080/experiment',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('http://localhost:8080/experiment', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/experiment", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /experiment`

*[user]  create an experiment*

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="post__experiment-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Experiment name|
|» name|body|string|false|none|

> Example responses

> 200 Response

<h3 id="post__experiment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated experiment|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="post__experiment-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__experiment_{experiment_id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/experiment/{experiment_id} \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/experiment/{experiment_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/experiment/{experiment_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/experiment/{experiment_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/experiment/{experiment_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /experiment/{experiment_id}`

*[user] get the specified experiment*

Allows for grabbing experiments via path parameter

<h3 id="get__experiment_{experiment_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="get__experiment_{experiment_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully got full experiment|[Experiment](#schemaexperiment)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="get__experiment_{experiment_id}-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## delete__experiment_{experiment_id}

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/experiment/{experiment_id} \
  -H 'Accept: */*'

```

```http
DELETE http://localhost:8080/experiment/{experiment_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}',
{
  method: 'DELETE',

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
  'Accept' => '*/*'
}

result = RestClient.delete 'http://localhost:8080/experiment/{experiment_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('http://localhost:8080/experiment/{experiment_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/experiment/{experiment_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /experiment/{experiment_id}`

*[user] delete the specified experiment*

<h3 id="delete__experiment_{experiment_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="delete__experiment_{experiment_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully got deleted experiment|[#/components/responses/ok_message_response](#schema#/components/responses/ok_message_response)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="delete__experiment_{experiment_id}-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## put__experiment_{experiment_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/experiment/{experiment_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/experiment/{experiment_id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}',
{
  method: 'PUT',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/experiment/{experiment_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/experiment/{experiment_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/experiment/{experiment_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /experiment/{experiment_id}`

*[user] update the specified experiment*

> Body parameter

```json
{}
```

<h3 id="put__experiment_{experiment_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|The information you wish to update this experiment with|
|experiment_id|path|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="put__experiment_{experiment_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated experiment|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="put__experiment_{experiment_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__experiment_{experiment_id}_create_add_element

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/experiment/{experiment_id}/create_add_element \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/experiment/{experiment_id}/create_add_element HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}/create_add_element',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}/create_add_element',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/experiment/{experiment_id}/create_add_element',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/experiment/{experiment_id}/create_add_element', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}/create_add_element");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/experiment/{experiment_id}/create_add_element", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /experiment/{experiment_id}/create_add_element`

*[user] Create then add a element to experiment*

First create an element, then add that element automatically to this experiment

<h3 id="put__experiment_{experiment_id}_create_add_element-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="put__experiment_{experiment_id}_create_add_element-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully created and added element|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="put__experiment_{experiment_id}_create_add_element-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|
|» element|[Element](#schemaelement)|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__experiment_{experiment_id}_remove_delete_element_{element_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id} \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/experiment/{experiment_id}/remove_delete_element/{element_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /experiment/{experiment_id}/remove_delete_element/{element_id}`

*[user] remove an elememnt from an experiment and delete it*

<h3 id="put__experiment_{experiment_id}_remove_delete_element_{element_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|
|element_id|path|string|true|The element ID|

> Example responses

> 200 Response

<h3 id="put__experiment_{experiment_id}_remove_delete_element_{element_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated experiment|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="put__experiment_{experiment_id}_remove_delete_element_{element_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__experiment_{experiment_id}_create_add_resource

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/experiment/{experiment_id}/create_add_resource \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/experiment/{experiment_id}/create_add_resource HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}/create_add_resource',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}/create_add_resource',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/experiment/{experiment_id}/create_add_resource',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/experiment/{experiment_id}/create_add_resource', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}/create_add_resource");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/experiment/{experiment_id}/create_add_resource", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /experiment/{experiment_id}/create_add_resource`

*[user] Create then add a resource to experiment*

First create an resource, then add that resource automatically to this experiment

<h3 id="put__experiment_{experiment_id}_create_add_resource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="put__experiment_{experiment_id}_create_add_resource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successfully created and added resource|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="put__experiment_{experiment_id}_create_add_resource-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|
|» resource|[Resource](#schemaresource)|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__experiment_{experiment_id}_remove_delete_resource_{resource_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id} \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/experiment/{experiment_id}/remove_delete_resource/{resource_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /experiment/{experiment_id}/remove_delete_resource/{resource_id}`

*[user] remove a resource from an experiment and delete it*

<h3 id="put__experiment_{experiment_id}_remove_delete_resource_{resource_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|experiment_id|path|string|true|The experiment ID|
|resource_id|path|string|true|The resource ID|

> Example responses

> 200 Response

<h3 id="put__experiment_{experiment_id}_remove_delete_resource_{resource_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated experiment|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|error stack in JSON|Inline|

<h3 id="put__experiment_{experiment_id}_remove_delete_resource_{resource_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» experiment|[Experiment](#schemaexperiment)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» elements|[[Element](#schemaelement)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»»» _id|string|true|none|none|
|»»»» name|string|true|none|none|
|»»»» type|string|false|none|none|
|»»»» content|object|false|none|none|
|»»»» __v|integer|false|none|none|
|»»» component|string|false|none|none|
|»»» configuration|object|false|none|none|
|»»» created|string|false|none|none|
|»»» __v|integer|false|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»» listening|array|false|none|none|
|»»» *anonymous*|any|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="manatee-current-data-api-element">Element</h1>

Elements routes

## get__element_{element_id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/element/{element_id} \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/element/{element_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/element/{element_id}',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/element/{element_id}',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/element/{element_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/element/{element_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/element/{element_id}");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/element/{element_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /element/{element_id}`

*[user] get a specific element*

<h3 id="get__element_{element_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|element_id|path|string|true|Element ID|

> Example responses

> 200 Response

<h3 id="get__element_{element_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|no errors returned|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|errors have been returned|Inline|

<h3 id="get__element_{element_id}-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## delete__element_{element_id}

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/element/{element_id} \
  -H 'Accept: */*'

```

```http
DELETE http://localhost:8080/element/{element_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/element/{element_id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('http://localhost:8080/element/{element_id}',
{
  method: 'DELETE',

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
  'Accept' => '*/*'
}

result = RestClient.delete 'http://localhost:8080/element/{element_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('http://localhost:8080/element/{element_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/element/{element_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/element/{element_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /element/{element_id}`

*[user] delete a specific element*

<h3 id="delete__element_{element_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|element_id|path|string|true|Element ID|

> Example responses

> 200 Response

<h3 id="delete__element_{element_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|everything went ok|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="delete__element_{element_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__element_{element_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/element/{element_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/element/{element_id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/element/{element_id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/element/{element_id}',
{
  method: 'PUT',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/element/{element_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/element/{element_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/element/{element_id}");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/element/{element_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /element/{element_id}`

*[user] update an element*

> Body parameter

```json
{}
```

<h3 id="put__element_{element_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Data for updateing the element with|
|element_id|path|string|true|Element ID|

> Example responses

> 200 Response

<h3 id="put__element_{element_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated element|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="put__element_{element_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» element|[Element](#schemaelement)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» resources|[[Resource](#schemaresource)]|false|none|none|
|»»» _id|string|true|none|none|
|»»» name|string|true|none|none|
|»»» type|string|false|none|none|
|»»» content|object|false|none|none|
|»»» __v|integer|false|none|none|
|»» component|string|false|none|none|
|»» configuration|object|false|none|none|
|»» created|string|false|none|none|
|»» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="manatee-current-data-api-resource">Resource</h1>

Resources routes

## get__resource

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/resource \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/resource HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/resource',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/resource',
{
  method: 'GET',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/resource',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/resource', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/resource");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/resource", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /resource`

*[user] lists all resources matching a query*

> Body parameter

```json
{}
```

<h3 id="get__resource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|Query to match the resources against, leave blank to match all|

> Example responses

> 200 Response

<h3 id="get__resource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|lists all resources matching query|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="get__resource-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Resource](#schemaresource)]|false|none|none|
|» _id|string|true|none|none|
|» name|string|true|none|none|
|» type|string|false|none|none|
|» content|object|false|none|none|
|» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## post__resource

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:8080/resource \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
POST http://localhost:8080/resource HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/resource',
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
  "name": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/resource',
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
  'Accept' => '*/*'
}

result = RestClient.post 'http://localhost:8080/resource',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.post('http://localhost:8080/resource', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/resource");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:8080/resource", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /resource`

*[user] create a resource*

> Body parameter

```json
{
  "name": "string"
}
```

<h3 id="post__resource-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|Details for making the object|
|» name|body|string|false|none|

> Example responses

> 200 Response

<h3 id="post__resource-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Succefully updated resource|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="post__resource-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» resource|[Resource](#schemaresource)|false|none|none|
|»» _id|string|true|none|none|
|»» name|string|true|none|none|
|»» type|string|false|none|none|
|»» content|object|false|none|none|
|»» __v|integer|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## get__resource_{resource_id}

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/resource/{resource_id} \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/resource/{resource_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/resource/{resource_id}',
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
  'Accept':'*/*'

};

fetch('http://localhost:8080/resource/{resource_id}',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/resource/{resource_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/resource/{resource_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/resource/{resource_id}");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/resource/{resource_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /resource/{resource_id}`

*[user] get the specified resource*

<h3 id="get__resource_{resource_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|resource_id|path|string|true|resource ID|

> Example responses

> 200 Response

<h3 id="get__resource_{resource_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|no errors returned|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|errors have been returned|Inline|

<h3 id="get__resource_{resource_id}-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## delete__resource_{resource_id}

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:8080/resource/{resource_id} \
  -H 'Accept: */*'

```

```http
DELETE http://localhost:8080/resource/{resource_id} HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/resource/{resource_id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('http://localhost:8080/resource/{resource_id}',
{
  method: 'DELETE',

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
  'Accept' => '*/*'
}

result = RestClient.delete 'http://localhost:8080/resource/{resource_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.delete('http://localhost:8080/resource/{resource_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/resource/{resource_id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:8080/resource/{resource_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /resource/{resource_id}`

*[user] delete a specific resource*

<h3 id="delete__resource_{resource_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|resource_id|path|string|true|resource ID|

> Example responses

> 200 Response

<h3 id="delete__resource_{resource_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|everything went ok|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="delete__resource_{resource_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## put__resource_{resource_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/resource/{resource_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/resource/{resource_id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/resource/{resource_id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/resource/{resource_id}',
{
  method: 'PUT',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/resource/{resource_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/resource/{resource_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/resource/{resource_id}");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/resource/{resource_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /resource/{resource_id}`

*[user] Update a resource*

> Body parameter

```json
{}
```

<h3 id="put__resource_{resource_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateDetails](#schemaupdatedetails)|true|The information for updating the resource|
|resource_id|path|string|true|resource ID|

> Example responses

> 200 Response

<h3 id="put__resource_{resource_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|everything went ok|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|unable to process the request|Inline|

<h3 id="put__resource_{resource_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|

Status Code **400**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|
|» error|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="manatee-current-data-api-session">Session</h1>

Session routes

## get__session

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:8080/session?session_info=string \
  -H 'Accept: */*'

```

```http
GET http://localhost:8080/session?session_info=string HTTP/1.1
Host: localhost:8080
Accept: */*

```

```javascript
var headers = {
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/session',
  method: 'get',
  data: '?session_info=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'*/*'

};

fetch('http://localhost:8080/session?session_info=string',
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
  'Accept' => '*/*'
}

result = RestClient.get 'http://localhost:8080/session',
  params: {
  'session_info' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': '*/*'
}

r = requests.get('http://localhost:8080/session', params={
  'session_info': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/session?session_info=string");
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
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:8080/session", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /session`

*[user] list sessions matching a query*

<h3 id="get__session-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|session_info|query|string|true|The experiment ID|

> Example responses

> 200 Response

<h3 id="get__session-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|no errors returned|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|errors have been returned|Inline|

<h3 id="get__session-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## put__session

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/session \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/session HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/session',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "_id": "string"
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/session',
{
  method: 'PUT',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/session',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/session', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/session");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/session", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /session`

*[user] update multiple sessions*

> Body parameter

```json
[
  {
    "_id": "string"
  }
]
```

<h3 id="put__session-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|true|The information for updating the resource|

> Example responses

> 200 Response

<h3 id="put__session-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|no errors returned|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|errors have been returned|Inline|

<h3 id="put__session-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## put__session_{session_id}

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:8080/session/{session_id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: */*'

```

```http
PUT http://localhost:8080/session/{session_id} HTTP/1.1
Host: localhost:8080
Content-Type: application/json
Accept: */*

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

$.ajax({
  url: 'http://localhost:8080/session/{session_id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'*/*'

};

fetch('http://localhost:8080/session/{session_id}',
{
  method: 'PUT',
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
  'Accept' => '*/*'
}

result = RestClient.put 'http://localhost:8080/session/{session_id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': '*/*'
}

r = requests.put('http://localhost:8080/session/{session_id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("http://localhost:8080/session/{session_id}");
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
        "Content-Type": []string{"application/json"},
        "Accept": []string{"*/*"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:8080/session/{session_id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /session/{session_id}`

*[user] Update a session*

> Body parameter

```json
{}
```

<h3 id="put__session_{session_id}-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UpdateDetails](#schemaupdatedetails)|true|The information for updating the resource|
|session_id|path|string|true|Session ID|

> Example responses

> 200 Response

<h3 id="put__session_{session_id}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|everything went ok|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|error stack in JSON|Inline|

<h3 id="put__session_{session_id}-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» message|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSexperiment_unpopulated">Experiment_unpopulated</h2>

<a id="schemaexperiment_unpopulated"></a>

```json
{
  "_id": "string",
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|true|none|none|
|name|string|true|none|none|

<h2 id="tocSexperiment">Experiment</h2>

<a id="schemaexperiment"></a>

```json
{
  "_id": "string",
  "name": "string",
  "elements": [
    {
      "_id": "string",
      "name": "string",
      "resources": [
        {
          "_id": "string",
          "name": "string",
          "type": "string",
          "content": {},
          "__v": 0
        }
      ],
      "component": "string",
      "configuration": {},
      "created": "string",
      "__v": 0
    }
  ],
  "resources": [
    {
      "_id": "string",
      "name": "string",
      "type": "string",
      "content": {},
      "__v": 0
    }
  ],
  "listening": [],
  "created": "string",
  "__v": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|true|none|none|
|name|string|true|none|none|
|elements|[[Element](#schemaelement)]|false|none|none|
|resources|[[Resource](#schemaresource)]|false|none|none|
|listening|[[Listener](#schemalistener)]|false|none|none|
|created|string|false|none|none|
|__v|integer|false|none|none|

<h2 id="tocSelement">Element</h2>

<a id="schemaelement"></a>

```json
{
  "_id": "string",
  "name": "string",
  "resources": [
    {
      "_id": "string",
      "name": "string",
      "type": "string",
      "content": {},
      "__v": 0
    }
  ],
  "component": "string",
  "configuration": {},
  "created": "string",
  "__v": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|true|none|none|
|name|string|true|none|none|
|resources|[[Resource](#schemaresource)]|false|none|none|
|component|string|false|none|none|
|configuration|object|false|none|none|
|created|string|false|none|none|
|__v|integer|false|none|none|

<h2 id="tocSresource">Resource</h2>

<a id="schemaresource"></a>

```json
{
  "_id": "string",
  "name": "string",
  "type": "string",
  "content": {},
  "__v": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_id|string|true|none|none|
|name|string|true|none|none|
|type|string|false|none|none|
|content|object|false|none|none|
|__v|integer|false|none|none|

<h2 id="tocSsession">Session</h2>

<a id="schemasession"></a>

```json
{}

```

### Properties

*None*

<h2 id="tocScomponent">Component</h2>

<a id="schemacomponent"></a>

```json
{
  "model": {
    "name": "string",
    "description": "string",
    "version": "string",
    "start": "string",
    "data": {},
    "configuration": {},
    "button_style": {},
    "default_configuration": {},
    "examples": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|model|object|true|none|none|
|» name|string|true|none|none|
|» description|string|false|none|none|
|» version|string|false|none|none|
|» start|string|false|none|none|
|» data|object|false|none|none|
|» configuration|object|false|none|none|
|» button_style|object|false|none|none|
|» default_configuration|object|false|none|none|
|» examples|object|false|none|none|

