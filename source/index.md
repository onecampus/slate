---
title: 学壹传媒 API 文档

language_tabs:
  - shell
  - ruby
  - java

toc_footers:
  - <a href='#'>学壹传媒</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# 介绍

学壹传媒API文档

# 授权

> 使用一下方式授权:

```ruby
```

```java
```

```shell
# 发送正确的authorization
curl "api_endpoint_here"
  -H "Authorization: Basic O4K4EGheju926VhH67KXOQ'"
```

> 替换 `O4K4EGheju926VhH67KXOQ` 为你的 `access_token`.

提供两种 `access_token` 发送形式:

* `Authorization: Basic O4K4EGheju926VhH67KXOQ`
* `url?access_token=O4K4EGheju926VhH67KXOQ`

<aside class="notice">
替换 `O4K4EGheju926VhH67KXOQ` 为你自己的 `access_token`.
</aside>


# 大学

## 大学列表

```ruby
```

```java
```

```shell
curl "http://api.thecampus.cc/api/v1/universities"
  -H "Authorization: Basic O4K4EGheju926VhH67KXOQ"
```

> JSON形如:

```json
{
  'status': 'success',
  'code': 200,
  'msg': '',
  'data': '',
  'links': {}
}
```

活取所有的大学列表.

### HTTP Request

`GET http://api.thecampus.cc/api/v1/universities`

### 参数

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```java
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP 请求

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

