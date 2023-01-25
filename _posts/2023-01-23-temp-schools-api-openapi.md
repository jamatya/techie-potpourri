---
title: Temp Schools API - OpenAPI 3.0
language_tabs:
  - python: Python
  - ruby: Ruby
  - javascript: Javascript
toc_footers: []
includes: []
search: true
date: 2023-01-23 12:30:00
categories: [api-testing]
tags: [api-testing]
author: jamatya
version: v1.0
---
> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is a temporary API that contains mock data related to QS, hosted on Azure

Base URLs:

* <a href="http://test.azure-api.net/qs-api">http://test.azure-api.net/qs-api</a>

* <a href="https://test.azure-api.net/qs-api">https://test.azure-api.net/qs-api</a>

<a href="http://swagger.io/terms/">Terms of service</a>

License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

* API Key (apiKeyHeader)
    - Parameter Name: **Ocp-Apim-Subscription-Key**, in: header. 

* API Key (apiKeyQuery)
    - Parameter Name: **subscription-key**, in: query. 

<h1 id="qed-temp-schools-api-openapi-3-0-school">school</h1>

Operations related to schools

<a href="http://swagger.io/">Find out more</a>

## getAllSchools

<a id="opIdgetAllSchools"></a>

`GET /schools/`

*Get all schools*

Returns a list of schools. For more information, click on https://jamatya.github.io/.

> Example responses

> 200 Response

```json
{
  "id": 1,
  "name": "Sherwood State School",
  "type": "Public",
  "ranking": 3
}
```

<h3 id="getallschools-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[School](#schemaschool)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Schools not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyHeader, apiKeyQuery
</aside>

## getSchoolById

<a id="opIdgetSchoolById"></a>

`GET /schools/{id}`

*Find school by ID*

Returns a single school

<h3 id="getschoolbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer(int64)|true|Format - int64. ID of the school to return|

> Example responses

> 200 Response

```json
{
  "id": 1,
  "name": "Sherwood State School",
  "type": "Public",
  "ranking": 3
}
```

<h3 id="getschoolbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[School](#schemaschool)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|School not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
apiKeyHeader, apiKeyQuery
</aside>

# Schemas

<h2 id="tocS_School">School</h2>
<!-- backwards compatibility -->
<a id="schemaschool"></a>
<a id="schema_School"></a>
<a id="tocSschool"></a>
<a id="tocsschool"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": "1.0"
    },
    "name": {
      "type": "string",
      "example": "Sherwood State School"
    },
    "type": {
      "type": "string",
      "example": "Public"
    },
    "ranking": {
      "type": "integer",
      "format": "int64",
      "example": "3.0"
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|name|string|false|none|none|
|type|string|false|none|none|
|ranking|integer(int64)|false|none|none|
