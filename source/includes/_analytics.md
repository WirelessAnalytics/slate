
---

<h1 id="analytics-transformed-">Analytics</h1>

Request Mobile and Wireless Charge information

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Analytics [Transformed]

Base URLs:

* <a href="/api/v2/analytics">/api/v2/analytics</a>

## Get resources for this service.

<a id="opIdgetAnalyticsResources"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /`

Return an array of the resources available.

<h3 id="get-resources-for-this-service.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|as_list|query|boolean|false|Return only a list of the resource identifiers.|
|as_access_list|query|boolean|false|Returns a list of the resources for role access designation.|
|include_access|query|boolean|false|Include the access permissions for the returned resource.|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string"
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RedshiftDbs>
  <resource>
    <name>string</name>
  </resource>
</RedshiftDbs>
```

<h3 id="get-resources-for-this-service.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Resource List|[RedshiftDbs](#schemaredshiftdbs)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one or more DbSchemaResources.

<a id="opIdgetAnalyticsDbSchemaResources"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema`

Use the 'ids' parameter to limit records that are returned. By default, all records up to the maximum are returned. Use the 'fields' parameters to limit properties returned for each record. By default, all fields are returned for each record.

<h3 id="retrieve-one-or-more-dbschemaresources.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="retrieve-one-or-more-dbschemaresources.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchemas|[TableSchemas](#schematableschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Create one or more tables.

<a id="opIdcreateAnalyticsTables"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_schema', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_schema', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_schema`

