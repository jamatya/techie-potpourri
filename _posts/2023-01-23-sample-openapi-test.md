---
title: Swagger Petstore - OpenAPI 3.0 v1.0.11
language_tabs:
  - python: Python
  - ruby: Ruby
toc_footers:
  - <a href="http://swagger.io">Find out more about Swagger</a>
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is a sample Pet Store Server based on the OpenAPI 3.0 specification.  You can find out more about
Swagger at [https://swagger.io](https://swagger.io). In the third iteration of the pet store, we've switched to the design first approach!
You can now help us improve the API whether it's by making changes to the definition itself or to the code.
That way, with time, we can improve the API in general, and expose some of the new features in OAS3.

_If you're looking for the Swagger 2.0/OAS 2.0 version of Petstore, then click [here](https://editor.swagger.io/?url=https://petstore.swagger.io/v2/swagger.yaml). Alternatively, you can load via the `Edit > Load Petstore OAS 2.0` menu option!_

Some useful links:
- [The Pet Store repository](https://github.com/swagger-api/swagger-petstore)
- [The source API definition for the Pet Store](https://github.com/swagger-api/swagger-petstore/blob/master/src/main/resources/openapi.yaml)

Base URLs:

* <a href="https://petstore3.swagger.io/api/v3">https://petstore3.swagger.io/api/v3</a>

<a href="http://swagger.io/terms/">Terms of service</a>
Email: <a href="mailto:apiteam@swagger.io">Support</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache 2.0</a>

# Authentication

- oAuth2 authentication. 

    - Flow: implicit
    - Authorization URL = [https://petstore3.swagger.io/oauth/authorize](https://petstore3.swagger.io/oauth/authorize)

|Scope|Scope Description|
|---|---|
|write:pets|modify pets in your account|
|read:pets|read your pets|

* API Key (api_key)
    - Parameter Name: **api_key**, in: header. 

<h1 id="swagger-petstore-openapi-3-0-pet">pet</h1>

Everything about your Pets

<a href="http://swagger.io">Find out more</a>

## updatePet

<a id="opIdupdatePet"></a>

`PUT /pet`

*Update an existing pet*

Update an existing pet by Id

> Body parameter

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}
```

```yaml
required:
  - name
  - photoUrls
type: object
properties:
  id:
    type: integer
    format: int64
    example: 10
  name:
    type: string
    example: doggie
  category:
    type: object
    properties:
      id:
        type: integer
        format: int64
        example: 1
      name:
        type: string
        example: Dogs
    xml:
      name: category
  photoUrls:
    type: array
    xml:
      wrapped: true
    items:
      type: string
      xml:
        name: photoUrl
  tags:
    type: array
    xml:
      wrapped: true
    items:
      type: object
      properties:
        id:
          type: integer
          format: int64
        name:
          type: string
      xml:
        name: tag
  status:
    type: string
    description: pet status in the store
    enum:
      - available
      - pending
      - sold
xml:
  name: pet

```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pet>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</pet>
```

<h3 id="updatepet-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pet](#schemapet)|true|Update an existent pet in the store|

> Example responses

> 200 Response

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pet>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</pet>
```

<h3 id="updatepet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Pet](#schemapet)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Pet not found|None|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Validation exception|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## addPet

<a id="opIdaddPet"></a>

`POST /pet`

*Add a new pet to the store*

Add a new pet to the store

> Body parameter

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}
```

```yaml
required:
  - name
  - photoUrls
type: object
properties:
  id:
    type: integer
    format: int64
    example: 10
  name:
    type: string
    example: doggie
  category:
    type: object
    properties:
      id:
        type: integer
        format: int64
        example: 1
      name:
        type: string
        example: Dogs
    xml:
      name: category
  photoUrls:
    type: array
    xml:
      wrapped: true
    items:
      type: string
      xml:
        name: photoUrl
  tags:
    type: array
    xml:
      wrapped: true
    items:
      type: object
      properties:
        id:
          type: integer
          format: int64
        name:
          type: string
      xml:
        name: tag
  status:
    type: string
    description: pet status in the store
    enum:
      - available
      - pending
      - sold
xml:
  name: pet

```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pet>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</pet>
```

<h3 id="addpet-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Pet](#schemapet)|true|Create a new pet in the store|

> Example responses

> 200 Response

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pet>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</pet>
```

<h3 id="addpet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[Pet](#schemapet)|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Invalid input|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## findPetsByStatus

<a id="opIdfindPetsByStatus"></a>

`GET /pet/findByStatus`

*Finds Pets by status*

Multiple status values can be provided with comma separated strings

<h3 id="findpetsbystatus-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|status|query|string|false|Status values that need to be considered for filter|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

> Example responses

> 200 Response

```json
{
  "type": "array",
  "items": {
    "required": [
      "name",
      "photoUrls"
    ],
    "type": "object",
    "properties": {
      "id": {
        "type": "integer",
        "format": "int64",
        "example": 10
      },
      "name": {
        "type": "string",
        "example": "doggie"
      },
      "category": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64",
            "example": 1
          },
          "name": {
            "type": "string",
            "example": "Dogs"
          }
        },
        "xml": {
          "name": "category"
        }
      },
      "photoUrls": {
        "type": "array",
        "xml": {
          "wrapped": true
        },
        "items": {
          "type": "string",
          "xml": {
            "name": "photoUrl"
          }
        }
      },
      "tags": {
        "type": "array",
        "xml": {
          "wrapped": true
        },
        "items": {
          "type": "object",
          "properties": {
            "id": {
              "type": "integer",
              "format": "int64"
            },
            "name": {
              "type": "string"
            }
          },
          "xml": {
            "name": "tag"
          }
        }
      },
      "status": {
        "type": "string",
        "description": "pet status in the store",
        "enum": [
          "available",
          "pending",
          "sold"
        ]
      }
    },
    "xml": {
      "name": "pet"
    }
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<type>array</type>
<items>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</items>
```

<h3 id="findpetsbystatus-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid status value|None|

<h3 id="findpetsbystatus-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pet](#schemapet)]|false|none|none|
|» id|integer(int64)|false|none|none|
|» name|string|true|none|none|
|» category|[Category](#schemacategory)|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» name|string|false|none|none|
|» photoUrls|[string]|true|none|none|
|» tags|[[Tag](#schematag)]|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» name|string|false|none|none|
|» status|string|false|none|pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## findPetsByTags

<a id="opIdfindPetsByTags"></a>

`GET /pet/findByTags`

*Finds Pets by tags*

Multiple tags can be provided with comma separated strings. Use tag1, tag2, tag3 for testing.

<h3 id="findpetsbytags-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|tags|query|array[string]|false|Tags to filter by|

> Example responses

> 200 Response

```json
{
  "type": "array",
  "items": {
    "required": [
      "name",
      "photoUrls"
    ],
    "type": "object",
    "properties": {
      "id": {
        "type": "integer",
        "format": "int64",
        "example": 10
      },
      "name": {
        "type": "string",
        "example": "doggie"
      },
      "category": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64",
            "example": 1
          },
          "name": {
            "type": "string",
            "example": "Dogs"
          }
        },
        "xml": {
          "name": "category"
        }
      },
      "photoUrls": {
        "type": "array",
        "xml": {
          "wrapped": true
        },
        "items": {
          "type": "string",
          "xml": {
            "name": "photoUrl"
          }
        }
      },
      "tags": {
        "type": "array",
        "xml": {
          "wrapped": true
        },
        "items": {
          "type": "object",
          "properties": {
            "id": {
              "type": "integer",
              "format": "int64"
            },
            "name": {
              "type": "string"
            }
          },
          "xml": {
            "name": "tag"
          }
        }
      },
      "status": {
        "type": "string",
        "description": "pet status in the store",
        "enum": [
          "available",
          "pending",
          "sold"
        ]
      }
    },
    "xml": {
      "name": "pet"
    }
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<type>array</type>
<items>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</items>
```

<h3 id="findpetsbytags-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid tag value|None|

<h3 id="findpetsbytags-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pet](#schemapet)]|false|none|none|
|» id|integer(int64)|false|none|none|
|» name|string|true|none|none|
|» category|[Category](#schemacategory)|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» name|string|false|none|none|
|» photoUrls|[string]|true|none|none|
|» tags|[[Tag](#schematag)]|false|none|none|
|»» id|integer(int64)|false|none|none|
|»» name|string|false|none|none|
|» status|string|false|none|pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## getPetById

<a id="opIdgetPetById"></a>

`GET /pet/{petId}`

*Find pet by ID*

Returns a single pet

<h3 id="getpetbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet to return|

> Example responses

> 200 Response

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<pet>
  <required>name</required>
  <required>photoUrls</required>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <name>
      <type>string</type>
      <example>doggie</example>
    </name>
    <category>
      <type>object</type>
      <properties>
        <id>
          <type>integer</type>
          <format>int64</format>
          <example>1</example>
        </id>
        <name>
          <type>string</type>
          <example>Dogs</example>
        </name>
      </properties>
      <xml>
        <name>category</name>
      </xml>
    </category>
    <photoUrls>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>string</type>
        <xml>
          <name>photoUrl</name>
        </xml>
      </items>
    </photoUrls>
    <tags>
      <type>array</type>
      <xml>
        <wrapped>true</wrapped>
      </xml>
      <items>
        <type>object</type>
        <properties>
          <id>
            <type>integer</type>
            <format>int64</format>
          </id>
          <name>
            <type>string</type>
          </name>
        </properties>
        <xml>
          <name>tag</name>
        </xml>
      </items>
    </tags>
    <status>
      <type>string</type>
      <description>pet status in the store</description>
      <enum>available</enum>
      <enum>pending</enum>
      <enum>sold</enum>
    </status>
  </properties>
  <xml>
    <name>pet</name>
  </xml>
</pet>
```

<h3 id="getpetbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Pet](#schemapet)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Pet not found|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key, petstore_auth ( Scopes: write:pets read:pets )
</aside>

## updatePetWithForm

<a id="opIdupdatePetWithForm"></a>

`POST /pet/{petId}`

*Updates a pet in the store with form data*

<h3 id="updatepetwithform-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet that needs to be updated|
|name|query|string|false|Name of pet that needs to be updated|
|status|query|string|false|Status of pet that needs to be updated|

<h3 id="updatepetwithform-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Invalid input|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## deletePet

<a id="opIddeletePet"></a>

`DELETE /pet/{petId}`

*Deletes a pet*

delete a pet

<h3 id="deletepet-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|api_key|header|string|false|none|
|petId|path|integer(int64)|true|Pet id to delete|

<h3 id="deletepet-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid pet value|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

## uploadFile

<a id="opIduploadFile"></a>

`POST /pet/{petId}/uploadImage`

*uploads an image*

> Body parameter

```yaml
type: string
format: binary

```

<h3 id="uploadfile-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|integer(int64)|true|ID of pet to update|
|additionalMetadata|query|string|false|Additional Metadata|
|body|body|string(binary)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "integer",
      "format": "int32"
    },
    "type": {
      "type": "string"
    },
    "message": {
      "type": "string"
    }
  },
  "xml": {
    "name": "##default"
  }
}
```

<h3 id="uploadfile-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[ApiResponse](#schemaapiresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
petstore_auth ( Scopes: write:pets read:pets )
</aside>

<h1 id="swagger-petstore-openapi-3-0-store">store</h1>

Access to Petstore orders

<a href="http://swagger.io">Find out more about our store</a>

## getInventory

<a id="opIdgetInventory"></a>

`GET /store/inventory`

*Returns pet inventories by status*

Returns a map of status codes to quantities

> Example responses

> 200 Response

```json
{
  "type": "object",
  "additionalProperties": {
    "type": "integer",
    "format": "int32"
  }
}
```

<h3 id="getinventory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="getinventory-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» **additionalProperties**|integer(int32)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
api_key
</aside>

## placeOrder

<a id="opIdplaceOrder"></a>

`POST /store/order`

*Place an order for a pet*

Place a new order in the store

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "petId": {
      "type": "integer",
      "format": "int64",
      "example": 198772
    },
    "quantity": {
      "type": "integer",
      "format": "int32",
      "example": 7
    },
    "shipDate": {
      "type": "string",
      "format": "date-time"
    },
    "status": {
      "type": "string",
      "description": "Order Status",
      "example": "approved",
      "enum": [
        "placed",
        "approved",
        "delivered"
      ]
    },
    "complete": {
      "type": "boolean"
    }
  },
  "xml": {
    "name": "order"
  }
}
```

```yaml
type: object
properties:
  id:
    type: integer
    format: int64
    example: 10
  petId:
    type: integer
    format: int64
    example: 198772
  quantity:
    type: integer
    format: int32
    example: 7
  shipDate:
    type: string
    format: date-time
  status:
    type: string
    description: Order Status
    example: approved
    enum:
      - placed
      - approved
      - delivered
  complete:
    type: boolean
xml:
  name: order

```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<order>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <petId>
      <type>integer</type>
      <format>int64</format>
      <example>198772</example>
    </petId>
    <quantity>
      <type>integer</type>
      <format>int32</format>
      <example>7</example>
    </quantity>
    <shipDate>
      <type>string</type>
      <format>date-time</format>
    </shipDate>
    <status>
      <type>string</type>
      <description>Order Status</description>
      <example>approved</example>
      <enum>placed</enum>
      <enum>approved</enum>
      <enum>delivered</enum>
    </status>
    <complete>
      <type>boolean</type>
    </complete>
  </properties>
  <xml>
    <name>order</name>
  </xml>
</order>
```

<h3 id="placeorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Order](#schemaorder)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "petId": {
      "type": "integer",
      "format": "int64",
      "example": 198772
    },
    "quantity": {
      "type": "integer",
      "format": "int32",
      "example": 7
    },
    "shipDate": {
      "type": "string",
      "format": "date-time"
    },
    "status": {
      "type": "string",
      "description": "Order Status",
      "example": "approved",
      "enum": [
        "placed",
        "approved",
        "delivered"
      ]
    },
    "complete": {
      "type": "boolean"
    }
  },
  "xml": {
    "name": "order"
  }
}
```

<h3 id="placeorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Order](#schemaorder)|
|405|[Method Not Allowed](https://tools.ietf.org/html/rfc7231#section-6.5.5)|Invalid input|None|

<aside class="success">
This operation does not require authentication
</aside>

## getOrderById

<a id="opIdgetOrderById"></a>

`GET /store/order/{orderId}`

*Find purchase order by ID*

For valid response try integer IDs with value <= 5 or > 10. Other values will generate exceptions.

<h3 id="getorderbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|integer(int64)|true|ID of order that needs to be fetched|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "petId": {
      "type": "integer",
      "format": "int64",
      "example": 198772
    },
    "quantity": {
      "type": "integer",
      "format": "int32",
      "example": 7
    },
    "shipDate": {
      "type": "string",
      "format": "date-time"
    },
    "status": {
      "type": "string",
      "description": "Order Status",
      "example": "approved",
      "enum": [
        "placed",
        "approved",
        "delivered"
      ]
    },
    "complete": {
      "type": "boolean"
    }
  },
  "xml": {
    "name": "order"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<order>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <petId>
      <type>integer</type>
      <format>int64</format>
      <example>198772</example>
    </petId>
    <quantity>
      <type>integer</type>
      <format>int32</format>
      <example>7</example>
    </quantity>
    <shipDate>
      <type>string</type>
      <format>date-time</format>
    </shipDate>
    <status>
      <type>string</type>
      <description>Order Status</description>
      <example>approved</example>
      <enum>placed</enum>
      <enum>approved</enum>
      <enum>delivered</enum>
    </status>
    <complete>
      <type>boolean</type>
    </complete>
  </properties>
  <xml>
    <name>order</name>
  </xml>
</order>
```

<h3 id="getorderbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Order](#schemaorder)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Order not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## deleteOrder

<a id="opIddeleteOrder"></a>

`DELETE /store/order/{orderId}`

*Delete purchase order by ID*

For valid response try integer IDs with value < 1000. Anything above 1000 or nonintegers will generate API errors

<h3 id="deleteorder-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|orderId|path|integer(int64)|true|ID of the order that needs to be deleted|

<h3 id="deleteorder-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid ID supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Order not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="swagger-petstore-openapi-3-0-user">user</h1>

Operations about user

## createUser

<a id="opIdcreateUser"></a>

`POST /user`

*Create user*

This can only be done by the logged in user.

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}
```

```yaml
type: object
properties:
  id:
    type: integer
    format: int64
    example: 10
  username:
    type: string
    example: theUser
  firstName:
    type: string
    example: John
  lastName:
    type: string
    example: James
  email:
    type: string
    example: john@email.com
  password:
    type: string
    example: "12345"
  phone:
    type: string
    example: "12345"
  userStatus:
    type: integer
    description: User Status
    format: int32
    example: 1
xml:
  name: user

```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <username>
      <type>string</type>
      <example>theUser</example>
    </username>
    <firstName>
      <type>string</type>
      <example>John</example>
    </firstName>
    <lastName>
      <type>string</type>
      <example>James</example>
    </lastName>
    <email>
      <type>string</type>
      <example>john@email.com</example>
    </email>
    <password>
      <type>string</type>
      <example>12345</example>
    </password>
    <phone>
      <type>string</type>
      <example>12345</example>
    </phone>
    <userStatus>
      <type>integer</type>
      <description>User Status</description>
      <format>int32</format>
      <example>1</example>
    </userStatus>
  </properties>
  <xml>
    <name>user</name>
  </xml>
</user>
```

<h3 id="createuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|false|Created user object|

> Example responses

> default Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <username>
      <type>string</type>
      <example>theUser</example>
    </username>
    <firstName>
      <type>string</type>
      <example>John</example>
    </firstName>
    <lastName>
      <type>string</type>
      <example>James</example>
    </lastName>
    <email>
      <type>string</type>
      <example>john@email.com</example>
    </email>
    <password>
      <type>string</type>
      <example>12345</example>
    </password>
    <phone>
      <type>string</type>
      <example>12345</example>
    </phone>
    <userStatus>
      <type>integer</type>
      <description>User Status</description>
      <format>int32</format>
      <example>1</example>
    </userStatus>
  </properties>
  <xml>
    <name>user</name>
  </xml>
</user>
```

<h3 id="createuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|[User](#schemauser)|

<aside class="success">
This operation does not require authentication
</aside>

## createUsersWithListInput

<a id="opIdcreateUsersWithListInput"></a>

`POST /user/createWithList`

*Creates list of users with given input array*

Creates list of users with given input array

> Body parameter

```json
{
  "type": "array",
  "items": {
    "type": "object",
    "properties": {
      "id": {
        "type": "integer",
        "format": "int64",
        "example": 10
      },
      "username": {
        "type": "string",
        "example": "theUser"
      },
      "firstName": {
        "type": "string",
        "example": "John"
      },
      "lastName": {
        "type": "string",
        "example": "James"
      },
      "email": {
        "type": "string",
        "example": "john@email.com"
      },
      "password": {
        "type": "string",
        "example": "12345"
      },
      "phone": {
        "type": "string",
        "example": "12345"
      },
      "userStatus": {
        "type": "integer",
        "description": "User Status",
        "format": "int32",
        "example": 1
      }
    },
    "xml": {
      "name": "user"
    }
  }
}
```

<h3 id="createuserswithlistinput-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[User](#schemauser)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <username>
      <type>string</type>
      <example>theUser</example>
    </username>
    <firstName>
      <type>string</type>
      <example>John</example>
    </firstName>
    <lastName>
      <type>string</type>
      <example>James</example>
    </lastName>
    <email>
      <type>string</type>
      <example>john@email.com</example>
    </email>
    <password>
      <type>string</type>
      <example>12345</example>
    </password>
    <phone>
      <type>string</type>
      <example>12345</example>
    </phone>
    <userStatus>
      <type>integer</type>
      <description>User Status</description>
      <format>int32</format>
      <example>1</example>
    </userStatus>
  </properties>
  <xml>
    <name>user</name>
  </xml>
</user>
```

<h3 id="createuserswithlistinput-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Successful operation|[User](#schemauser)|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## loginUser

<a id="opIdloginUser"></a>

`GET /user/login`

*Logs user into the system*

<h3 id="loginuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|query|string|false|The user name for login|
|password|query|string|false|The password for login in clear text|

> Example responses

> 200 Response

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<type>string</type>
```

```json
{
  "type": "string"
}
```

<h3 id="loginuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|string|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username/password supplied|None|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|X-Rate-Limit|integer|int32|calls per hour allowed by the user|
|200|X-Expires-After|string|date-time|date in UTC when token expires|

<aside class="success">
This operation does not require authentication
</aside>

## logoutUser

<a id="opIdlogoutUser"></a>

`GET /user/logout`

*Logs out current logged in user session*

<h3 id="logoutuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## getUserByName

<a id="opIdgetUserByName"></a>

`GET /user/{username}`

*Get user by user name*

<h3 id="getuserbyname-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The name that needs to be fetched. Use user1 for testing. |

> Example responses

> 200 Response

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <username>
      <type>string</type>
      <example>theUser</example>
    </username>
    <firstName>
      <type>string</type>
      <example>John</example>
    </firstName>
    <lastName>
      <type>string</type>
      <example>James</example>
    </lastName>
    <email>
      <type>string</type>
      <example>john@email.com</example>
    </email>
    <password>
      <type>string</type>
      <example>12345</example>
    </password>
    <phone>
      <type>string</type>
      <example>12345</example>
    </phone>
    <userStatus>
      <type>integer</type>
      <description>User Status</description>
      <format>int32</format>
      <example>1</example>
    </userStatus>
  </properties>
  <xml>
    <name>user</name>
  </xml>
</user>
```

<h3 id="getuserbyname-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[User](#schemauser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## updateUser

<a id="opIdupdateUser"></a>

`PUT /user/{username}`

*Update user*

This can only be done by the logged in user.

> Body parameter

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}
```

```yaml
type: object
properties:
  id:
    type: integer
    format: int64
    example: 10
  username:
    type: string
    example: theUser
  firstName:
    type: string
    example: John
  lastName:
    type: string
    example: James
  email:
    type: string
    example: john@email.com
  password:
    type: string
    example: "12345"
  phone:
    type: string
    example: "12345"
  userStatus:
    type: integer
    description: User Status
    format: int32
    example: 1
xml:
  name: user

```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<user>
  <type>object</type>
  <properties>
    <id>
      <type>integer</type>
      <format>int64</format>
      <example>10</example>
    </id>
    <username>
      <type>string</type>
      <example>theUser</example>
    </username>
    <firstName>
      <type>string</type>
      <example>John</example>
    </firstName>
    <lastName>
      <type>string</type>
      <example>James</example>
    </lastName>
    <email>
      <type>string</type>
      <example>john@email.com</example>
    </email>
    <password>
      <type>string</type>
      <example>12345</example>
    </password>
    <phone>
      <type>string</type>
      <example>12345</example>
    </phone>
    <userStatus>
      <type>integer</type>
      <description>User Status</description>
      <format>int32</format>
      <example>1</example>
    </userStatus>
  </properties>
  <xml>
    <name>user</name>
  </xml>
</user>
```

<h3 id="updateuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|name that need to be deleted|
|body|body|[User](#schemauser)|false|Update an existent user in the store|

<h3 id="updateuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="success">
This operation does not require authentication
</aside>

## deleteUser

<a id="opIddeleteUser"></a>

`DELETE /user/{username}`

*Delete user*

This can only be done by the logged in user.

<h3 id="deleteuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The name that needs to be deleted|

<h3 id="deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Invalid username supplied|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User not found|None|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Order">Order</h2>
<!-- backwards compatibility -->
<a id="schemaorder"></a>
<a id="schema_Order"></a>
<a id="tocSorder"></a>
<a id="tocsorder"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "petId": {
      "type": "integer",
      "format": "int64",
      "example": 198772
    },
    "quantity": {
      "type": "integer",
      "format": "int32",
      "example": 7
    },
    "shipDate": {
      "type": "string",
      "format": "date-time"
    },
    "status": {
      "type": "string",
      "description": "Order Status",
      "example": "approved",
      "enum": [
        "placed",
        "approved",
        "delivered"
      ]
    },
    "complete": {
      "type": "boolean"
    }
  },
  "xml": {
    "name": "order"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|petId|integer(int64)|false|none|none|
|quantity|integer(int32)|false|none|none|
|shipDate|string(date-time)|false|none|none|
|status|string|false|none|Order Status|
|complete|boolean|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|placed|
|status|approved|
|status|delivered|

<h2 id="tocS_Customer">Customer</h2>
<!-- backwards compatibility -->
<a id="schemacustomer"></a>
<a id="schema_Customer"></a>
<a id="tocScustomer"></a>
<a id="tocscustomer"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 100000
    },
    "username": {
      "type": "string",
      "example": "fehguy"
    },
    "address": {
      "type": "array",
      "xml": {
        "name": "addresses",
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "street": {
            "type": "string",
            "example": "437 Lytton"
          },
          "city": {
            "type": "string",
            "example": "Palo Alto"
          },
          "state": {
            "type": "string",
            "example": "CA"
          },
          "zip": {
            "type": "string",
            "example": "94301"
          }
        },
        "xml": {
          "name": "address"
        }
      }
    }
  },
  "xml": {
    "name": "customer"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|username|string|false|none|none|
|address|[[Address](#schemaaddress)]|false|none|none|

<h2 id="tocS_Address">Address</h2>
<!-- backwards compatibility -->
<a id="schemaaddress"></a>
<a id="schema_Address"></a>
<a id="tocSaddress"></a>
<a id="tocsaddress"></a>

```json
{
  "type": "object",
  "properties": {
    "street": {
      "type": "string",
      "example": "437 Lytton"
    },
    "city": {
      "type": "string",
      "example": "Palo Alto"
    },
    "state": {
      "type": "string",
      "example": "CA"
    },
    "zip": {
      "type": "string",
      "example": "94301"
    }
  },
  "xml": {
    "name": "address"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|street|string|false|none|none|
|city|string|false|none|none|
|state|string|false|none|none|
|zip|string|false|none|none|

<h2 id="tocS_Category">Category</h2>
<!-- backwards compatibility -->
<a id="schemacategory"></a>
<a id="schema_Category"></a>
<a id="tocScategory"></a>
<a id="tocscategory"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 1
    },
    "name": {
      "type": "string",
      "example": "Dogs"
    }
  },
  "xml": {
    "name": "category"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|name|string|false|none|none|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "username": {
      "type": "string",
      "example": "theUser"
    },
    "firstName": {
      "type": "string",
      "example": "John"
    },
    "lastName": {
      "type": "string",
      "example": "James"
    },
    "email": {
      "type": "string",
      "example": "john@email.com"
    },
    "password": {
      "type": "string",
      "example": "12345"
    },
    "phone": {
      "type": "string",
      "example": "12345"
    },
    "userStatus": {
      "type": "integer",
      "description": "User Status",
      "format": "int32",
      "example": 1
    }
  },
  "xml": {
    "name": "user"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|username|string|false|none|none|
|firstName|string|false|none|none|
|lastName|string|false|none|none|
|email|string|false|none|none|
|password|string|false|none|none|
|phone|string|false|none|none|
|userStatus|integer(int32)|false|none|User Status|

<h2 id="tocS_Tag">Tag</h2>
<!-- backwards compatibility -->
<a id="schematag"></a>
<a id="schema_Tag"></a>
<a id="tocStag"></a>
<a id="tocstag"></a>

```json
{
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64"
    },
    "name": {
      "type": "string"
    }
  },
  "xml": {
    "name": "tag"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|name|string|false|none|none|

<h2 id="tocS_Pet">Pet</h2>
<!-- backwards compatibility -->
<a id="schemapet"></a>
<a id="schema_Pet"></a>
<a id="tocSpet"></a>
<a id="tocspet"></a>

```json
{
  "required": [
    "name",
    "photoUrls"
  ],
  "type": "object",
  "properties": {
    "id": {
      "type": "integer",
      "format": "int64",
      "example": 10
    },
    "name": {
      "type": "string",
      "example": "doggie"
    },
    "category": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer",
          "format": "int64",
          "example": 1
        },
        "name": {
          "type": "string",
          "example": "Dogs"
        }
      },
      "xml": {
        "name": "category"
      }
    },
    "photoUrls": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "string",
        "xml": {
          "name": "photoUrl"
        }
      }
    },
    "tags": {
      "type": "array",
      "xml": {
        "wrapped": true
      },
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer",
            "format": "int64"
          },
          "name": {
            "type": "string"
          }
        },
        "xml": {
          "name": "tag"
        }
      }
    },
    "status": {
      "type": "string",
      "description": "pet status in the store",
      "enum": [
        "available",
        "pending",
        "sold"
      ]
    }
  },
  "xml": {
    "name": "pet"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|false|none|none|
|name|string|true|none|none|
|category|[Category](#schemacategory)|false|none|none|
|photoUrls|[string]|true|none|none|
|tags|[[Tag](#schematag)]|false|none|none|
|status|string|false|none|pet status in the store|

#### Enumerated Values

|Property|Value|
|---|---|
|status|available|
|status|pending|
|status|sold|

<h2 id="tocS_ApiResponse">ApiResponse</h2>
<!-- backwards compatibility -->
<a id="schemaapiresponse"></a>
<a id="schema_ApiResponse"></a>
<a id="tocSapiresponse"></a>
<a id="tocsapiresponse"></a>

```json
{
  "type": "object",
  "properties": {
    "code": {
      "type": "integer",
      "format": "int32"
    },
    "type": {
      "type": "string"
    },
    "message": {
      "type": "string"
    }
  },
  "xml": {
    "name": "##default"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|false|none|none|
|type|string|false|none|none|
|message|string|false|none|none|

