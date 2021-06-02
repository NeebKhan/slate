---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ

  - javascript

toc_footers:
  - If you have any questions,<br> please feel free to email us at<br> support@voxpopme.com


includes:
  - errors

search: true

code_clipboard: true
---

# Introduction

The Voxpopme embed widgets can be implemented by adding snippets of code onto your web page(s)<br><br>
The widgets make it so that you can easily view Voxpopme content within your own platform.
<br><br>
The summary widget allows you to preview videos and themes similar to how the Auto-video summarization section appears within Insights when viewing the portal directly

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# 

## Summary Widget

```javascript
  <vpm-auto-summary-widget data-config="vpmConfig"></vpm-auto-summary-widget>
        <script>
              var vpmGlobal = {
                  "auth": {
                      "version": "v1",
                      "payload": "PAYLOAD"
                  }
              }
              var vpmConfig = {
                  "questionId": [your_project_id]
              };
              (function() {
                  var d = document, s = d.createElement('script');
                  s.src = 'https://vpm-importer.s3-eu-west-1.amazonaws.com/media/general_client/voxpopme/embed-widget/bundle.js';
                  (d.head || d.body).appendChild(s);
              })();
        </script>
```
> In the above example, replace [your_project_id] with your desired Project ID.

> If you would like to see an example of this within a browser before adding it; you can save the below example as a .html file, replace [<mark>your_project_id</mark>] with your desired ID and open it in a web browser:

```javascript
<html>
    <title>Widget Page</title>
    <body>
        <vpm-auto-summary-widget data-config="vpmConfig"></vpm-auto-summary-widget>
        <script>
              var vpmGlobal = {
                  "auth": {
                      "version": "v1",
                      "payload": "PAYLOAD"
                  }
              }
              var vpmConfig = {
                  "questionId": [your_project_id]
              };
              (function() {
                  var d = document, s = d.createElement('script');
                  s.src = 'https://vpm-importer.s3-eu-west-1.amazonaws.com/media/general_client/voxpopme/embed-widget/bundle.js';
                  (d.head || d.body).appendChild(s);
              })();
        </script>
    </body>
</html>
```

Replace [your_project_id] in the following code with your desired Project ID:

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
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

Replace your_project_id in the following code with your desired Project ID

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