Post data should be a single table definition or an array of table definitions.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="create-one-or-more-tables.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TableSchemas](#schematableschemas)|false|TableSchemas|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="create-one-or-more-tables.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchemas|[TableSchemas](#schematableschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (replace) one or more tables.

<a id="opIdreplaceAnalyticsTables"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_schema', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_schema', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_schema`

Post data should be a single table definition or an array of table definitions.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="update-(replace)-one-or-more-tables.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TableSchemas](#schematableschemas)|false|TableSchemas|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="update-(replace)-one-or-more-tables.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchemas|[TableSchemas](#schematableschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (patch) one or more tables.

<a id="opIdupdateAnalyticsTables"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_schema', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_schema', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_schema`

Post data should be a single table definition or an array of table definitions.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="update-(patch)-one-or-more-tables.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TableSchemas](#schematableschemas)|false|TableSchemas|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="update-(patch)-one-or-more-tables.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchemas|[TableSchemas](#schematableschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve table definition for the given table.

<a id="opIddescribeAnalyticsTable"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema/analytics`

This describes the table, its fields and relations to other tables.

<h3 id="retrieve-table-definition-for-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "label": "string",
  "description": "string",
  "plural": "string",
  "primary_key": [
    "string"
  ],
  "name_field": "string",
  "field": [
    null
  ],
  "related": [
    null
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchema>
  <name>string</name>
  <label>string</label>
  <description>string</description>
  <plural>string</plural>
  <primary_key>string</primary_key>
  <name_field>string</name_field>
  <field/>
  <related/>
</TableSchema>
```

<h3 id="retrieve-table-definition-for-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchema|[TableSchema](#schematableschema)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Create a table with the given properties and fields.

<a id="opIdcreateAnalyticsTable"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_schema/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_schema/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_schema/analytics`

Post data should be an array of field properties.

> Body parameter

```json
{
  "name": "string",
  "label": "string",
  "description": "string",
  "plural": "string",
  "primary_key": [
    "string"
  ],
  "name_field": "string",
  "field": [
    null
  ],
  "related": [
    null
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchema>
  <name>string</name>
  <label>string</label>
  <description>string</description>
  <plural>string</plural>
  <primary_key>string</primary_key>
  <name_field>string</name_field>
  <field/>
  <related/>
</TableSchema>
```

<h3 id="create-a-table-with-the-given-properties-and-fields.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TableSchema](#schematableschema)|false|TableSchema|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="create-a-table-with-the-given-properties-and-fields.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (replace) a table with the given properties.

<a id="opIdreplaceAnalyticsTable"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_schema/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_schema/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_schema/analytics`

Post data should be an array of field properties.

> Body parameter

```json
{
  "name": "string",
  "label": "string",
  "description": "string",
  "plural": "string",
  "primary_key": [
    "string"
  ],
  "name_field": "string",
  "field": [
    null
  ],
  "related": [
    null
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchema>
  <name>string</name>
  <label>string</label>
  <description>string</description>
  <plural>string</plural>
  <primary_key>string</primary_key>
  <name_field>string</name_field>
  <field/>
  <related/>
</TableSchema>
```

<h3 id="update-(replace)-a-table-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[TableSchema](#schematableschema)|false|TableSchema|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-(replace)-a-table-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (patch) a table with the given properties.

<a id="opIdupdateAnalyticsRelationships"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_schema/analytics/_related', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_schema/analytics/_related', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_schema/analytics/_related`

Post data should be an array of relationship properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "alias": "string",
      "label": "string",
      "description": "string",
      "type": "string",
      "field": "string",
      "ref_table": "string",
      "ref_field": "string",
      "junction_table": "string",
      "junction_field": "string",
      "junction_ref_field": "string",
      "always_fetch": true
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchemas>
  <resource>
    <name>string</name>
    <alias>string</alias>
    <label>string</label>
    <description>string</description>
    <type>string</type>
    <field>string</field>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <junction_table>string</junction_table>
    <junction_field>string</junction_field>
    <junction_ref_field>string</junction_ref_field>
    <always_fetch>true</always_fetch>
  </resource>
</RelationshipSchemas>
```

<h3 id="update-(patch)-a-table-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RelationshipSchemas](#schemarelationshipschemas)|false|RelationshipSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-(patch)-a-table-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Delete (aka drop) the given table.

<a id="opIddeleteAnalyticsTable"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_schema/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_schema/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_schema/analytics`

Careful, this drops the database table and all of its contents.

<h3 id="delete-(aka-drop)-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="delete-(aka-drop)-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve table field definitions for the given table.

<a id="opIddescribeAnalyticsFields"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema/analytics/_field', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema/analytics/_field', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema/analytics/_field`

This describes the table's fields.

<h3 id="retrieve-table-field-definitions-for-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default_value": "string",
      "required": true,
      "allow_null": true,
      "fixed_length": true,
      "supports_multibyte": true,
      "auto_increment": true,
      "is_primary_key": true,
      "is_foreign_key": true,
      "ref_table": "string",
      "ref_field": "string",
      "validation": [
        "string"
      ],
      "value": [
        "string"
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <type>string</type>
    <db_type>string</db_type>
    <length>0</length>
    <precision>0</precision>
    <scale>0</scale>
    <default_value>string</default_value>
    <required>true</required>
    <allow_null>true</allow_null>
    <fixed_length>true</fixed_length>
    <supports_multibyte>true</supports_multibyte>
    <auto_increment>true</auto_increment>
    <is_primary_key>true</is_primary_key>
    <is_foreign_key>true</is_foreign_key>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <validation>string</validation>
    <value>string</value>
  </resource>
</FieldSchemas>
```

<h3 id="retrieve-table-field-definitions-for-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|FieldSchemas|[FieldSchemas](#schemafieldschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Create table fields.

<a id="opIdcreateAnalyticsFields"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_schema/analytics/_field', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_schema/analytics/_field', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_schema/analytics/_field`

Post data should be an array of fields and their properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default_value": "string",
      "required": true,
      "allow_null": true,
      "fixed_length": true,
      "supports_multibyte": true,
      "auto_increment": true,
      "is_primary_key": true,
      "is_foreign_key": true,
      "ref_table": "string",
      "ref_field": "string",
      "validation": [
        "string"
      ],
      "value": [
        "string"
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <type>string</type>
    <db_type>string</db_type>
    <length>0</length>
    <precision>0</precision>
    <scale>0</scale>
    <default_value>string</default_value>
    <required>true</required>
    <allow_null>true</allow_null>
    <fixed_length>true</fixed_length>
    <supports_multibyte>true</supports_multibyte>
    <auto_increment>true</auto_increment>
    <is_primary_key>true</is_primary_key>
    <is_foreign_key>true</is_foreign_key>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <validation>string</validation>
    <value>string</value>
  </resource>
</FieldSchemas>
```

<h3 id="create-table-fields.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FieldSchemas](#schemafieldschemas)|false|FieldSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="create-table-fields.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (replace) table fields with the given properties.

<a id="opIdreplaceAnalyticsFields"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_schema/analytics/_field', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_schema/analytics/_field', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_schema/analytics/_field`

Post data should be an array of fields and their properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default_value": "string",
      "required": true,
      "allow_null": true,
      "fixed_length": true,
      "supports_multibyte": true,
      "auto_increment": true,
      "is_primary_key": true,
      "is_foreign_key": true,
      "ref_table": "string",
      "ref_field": "string",
      "validation": [
        "string"
      ],
      "value": [
        "string"
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <type>string</type>
    <db_type>string</db_type>
    <length>0</length>
    <precision>0</precision>
    <scale>0</scale>
    <default_value>string</default_value>
    <required>true</required>
    <allow_null>true</allow_null>
    <fixed_length>true</fixed_length>
    <supports_multibyte>true</supports_multibyte>
    <auto_increment>true</auto_increment>
    <is_primary_key>true</is_primary_key>
    <is_foreign_key>true</is_foreign_key>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <validation>string</validation>
    <value>string</value>
  </resource>
</FieldSchemas>
```

<h3 id="update-(replace)-table-fields-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FieldSchemas](#schemafieldschemas)|false|FieldSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-(replace)-table-fields-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (patch) table fields with the given properties.

<a id="opIdupdateAnalyticsFields"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_schema/analytics/_field', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_schema/analytics/_field', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_schema/analytics/_field`

Post data should be an array of field properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default_value": "string",
      "required": true,
      "allow_null": true,
      "fixed_length": true,
      "supports_multibyte": true,
      "auto_increment": true,
      "is_primary_key": true,
      "is_foreign_key": true,
      "ref_table": "string",
      "ref_field": "string",
      "validation": [
        "string"
      ],
      "value": [
        "string"
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <type>string</type>
    <db_type>string</db_type>
    <length>0</length>
    <precision>0</precision>
    <scale>0</scale>
    <default_value>string</default_value>
    <required>true</required>
    <allow_null>true</allow_null>
    <fixed_length>true</fixed_length>
    <supports_multibyte>true</supports_multibyte>
    <auto_increment>true</auto_increment>
    <is_primary_key>true</is_primary_key>
    <is_foreign_key>true</is_foreign_key>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <validation>string</validation>
    <value>string</value>
  </resource>
</FieldSchemas>
```

<h3 id="update-(patch)-table-fields-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FieldSchemas](#schemafieldschemas)|false|FieldSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-(patch)-table-fields-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Delete (aka drop) the given fields.

<a id="opIddeleteAnalyticsFields"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_schema/analytics/_field', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_schema/analytics/_field', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_schema/analytics/_field`

Careful, this drops the table column and all of its contents.

<h3 id="delete-(aka-drop)-the-given-fields.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="delete-(aka-drop)-the-given-fields.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve relationships definition for the given table.

<a id="opIddescribeAnalyticsRelationships"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema/analytics/_related', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema/analytics/_related', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema/analytics/_related`

This describes the table relationships to other tables.

<h3 id="retrieve-relationships-definition-for-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "alias": "string",
      "label": "string",
      "description": "string",
      "type": "string",
      "field": "string",
      "ref_table": "string",
      "ref_field": "string",
      "junction_table": "string",
      "junction_field": "string",
      "junction_ref_field": "string",
      "always_fetch": true
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchemas>
  <resource>
    <name>string</name>
    <alias>string</alias>
    <label>string</label>
    <description>string</description>
    <type>string</type>
    <field>string</field>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <junction_table>string</junction_table>
    <junction_field>string</junction_field>
    <junction_ref_field>string</junction_ref_field>
    <always_fetch>true</always_fetch>
  </resource>
</RelationshipSchemas>
```

<h3 id="retrieve-relationships-definition-for-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|RelationshipSchemas|[RelationshipSchemas](#schemarelationshipschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Create table relationships with the given properties.

<a id="opIdcreateAnalyticsRelationships"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_schema/analytics/_related', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_schema/analytics/_related', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_schema/analytics/_related`

Post data should be an array of relationship properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "alias": "string",
      "label": "string",
      "description": "string",
      "type": "string",
      "field": "string",
      "ref_table": "string",
      "ref_field": "string",
      "junction_table": "string",
      "junction_field": "string",
      "junction_ref_field": "string",
      "always_fetch": true
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchemas>
  <resource>
    <name>string</name>
    <alias>string</alias>
    <label>string</label>
    <description>string</description>
    <type>string</type>
    <field>string</field>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <junction_table>string</junction_table>
    <junction_field>string</junction_field>
    <junction_ref_field>string</junction_ref_field>
    <always_fetch>true</always_fetch>
  </resource>
</RelationshipSchemas>
```

<h3 id="create-table-relationships-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RelationshipSchemas](#schemarelationshipschemas)|false|RelationshipSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="create-table-relationships-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (replace) table relationships with the given properties.

<a id="opIdreplaceAnalyticsRelationships"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_schema/analytics/_related', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_schema/analytics/_related', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_schema/analytics/_related`

Post data should be an array of relationship properties.

> Body parameter

```json
{
  "resource": [
    {
      "name": "string",
      "alias": "string",
      "label": "string",
      "description": "string",
      "type": "string",
      "field": "string",
      "ref_table": "string",
      "ref_field": "string",
      "junction_table": "string",
      "junction_field": "string",
      "junction_ref_field": "string",
      "always_fetch": true
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchemas>
  <resource>
    <name>string</name>
    <alias>string</alias>
    <label>string</label>
    <description>string</description>
    <type>string</type>
    <field>string</field>
    <ref_table>string</ref_table>
    <ref_field>string</ref_field>
    <junction_table>string</junction_table>
    <junction_field>string</junction_field>
    <junction_ref_field>string</junction_ref_field>
    <always_fetch>true</always_fetch>
  </resource>
</RelationshipSchemas>
```

<h3 id="update-(replace)-table-relationships-with-the-given-properties.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RelationshipSchemas](#schemarelationshipschemas)|false|RelationshipSchemas|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-(replace)-table-relationships-with-the-given-properties.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Delete the given table relationships.

<a id="opIddeleteAnalyticsRelationships"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_schema/analytics/_related', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_schema/analytics/_related', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_schema/analytics/_related`

Removes the relationships between tables.

<h3 id="delete-the-given-table-relationships.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="delete-the-given-table-relationships.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve the definition of the given field for the given table.

<a id="opIddescribeAnalyticsField"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field/{field_name}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema/analytics/_field/{field_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema/analytics/_field/{field_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema/analytics/_field/{field_name}`

This describes the field and its properties.

<h3 id="retrieve-the-definition-of-the-given-field-for-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|
|table_name|path|string|true|Name of the table to perform operations on.|
|field_name|path|string|true|Name of the field to perform operations on.|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "label": "string",
  "type": "string",
  "db_type": "string",
  "length": 0,
  "precision": 0,
  "scale": 0,
  "default_value": "string",
  "required": true,
  "allow_null": true,
  "fixed_length": true,
  "supports_multibyte": true,
  "auto_increment": true,
  "is_primary_key": true,
  "is_foreign_key": true,
  "ref_table": "string",
  "ref_field": "string",
  "validation": [
    "string"
  ],
  "value": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchema>
  <name>string</name>
  <label>string</label>
  <type>string</type>
  <db_type>string</db_type>
  <length>0</length>
  <precision>0</precision>
  <scale>0</scale>
  <default_value>string</default_value>
  <required>true</required>
  <allow_null>true</allow_null>
  <fixed_length>true</fixed_length>
  <supports_multibyte>true</supports_multibyte>
  <auto_increment>true</auto_increment>
  <is_primary_key>true</is_primary_key>
  <is_foreign_key>true</is_foreign_key>
  <ref_table>string</ref_table>
  <ref_field>string</ref_field>
  <validation>string</validation>
  <value>string</value>
</FieldSchema>
```

<h3 id="retrieve-the-definition-of-the-given-field-for-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|FieldSchema|[FieldSchema](#schemafieldschema)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update one field by identifier.

<a id="opIdupdateAnalyticsField"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field/{field_name}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_schema/analytics/_field/{field_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_schema/analytics/_field/{field_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_schema/analytics/_field/{field_name}`

Post data should be an array of field properties for the given field.

> Body parameter

```json
{
  "name": "string",
  "label": "string",
  "type": "string",
  "db_type": "string",
  "length": 0,
  "precision": 0,
  "scale": 0,
  "default_value": "string",
  "required": true,
  "allow_null": true,
  "fixed_length": true,
  "supports_multibyte": true,
  "auto_increment": true,
  "is_primary_key": true,
  "is_foreign_key": true,
  "ref_table": "string",
  "ref_field": "string",
  "validation": [
    "string"
  ],
  "value": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<FieldSchema>
  <name>string</name>
  <label>string</label>
  <type>string</type>
  <db_type>string</db_type>
  <length>0</length>
  <precision>0</precision>
  <scale>0</scale>
  <default_value>string</default_value>
  <required>true</required>
  <allow_null>true</allow_null>
  <fixed_length>true</fixed_length>
  <supports_multibyte>true</supports_multibyte>
  <auto_increment>true</auto_increment>
  <is_primary_key>true</is_primary_key>
  <is_foreign_key>true</is_foreign_key>
  <ref_table>string</ref_table>
  <ref_field>string</ref_field>
  <validation>string</validation>
  <value>string</value>
</FieldSchema>
```

<h3 id="update-one-field-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FieldSchema](#schemafieldschema)|false|FieldSchema|
|table_name|path|string|true|Name of the table to perform operations on.|
|field_name|path|string|true|Name of the field to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-one-field-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Remove the given field from the given table.

<a id="opIddeleteAnalyticsField"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_field/{field_name}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_schema/analytics/_field/{field_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_schema/analytics/_field/{field_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_schema/analytics/_field/{field_name}`

Careful, this drops the database table field/column and all of its contents.

<h3 id="remove-the-given-field-from-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|table_name|path|string|true|Name of the table to perform operations on.|
|field_name|path|string|true|Name of the field to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="remove-the-given-field-from-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve the definition of the given relationship for the given table.

<a id="opIddescribeAnalyticsRelationship"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related/{relationship_name}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_schema/analytics/_related/{relationship_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_schema/analytics/_related/{relationship_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_schema/analytics/_related/{relationship_name}`

This describes the relationship and its properties.

<h3 id="retrieve-the-definition-of-the-given-relationship-for-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|refresh|query|boolean|false|Refresh any cached resource list on the server.|
|table_name|path|string|true|Name of the table to perform operations on.|
|relationship_name|path|string|true|Name of the relationship to perform operations on.|

> Example responses

> 200 Response

```json
{
  "name": "string",
  "alias": "string",
  "label": "string",
  "description": "string",
  "type": "string",
  "field": "string",
  "ref_table": "string",
  "ref_field": "string",
  "junction_table": "string",
  "junction_field": "string",
  "junction_ref_field": "string",
  "always_fetch": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchema>
  <name>string</name>
  <alias>string</alias>
  <label>string</label>
  <description>string</description>
  <type>string</type>
  <field>string</field>
  <ref_table>string</ref_table>
  <ref_field>string</ref_field>
  <junction_table>string</junction_table>
  <junction_field>string</junction_field>
  <junction_ref_field>string</junction_ref_field>
  <always_fetch>true</always_fetch>
</RelationshipSchema>
```

<h3 id="retrieve-the-definition-of-the-given-relationship-for-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|RelationshipSchema|[RelationshipSchema](#schemarelationshipschema)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update one relationship by identifier.

<a id="opIdupdateAnalyticsRelationship"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related/{relationship_name}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_schema/analytics/_related/{relationship_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_schema/analytics/_related/{relationship_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_schema/analytics/_related/{relationship_name}`

Post data should be an array of properties for the given relationship.

> Body parameter

```json
{
  "name": "string",
  "alias": "string",
  "label": "string",
  "description": "string",
  "type": "string",
  "field": "string",
  "ref_table": "string",
  "ref_field": "string",
  "junction_table": "string",
  "junction_field": "string",
  "junction_ref_field": "string",
  "always_fetch": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RelationshipSchema>
  <name>string</name>
  <alias>string</alias>
  <label>string</label>
  <description>string</description>
  <type>string</type>
  <field>string</field>
  <ref_table>string</ref_table>
  <ref_field>string</ref_field>
  <junction_table>string</junction_table>
  <junction_field>string</junction_field>
  <junction_ref_field>string</junction_ref_field>
  <always_fetch>true</always_fetch>
</RelationshipSchema>
```

<h3 id="update-one-relationship-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[RelationshipSchema](#schemarelationshipschema)|false|RelationshipSchema|
|table_name|path|string|true|Name of the table to perform operations on.|
|relationship_name|path|string|true|Name of the relationship to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="update-one-relationship-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Remove the given relationship from the given table.

<a id="opIddeleteAnalyticsRelationship"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_schema/analytics/_related/{relationship_name}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_schema/analytics/_related/{relationship_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_schema/analytics/_related/{relationship_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_schema/analytics/_related/{relationship_name}`

Removes the relationship between the tables given.

<h3 id="remove-the-given-relationship-from-the-given-table.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|table_name|path|string|true|Name of the table to perform operations on.|
|relationship_name|path|string|true|Name of the relationship to perform operations on.|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Success>
  <success>true</success>
</Success>
```

<h3 id="remove-the-given-relationship-from-the-given-table.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success Response|[Success](#schemasuccess)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one or more Tables.

<a id="opIdgetAnalyticsTables"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_table', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_table', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_table`

Use the 'ids' parameter to limit records that are returned. By default, all records up to the maximum are returned. Use the 'fields' parameters to limit properties returned for each record. By default, all fields are returned for each record.

<h3 id="retrieve-one-or-more-tables.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<TableSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <plural>string</plural>
    <primary_key>string</primary_key>
    <name_field>string</name_field>
    <field/>
    <related/>
  </resource>
</TableSchemas>
```

<h3 id="retrieve-one-or-more-tables.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|TableSchemas|[TableSchemas](#schematableschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one or more records.

<a id="opIdgetAnalyticsTableRecords"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_table/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_table/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_table/analytics`

Set the **filter** parameter to a SQL WHERE clause (optional native filter accepted in some scenarios) to limit records returned or leave it blank to return all records up to the maximum limit. Set the **limit** parameter with or without a filter to return a specific amount of records. Use the **offset** parameter along with the **limit** parameter to page through sets of records. Set the **order** parameter to SQL ORDER_BY clause containing field and optional direction (field_name [ASC|DESC]) to order the returned records. Alternatively, to send the **filter** with or without **params** as posted data, use the getRecordsByPost() POST request and post a filter with or without params.Pass the identifying field values as a comma-separated list in the **ids** parameter. Use the **id_field** and **id_type** parameters to override or specify detail for identifying fields where applicable. Alternatively, to send the **ids** as posted data, use the getRecordsByPost() POST request. Use the **fields** parameter to limit properties returned for each record. By default, all fields are returned for all records. 

<h3 id="retrieve-one-or-more-records.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|filter|query|string|false|SQL-like filter to limit the records to retrieve.|
|limit|query|integer(int32)|false|Set to limit the filter results.|
|offset|query|integer(int32)|false|Set to offset the filter results to a particular record count.|
|order|query|string|false|SQL-like order containing field and direction for filter results.|
|group|query|string|false|Comma-delimited list of the fields used for grouping of filter results.|
|count_only|query|boolean|false|Return only the total number of filter results.|
|include_count|query|boolean|false|Include the total number of filter results in returned metadata.|
|include_schema|query|boolean|false|Include the schema of the table queried in returned metadata.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|continue|query|boolean|false|In batch scenarios where supported, continue processing even after one action fails. Default behavior is to halt and return results up to the first point of failure.|
|rollback|query|boolean|false|In batch scenarios where supported, rollback all actions if one action fails. Default behavior is to halt and return results up to the first point of failure.|
|file|query|string|false|Download the results of the request as a file. **This is here for documentation purpose only. File will not download using API Docs.**|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsResponse>
  <resource>
    <id>0</id>
  </resource>
  <meta>
    <schema>string</schema>
    <count>0</count>
  </meta>
</RecordsResponse>
```

<h3 id="retrieve-one-or-more-records.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Records Response|[RecordsResponse](#schemarecordsresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Create one or more records.

<a id="opIdcreateAnalyticsTableRecords"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'X-HTTP-METHOD':'GET'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'X-HTTP-METHOD': 'GET'
}

r = requests.post('/api/v2/analytics/_table/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    'X-HTTP-METHOD' => 'GET',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_table/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_table/analytics`

Posted data should be an array of records wrapped in a **record** element. By default, only the id property of the record is returned on success. Use **fields** parameter to return more info.

> Body parameter

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "ids": [
    0
  ],
  "filter": "string",
  "params": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsRequest>
  <resource>
    <id>0</id>
  </resource>
  <ids>0</ids>
  <filter>string</filter>
  <params>string</params>
</RecordsRequest>
```

<h3 id="create-one-or-more-records.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|continue|query|boolean|false|In batch scenarios where supported, continue processing even after one action fails. Default behavior is to halt and return results up to the first point of failure.|
|rollback|query|boolean|false|In batch scenarios where supported, rollback all actions if one action fails. Default behavior is to halt and return results up to the first point of failure.|
|X-HTTP-METHOD|header|string|false|Override request using POST to tunnel other http request, such as DELETE or GET passing a payload.|
|body|body|[RecordsRequest](#schemarecordsrequest)|false|Records Request|
|table_name|path|string|true|Name of the table to perform operations on.|

#### Enumerated Values

|Parameter|Value|
|---|---|
|X-HTTP-METHOD|GET|
|X-HTTP-METHOD|PUT|
|X-HTTP-METHOD|PATCH|
|X-HTTP-METHOD|DELETE|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsResponse>
  <resource>
    <id>0</id>
  </resource>
  <meta>
    <schema>string</schema>
    <count>0</count>
  </meta>
</RecordsResponse>
```

<h3 id="create-one-or-more-records.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Records Response|[RecordsResponse](#schemarecordsresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (replace) one or more records.

<a id="opIdreplaceAnalyticsTableRecords"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_table/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_table/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_table/analytics`

Post data should be an array of records wrapped in a **resource** tag. If ids or filter is used, posted body should be a single record with name-value pairs to update, wrapped in a **resource** tag. Ids can be included via URL parameter or included in the posted body. Filter can be included via URL parameter or included in the posted body. By default, only the id property of the record is returned on success. Use **fields** parameter to return more info.

> Body parameter

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "ids": [
    0
  ],
  "filter": "string",
  "params": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsRequest>
  <resource>
    <id>0</id>
  </resource>
  <ids>0</ids>
  <filter>string</filter>
  <params>string</params>
</RecordsRequest>
```

<h3 id="update-(replace)-one-or-more-records.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|continue|query|boolean|false|In batch scenarios where supported, continue processing even after one action fails. Default behavior is to halt and return results up to the first point of failure.|
|rollback|query|boolean|false|In batch scenarios where supported, rollback all actions if one action fails. Default behavior is to halt and return results up to the first point of failure.|
|filter|query|string|false|SQL-like filter to limit the records to retrieve.|
|body|body|[RecordsRequest](#schemarecordsrequest)|false|Records Request|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsResponse>
  <resource>
    <id>0</id>
  </resource>
  <meta>
    <schema>string</schema>
    <count>0</count>
  </meta>
</RecordsResponse>
```

<h3 id="update-(replace)-one-or-more-records.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Records Response|[RecordsResponse](#schemarecordsresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (patch) one or more records.

<a id="opIdupdateAnalyticsTableRecords"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_table/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_table/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_table/analytics`

Post data should be an array of records containing at least the identifying fields for each record. Posted body should be a single record with name-value pairs to update wrapped in a **record** tag. Ids can be included via URL parameter or included in the posted body. Filter can be included via URL parameter or included in the posted body. By default, only the id property of the record is returned on success. Use **fields** parameter to return more info.

> Body parameter

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "ids": [
    0
  ],
  "filter": "string",
  "params": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsRequest>
  <resource>
    <id>0</id>
  </resource>
  <ids>0</ids>
  <filter>string</filter>
  <params>string</params>
</RecordsRequest>
```

<h3 id="update-(patch)-one-or-more-records.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|continue|query|boolean|false|In batch scenarios where supported, continue processing even after one action fails. Default behavior is to halt and return results up to the first point of failure.|
|rollback|query|boolean|false|In batch scenarios where supported, rollback all actions if one action fails. Default behavior is to halt and return results up to the first point of failure.|
|filter|query|string|false|SQL-like filter to limit the records to retrieve.|
|body|body|[RecordsRequest](#schemarecordsrequest)|false|Records Request|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsResponse>
  <resource>
    <id>0</id>
  </resource>
  <meta>
    <schema>string</schema>
    <count>0</count>
  </meta>
</RecordsResponse>
```

<h3 id="update-(patch)-one-or-more-records.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Records Response|[RecordsResponse](#schemarecordsresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Delete one or more records.

<a id="opIddeleteAnalyticsTableRecords"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_table/analytics', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_table/analytics', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_table/analytics`

Set the **ids** parameter to a list of record identifying (primary key) values to delete specific records. Alternatively, to delete records by a large list of ids, pass the ids in the **body**. By default, only the id property of the record is returned on success, use **fields** to return more info. Set the **filter** parameter to a SQL WHERE clause to delete specific records, otherwise set **force** to true to clear the table. Alternatively, to delete by a complicated filter or to use parameter replacement, pass the filter with or without params as the **body**. By default, only the id property of the record is returned on success, use **fields** to return more info. Set the **body** to an array of records, minimally including the identifying fields, to delete specific records. By default, only the id property of the record is returned on success, use **fields** to return more info. 

> Body parameter

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "ids": [
    0
  ],
  "filter": "string",
  "params": [
    "string"
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsRequest>
  <resource>
    <id>0</id>
  </resource>
  <ids>0</ids>
  <filter>string</filter>
  <params>string</params>
</RecordsRequest>
```

<h3 id="delete-one-or-more-records.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|continue|query|boolean|false|In batch scenarios where supported, continue processing even after one action fails. Default behavior is to halt and return results up to the first point of failure.|
|rollback|query|boolean|false|In batch scenarios where supported, rollback all actions if one action fails. Default behavior is to halt and return results up to the first point of failure.|
|filter|query|string|false|SQL-like filter to limit the records to retrieve.|
|force|query|boolean|false|Set to true to delete all resources in the given table, folder, etc.|
|body|body|[RecordsRequest](#schemarecordsrequest)|false|Records Request|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordsResponse>
  <resource>
    <id>0</id>
  </resource>
  <meta>
    <schema>string</schema>
    <count>0</count>
  </meta>
</RecordsResponse>
```

<h3 id="delete-one-or-more-records.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Records Response|[RecordsResponse](#schemarecordsresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one record by identifier.

<a id="opIdgetAnalyticsTableRecord"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_table/analytics/{id}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_table/analytics/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_table/analytics/{id}`

Use the **fields** parameter to limit properties that are returned. By default, all fields are returned.

<h3 id="retrieve-one-record-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|id|path|string|true|Identifier of the record to retrieve.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordResponse>
  <id>0</id>
</RecordResponse>
```

<h3 id="retrieve-one-record-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Record Response|[RecordResponse](#schemarecordresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Replace the content of one record by identifier.

<a id="opIdreplaceAnalyticsTableRecord"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('/api/v2/analytics/_table/analytics/{id}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','/api/v2/analytics/_table/analytics/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PUT /_table/analytics/{id}`

Post data should be an array of fields for a single record. Use the **fields** parameter to return more properties. By default, the id is returned.

> Body parameter

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordRequest>
  <id>0</id>
</RecordRequest>
```

<h3 id="replace-the-content-of-one-record-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|body|body|[RecordRequest](#schemarecordrequest)|false|Record Request|
|id|path|string|true|Identifier of the record to retrieve.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordResponse>
  <id>0</id>
</RecordResponse>
```

<h3 id="replace-the-content-of-one-record-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Record Response|[RecordResponse](#schemarecordresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Update (patch) one record by identifier.

<a id="opIdupdateAnalyticsTableRecord"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics/{id}',
  method: 'patch',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('/api/v2/analytics/_table/analytics/{id}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','/api/v2/analytics/_table/analytics/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`PATCH /_table/analytics/{id}`

Post data should be an array of fields for a single record. Use the **fields** parameter to return more properties. By default, the id is returned.

> Body parameter

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordRequest>
  <id>0</id>
</RecordRequest>
```

<h3 id="update-(patch)-one-record-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|body|body|[RecordRequest](#schemarecordrequest)|false|Record Request|
|id|path|string|true|Identifier of the record to retrieve.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordResponse>
  <id>0</id>
</RecordResponse>
```

<h3 id="update-(patch)-one-record-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Record Response|[RecordResponse](#schemarecordresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Delete one record by identifier.

<a id="opIddeleteAnalyticsTableRecord"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_table/analytics/{id}',
  method: 'delete',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/api/v2/analytics/_table/analytics/{id}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','/api/v2/analytics/_table/analytics/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`DELETE /_table/analytics/{id}`

Use the **fields** parameter to return more deleted properties. By default, the id is returned.

<h3 id="delete-one-record-by-identifier.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|related|query|array[string]|false|Comma-delimited list of related names to retrieve for each resource.|
|id_field|query|array[string]|false|Comma-delimited list of the fields used as identifiers, used to override defaults or provide identifiers when none are provisioned.|
|id_type|query|array[string]|false|Comma-delimited list of the field types used as identifiers for the table, used to override defaults or provide identifiers when none are provisioned.|
|id|path|string|true|Identifier of the record to retrieve.|
|table_name|path|string|true|Name of the table to perform operations on.|

> Example responses

> 200 Response

```json
{
  "id": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<RecordResponse>
  <id>0</id>
</RecordResponse>
```

<h3 id="delete-one-record-by-identifier.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Record Response|[RecordResponse](#schemarecordresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one or more StoredProcedures.

<a id="opIdgetAnalyticsStoredProcedures"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_proc',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_proc', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_proc', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_proc`

Use the 'ids' parameter to limit records that are returned. By default, all records up to the maximum are returned. Use the 'fields' parameters to limit properties returned for each record. By default, all fields are returned for each record.

<h3 id="retrieve-one-or-more-storedprocedures.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "return_type": "string",
      "return_schema": "string",
      "params": [
        {
          "name": "string",
          "position": "string",
          "param_type": "string",
          "type": "string",
          "db_type": "string",
          "length": 0,
          "precision": 0,
          "scale": 0,
          "default": "string"
        }
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredRoutineSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <return_type>string</return_type>
    <return_schema>string</return_schema>
    <params>
      <name>string</name>
      <position>string</position>
      <param_type>string</param_type>
      <type>string</type>
      <db_type>string</db_type>
      <length>0</length>
      <precision>0</precision>
      <scale>0</scale>
      <default>string</default>
    </params>
  </resource>
</StoredRoutineSchemas>
```

<h3 id="retrieve-one-or-more-storedprocedures.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored Procedure Schemas|[StoredRoutineSchemas](#schemastoredroutineschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Call a stored procedure.

<a id="opIdcallAnalyticsStoredProcedureWithParams"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_proc/{procedure_name}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_proc/{procedure_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_proc/{procedure_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_proc/{procedure_name}`

Call a stored procedure with parameters. Set an optional wrapper and schema for the returned data set. 

> Body parameter

```json
{
  "params": [
    {
      "name": "string",
      "value": "string"
    }
  ],
  "schema": {
    "_field_name_": "string"
  },
  "wrapper": "string",
  "returns": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredProcedureRequest>
  <params>
    <name>string</name>
    <value>string</value>
  </params>
  <schema>
    <_field_name_>string</_field_name_>
  </schema>
  <wrapper>string</wrapper>
  <returns>string</returns>
</StoredProcedureRequest>
```

<h3 id="call-a-stored-procedure.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StoredProcedureRequest](#schemastoredprocedurerequest)|false|Stored Procedure Request|
|procedure_name|path|string|true|Name of the stored procedure to call.|
|wrapper|query|string|false|Add this wrapper around the expected data set before returning.|
|returns|query|string|false|If returning a single value, use this to set the type of that value.|

> Example responses

> 200 Response

```json
{
  "_wrapper_if_supplied_": [
    "string"
  ],
  "_out_param_name_": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredProcedureResponse>
  <_wrapper_if_supplied_>string</_wrapper_if_supplied_>
  <_out_param_name_>string</_out_param_name_>
</StoredProcedureResponse>
```

<h3 id="call-a-stored-procedure.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored Procedure Response|[StoredProcedureResponse](#schemastoredprocedureresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Retrieve one or more StoredFunctions.

<a id="opIdgetAnalyticsStoredFunctions"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_func',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_func', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_func', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_func`

Use the 'ids' parameter to limit records that are returned. By default, all records up to the maximum are returned. Use the 'fields' parameters to limit properties returned for each record. By default, all fields are returned for each record.

<h3 id="retrieve-one-or-more-storedfunctions.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|fields|query|array[string]|false|Comma-delimited list of properties to be returned for each resource, "*" returns all properties. If as_list, use this to override the default identifier.|
|ids|query|array[integer]|false|Comma-delimited list of the identifiers of the records to retrieve.|

> Example responses

> 200 Response

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "return_type": "string",
      "return_schema": "string",
      "params": [
        {
          "name": "string",
          "position": "string",
          "param_type": "string",
          "type": "string",
          "db_type": "string",
          "length": 0,
          "precision": 0,
          "scale": 0,
          "default": "string"
        }
      ]
    }
  ]
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredRoutineSchemas>
  <resource>
    <name>string</name>
    <label>string</label>
    <description>string</description>
    <return_type>string</return_type>
    <return_schema>string</return_schema>
    <params>
      <name>string</name>
      <position>string</position>
      <param_type>string</param_type>
      <type>string</type>
      <db_type>string</db_type>
      <length>0</length>
      <precision>0</precision>
      <scale>0</scale>
      <default>string</default>
    </params>
  </resource>
</StoredRoutineSchemas>
```

<h3 id="retrieve-one-or-more-storedfunctions.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored Function Schemas|[StoredRoutineSchemas](#schemastoredroutineschemas)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Call a stored function.

<a id="opIdcallAnalyticsStoredFunction"></a>

> Code samples

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_func/{function_name}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/api/v2/analytics/_func/{function_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','/api/v2/analytics/_func/{function_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`GET /_func/{function_name}`

Call a stored function with no parameters. 

<h3 id="call-a-stored-function.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|function_name|path|string|true|Name of the stored function to call.|
|returns|query|string|false|If returning a single value, use this to set the type of that value.|

> Example responses

> 200 Response

```json
{
  "_out_param_name_": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredFunctionResponse>
  <_out_param_name_>string</_out_param_name_>
</StoredFunctionResponse>
```

<h3 id="call-a-stored-function.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored Function Response|[StoredFunctionResponse](#schemastoredfunctionresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

## Call a stored function with parameters.

<a id="opIdcallAnalyticsStoredFunctionWithParams"></a>

> Code samples

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/api/v2/analytics/_func/{function_name}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/api/v2/analytics/_func/{function_name}', params={

}, headers = headers)

print r.json()

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
    
    );

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','/api/v2/analytics/_func/{function_name}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

`POST /_func/{function_name}`

Call a stored function with parameters. 

> Body parameter

```json
{
  "params": [
    {
      "name": "string",
      "value": "string"
    }
  ],
  "schema": {
    "_field_name_": "string"
  },
  "returns": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredFunctionRequest>
  <params>
    <name>string</name>
    <value>string</value>
  </params>
  <schema>
    <_field_name_>string</_field_name_>
  </schema>
  <returns>string</returns>
</StoredFunctionRequest>
```

<h3 id="call-a-stored-function-with-parameters.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[StoredFunctionRequest](#schemastoredfunctionrequest)|false|Stored Function Request|
|function_name|path|string|true|Name of the stored function to call.|
|returns|query|string|false|If returning a single value, use this to set the type of that value.|

> Example responses

> 200 Response

```json
{
  "_out_param_name_": "string"
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<StoredFunctionResponse>
  <_out_param_name_>string</_out_param_name_>
</StoredFunctionResponse>
```

<h3 id="call-a-stored-function-with-parameters.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Stored Function Response|[StoredFunctionResponse](#schemastoredfunctionresponse)|
|default|Default|Error Response|[Error](#schemaerror)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
BasicAuth, BearerAuth, ApiKeyQuery, ApiKeyHeader, SessionTokenQuery, SessionTokenHeader
</aside>

# Schemas

<h2 id="tocSsuccess">Success</h2>

<a id="schemasuccess"></a>

```json
{
  "success": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|True when API call was successful, false or error otherwise.|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "code": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|false|none|Error code.|
|message|string|false|none|String description of the error.|

<h2 id="tocSresourcelist">ResourceList</h2>

<a id="schemaresourcelist"></a>

```json
{
  "resource": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[string]|false|none|Array of accessible resources available to this service.|

<h2 id="tocSredshiftdb">RedshiftDb</h2>

<a id="schemaredshiftdb"></a>

```json
{
  "name": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Identifier of the resource.|

<h2 id="tocSredshiftdbs">RedshiftDbs</h2>

<a id="schemaredshiftdbs"></a>

```json
{
  "resource": [
    {
      "name": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[RedshiftDb](#schemaredshiftdb)]|false|none|Array of resources available to this service.|

<h2 id="tocStableschemas">TableSchemas</h2>

<a id="schematableschemas"></a>

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "plural": "string",
      "primary_key": [
        "string"
      ],
      "name_field": "string",
      "field": [
        null
      ],
      "related": [
        null
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[TableSchema](#schematableschema)]|false|none|An array of table definitions.|

<h2 id="tocStableschema">TableSchema</h2>

<a id="schematableschema"></a>

```json
{
  "name": "string",
  "label": "string",
  "description": "string",
  "plural": "string",
  "primary_key": [
    "string"
  ],
  "name_field": "string",
  "field": [
    null
  ],
  "related": [
    null
  ]
}

```

*The database table schema.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Identifier/Name for the table.|
|label|string|false|none|Displayable singular name for the table.|
|description|string|false|none|Description of the table.|
|plural|string|false|none|Displayable plural name for the table.|
|primary_key|[string]|false|none|Field(s), if any, that represent the primary key of each record.|
|name_field|string|false|none|Field(s), if any, that represent the name of each record.|
|field|[db_schema_table_field]|false|none|An array of available fields in this table.|
|related|[db_schema_table_relation]|false|none|An array of available relationships to other tables.|

<h2 id="tocSfieldschemas">FieldSchemas</h2>

<a id="schemafieldschemas"></a>

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default_value": "string",
      "required": true,
      "allow_null": true,
      "fixed_length": true,
      "supports_multibyte": true,
      "auto_increment": true,
      "is_primary_key": true,
      "is_foreign_key": true,
      "ref_table": "string",
      "ref_field": "string",
      "validation": [
        "string"
      ],
      "value": [
        "string"
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[FieldSchema](#schemafieldschema)]|false|none|An array of field definitions.|

<h2 id="tocSfieldschema">FieldSchema</h2>

<a id="schemafieldschema"></a>

```json
{
  "name": "string",
  "label": "string",
  "type": "string",
  "db_type": "string",
  "length": 0,
  "precision": 0,
  "scale": 0,
  "default_value": "string",
  "required": true,
  "allow_null": true,
  "fixed_length": true,
  "supports_multibyte": true,
  "auto_increment": true,
  "is_primary_key": true,
  "is_foreign_key": true,
  "ref_table": "string",
  "ref_field": "string",
  "validation": [
    "string"
  ],
  "value": [
    "string"
  ]
}

```

*The database table field schema.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|The API name of the field.|
|label|string|false|none|The displayable label for the field.|
|type|string|false|none|The DreamFactory abstract data type for this field.|
|db_type|string|false|none|The native database type used for this field.|
|length|integer(int32)|false|none|The maximum length allowed (in characters for string, displayed for numbers).|
|precision|integer(int32)|false|none|Total number of places for numbers.|
|scale|integer(int32)|false|none|Number of decimal places allowed for numbers.|
|default_value|string|false|none|Default value for this field.|
|required|boolean|false|none|Is a value required for record creation.|
|allow_null|boolean|false|none|Is null allowed as a value.|
|fixed_length|boolean|false|none|Is the length fixed (not variable).|
|supports_multibyte|boolean|false|none|Does the data type support multibyte characters.|
|auto_increment|boolean|false|none|Does the integer field value increment upon new record creation.|
|is_primary_key|boolean|false|none|Is this field used as/part of the primary key.|
|is_foreign_key|boolean|false|none|Is this field used as a foreign key.|
|ref_table|string|false|none|For foreign keys, the referenced table name.|
|ref_field|string|false|none|For foreign keys, the referenced table field name.|
|validation|[string]|false|none|validations to be performed on this field.|
|value|[string]|false|none|Selectable string values for client menus and picklist validation.|

<h2 id="tocSrelationshipschemas">RelationshipSchemas</h2>

<a id="schemarelationshipschemas"></a>

```json
{
  "resource": [
    {
      "name": "string",
      "alias": "string",
      "label": "string",
      "description": "string",
      "type": "string",
      "field": "string",
      "ref_table": "string",
      "ref_field": "string",
      "junction_table": "string",
      "junction_field": "string",
      "junction_ref_field": "string",
      "always_fetch": true
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[RelationshipSchema](#schemarelationshipschema)]|false|none|An array of relationship definitions.|

<h2 id="tocSrelationshipschema">RelationshipSchema</h2>

<a id="schemarelationshipschema"></a>

```json
{
  "name": "string",
  "alias": "string",
  "label": "string",
  "description": "string",
  "type": "string",
  "field": "string",
  "ref_table": "string",
  "ref_field": "string",
  "junction_table": "string",
  "junction_field": "string",
  "junction_ref_field": "string",
  "always_fetch": true
}

```

*The database table relation schema.*

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Name of the relationship.|
|alias|string|false|none|Alias to use in the API to override the name the relationship.|
|label|string|false|none|Label for the relationship.|
|description|string|false|none|Description of the relationship.|
|type|string|false|none|Relationship type - belongs_to, has_many, many_many.|
|field|string|false|none|The current table field that is used in the relationship.|
|ref_table|string|false|none|The table name that is referenced by the relationship.|
|ref_field|string|false|none|The field name that is referenced by the relationship.|
|junction_table|string|false|none|The intermediate junction table used for many_many relationships.|
|junction_field|string|false|none|The intermediate junction table field used for many_many relationships.|
|junction_ref_field|string|false|none|The intermediate joining table referencing field used for many_many relationships.|
|always_fetch|boolean|false|none|Always fetch this relationship when querying the parent table.|

<h2 id="tocSstoredroutineschemas">StoredRoutineSchemas</h2>

<a id="schemastoredroutineschemas"></a>

```json
{
  "resource": [
    {
      "name": "string",
      "label": "string",
      "description": "string",
      "return_type": "string",
      "return_schema": "string",
      "params": [
        {
          "name": "string",
          "position": "string",
          "param_type": "string",
          "type": "string",
          "db_type": "string",
          "length": 0,
          "precision": 0,
          "scale": 0,
          "default": "string"
        }
      ]
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[StoredRoutineSchema](#schemastoredroutineschema)]|false|none|An array of routine definitions.|

<h2 id="tocSstoredroutineschema">StoredRoutineSchema</h2>

<a id="schemastoredroutineschema"></a>

```json
{
  "name": "string",
  "label": "string",
  "description": "string",
  "return_type": "string",
  "return_schema": "string",
  "params": [
    {
      "name": "string",
      "position": "string",
      "param_type": "string",
      "type": "string",
      "db_type": "string",
      "length": 0,
      "precision": 0,
      "scale": 0,
      "default": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Identifier/Name for the routine.|
|label|string|false|none|Displayable name for the routine.|
|description|string|false|none|Description for the routine.|
|return_type|string|false|none|Displayable plural name for the routine.|
|return_schema|string|false|none|Field(s), if any, that represent the primary key of each record.|
|params|[[StoredRoutineParameterSchema](#schemastoredroutineparameterschema)]|false|none|An array of available fields in each record.|

<h2 id="tocSstoredroutineparameterschema">StoredRoutineParameterSchema</h2>

<a id="schemastoredroutineparameterschema"></a>

```json
{
  "name": "string",
  "position": "string",
  "param_type": "string",
  "type": "string",
  "db_type": "string",
  "length": 0,
  "precision": 0,
  "scale": 0,
  "default": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Identifier/Name for the parameter.|
|position|string|false|none|Displayable singular name for the parameter.|
|param_type|string|false|none|Displayable plural name for the parameter.|
|type|string|false|none|The DreamFactory abstract data type for this parameter.|
|db_type|string|false|none|The native database type used for this parameter.|
|length|integer(int32)|false|none|The maximum length allowed (in characters for string, displayed for numbers).|
|precision|integer(int32)|false|none|Total number of places for numbers.|
|scale|integer(int32)|false|none|Number of decimal places allowed for numbers.|
|default|string|false|none|Default value for this parameter.|

<h2 id="tocSrecordrequest">RecordRequest</h2>

<a id="schemarecordrequest"></a>

```json
{
  "id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int32)|false|none|Sample identifier of this record.|

<h2 id="tocSrecordsrequest">RecordsRequest</h2>

<a id="schemarecordsrequest"></a>

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "ids": [
    0
  ],
  "filter": "string",
  "params": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[RecordRequest](#schemarecordrequest)]|false|none|Array of records.|
|ids|[integer]|false|none|Array of record identifiers.|
|filter|string|false|none|SQL or native filter to determine records where modifications will be applied.|
|params|[string]|false|none|Array of name-value pairs, used for parameter replacement on filters.|

<h2 id="tocSrecordresponse">RecordResponse</h2>

<a id="schemarecordresponse"></a>

```json
{
  "id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int32)|false|none|Sample identifier of this record.|

<h2 id="tocSrecordsresponse">RecordsResponse</h2>

<a id="schemarecordsresponse"></a>

```json
{
  "resource": [
    {
      "id": 0
    }
  ],
  "meta": {
    "schema": [
      "string"
    ],
    "count": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|resource|[[RecordResponse](#schemarecordresponse)]|false|none|Array of system user records.|
|meta|[Metadata](#schemametadata)|false|none|none|

<h2 id="tocSmetadata">Metadata</h2>

<a id="schemametadata"></a>

```json
{
  "schema": [
    "string"
  ],
  "count": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|schema|[string]|false|none|Array of table schema.|
|count|integer(int32)|false|none|Record count returned for GET requests.|

<h2 id="tocSstoredprocedureresponse">StoredProcedureResponse</h2>

<a id="schemastoredprocedureresponse"></a>

```json
{
  "_wrapper_if_supplied_": [
    "string"
  ],
  "_out_param_name_": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_wrapper_if_supplied_|[string]|false|none|Array of returned data.|
|_out_param_name_|string|false|none|Name and value of any given output parameter.|

<h2 id="tocSstoredprocedurerequest">StoredProcedureRequest</h2>

<a id="schemastoredprocedurerequest"></a>

```json
{
  "params": [
    {
      "name": "string",
      "value": "string"
    }
  ],
  "schema": {
    "_field_name_": "string"
  },
  "wrapper": "string",
  "returns": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|params|[[StoredProcedureParam](#schemastoredprocedureparam)]|false|none|Optional array of input and output parameters.|
|schema|[StoredProcedureResultSchema](#schemastoredprocedureresultschema)|false|none|none|
|wrapper|string|false|none|Add this wrapper around the expected data set before returning, same as URL parameter.|
|returns|string|false|none|If returning a single value, use this to set the type of that value, same as URL parameter.|

<h2 id="tocSstoredprocedureparam">StoredProcedureParam</h2>

<a id="schemastoredprocedureparam"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Name of the parameter, required for OUT and INOUT types, must be the same as the stored procedure's parameter name.|
|value|string|false|none|Value of the parameter, used for the IN and INOUT types, defaults to NULL.|

<h2 id="tocSstoredprocedureresultschema">StoredProcedureResultSchema</h2>

<a id="schemastoredprocedureresultschema"></a>

```json
{
  "_field_name_": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_field_name_|string|false|none|The name of the returned element where the value is set to the requested type for the returned value, i.e. integer, boolean, string, etc.|

<h2 id="tocSstoredfunctionresponse">StoredFunctionResponse</h2>

<a id="schemastoredfunctionresponse"></a>

```json
{
  "_out_param_name_": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_out_param_name_|string|false|none|Name and value of any given output parameter.|

<h2 id="tocSstoredfunctionrequest">StoredFunctionRequest</h2>

<a id="schemastoredfunctionrequest"></a>

```json
{
  "params": [
    {
      "name": "string",
      "value": "string"
    }
  ],
  "schema": {
    "_field_name_": "string"
  },
  "returns": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|params|[[StoredFunctionParam](#schemastoredfunctionparam)]|false|none|Optional array of input and output parameters.|
|schema|[StoredFunctionResultSchema](#schemastoredfunctionresultschema)|false|none|none|
|returns|string|false|none|If returning a single value, use this to set the type of that value, same as URL parameter.|

<h2 id="tocSstoredfunctionparam">StoredFunctionParam</h2>

<a id="schemastoredfunctionparam"></a>

```json
{
  "name": "string",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|none|Name of the parameter, required for OUT and INOUT types, must be the same as the stored procedure's parameter name.|
|value|string|false|none|Value of the parameter, used for the IN and INOUT types, defaults to NULL.|

<h2 id="tocSstoredfunctionresultschema">StoredFunctionResultSchema</h2>

<a id="schemastoredfunctionresultschema"></a>

```json
{
  "_field_name_": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|_field_name_|string|false|none|The name of the returned element where the value is set to the requested type for the returned value, i.e. integer, boolean, string, etc.|

