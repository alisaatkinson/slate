---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/alisaatkinson'>Written by Alisa Atkinson</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Documentation API
---

# Introduction

The Documentation API is used to determine the Technical Writer's effectiveness when writing API documentation with Slate. The Documentation enpoints allow access to various published works including but not limited to:

* User Guides
* Quick Reference Cards
* API Reference Documentation
* Engineering Architecture


# Authentication

> Use the following code to perform authentication for Documentation:

```ruby
require 'Documentation'

api = Documentation::APIClient.authorize!('UserGuide')
```

```python
import Documentation

api = Documentation.authorize('User Guide')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: UserGuide"
```

```javascript
const Documentation = require('Documentation');

let api = Documentation.authorize('userguide');
```

> 

The library uses API keys to allow access to the Documentation API. New API keys can be registered at the following portal:
 [developer portal](http://example.com/developers).

Documentation expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: UserGuide`

<aside class="notice">
 <code>UserGuide</code> must be replaced with a API key.
</aside>

# Documentation

## Get All UserGuides

```ruby
require 'UserGuides'

api = UserGuides::APIClient.authorize!('UserGuide')
api.userguides.get
```

```python
import userguide

api = userguides.authorize('UserGuide')
api.UserGuides.get()
```

```shell
curl "http://example.com/api/Userguide" \
  -H "Authorization: UserGuides"
```

```javascript
const Userguide = require('UserGuide');

let api = userguides.authorize('UserGuide');
let UserGuides = api.userguides.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "title": "Backend for Frontend",
    "Genre": "Architecture",
  },
  {
    "id": 2,
    "title": "Azure Dev-Ops Naming Conventions",
    "genre": "Developer Documentation",
  }
]
```

The following endpoint retrieves all User Guides.

### HTTP Request

`GET http://example.com/api/UserGuides`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_allgenres | false | If set to true, the result will also include all genres.
available | true | If set to false, the result will include varying types of documentation.

<aside class="success">
Remember — When life gives you lemons read the juicer manual!
</aside>

## Get a Specific Document

```ruby
require 'UserGuide'

api = Documentation::APIClient.authorize!('UserGuides')
api.documentation.get(2)
```

```python
import document

api = document.authorize('User Guide')
api.documents.get(2)
```

```shell
curl "http://example.com/api/documents/2" \
  -H "Authorization: User Guide"
```

```javascript
const document = require('Document');

let api = document.authorize('User Guide');
let max = api.document.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific document.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/documents/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the document to retrieve

## Delete a Specific Document

```ruby
require 'alisa'

api = Alisa::APIClient.authorize!('UserGuide')
api.alisa.delete(2)
```

```python
import Alisa

api = Alisa.authorize('UserGuide')
api.Alisa.delete(2)
```

```shell
curl "http://example.com/api/Alisa/2" \
  -X DELETE \
  -H "Authorization: UserGuide"
```

```javascript
const alisa = require('alisa');

let api = alisa.authorize('UserGuide');
let max = api.Alisa.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific user guide.

### HTTP Request

`DELETE http://alisa.atkinson.com/UserGuide/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the User Guide to delete

