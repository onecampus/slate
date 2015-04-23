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
curl "http://localhost:3000/api/v1/universities" -H "Authorization: Basic O4K4EGheju926VhH67KXOQ"
```

> JSON形如:

```json
{
    "status": "success",
    "code": 200,
    "msg": "Universities all.",
    "data": {
        "universities": [
            {
                "id": 1,
                "university_code": 1001,
                "name": "清华大学",
                "intro": null,
                "province_code": 110000,
                "english_name": null,
                "longitude": null,
                "latitude": null,
                "created_at": null,
                "updated_at": null
            },
            {
                "id": 2,
                "university_code": 1002,
                "name": "北京大学",
                "intro": null,
                "province_code": 110000,
                "english_name": null,
                "longitude": null,
                "latitude": null,
                "created_at": null,
                "updated_at": null
            },
            {
                "id": 3,
                "university_code": 1003,
                "name": "中国人民大学",
                "intro": null,
                "province_code": 110000,
                "english_name": null,
                "longitude": null,
                "latitude": null,
                "created_at": null,
                "updated_at": null
            }
        ]
    },
    "links": null
}
```

活取所有的大学列表, 不需要认证

### HTTP Request

`GET http://api.thecampus.cc/api/v1/universities`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------

<aside class="success">
</aside>

# 用户

## 注册

```ruby
```

```java
```

```shell
curl "http://localhost:3000/api/v1/users/register" -d "register[mobile]=13560474457&register[pass]=12345678"
```

> JSON形如:

```json
{
    "status": "success",
    "code": 201,
    "msg": "User registered success.",
    "data": {
        "user": {
            "id": 7,
            "last_name": null,
            "first_name": null,
            "nick_name": null,
            "uid": null,
            "avatar": null,
            "email": null,
            "age": null,
            "university_id": null,
            "address_current": null,
            "birthday": null,
            "mobile": "1356048958",
            "gender": null,
            "access_token": "JIuflK7-pd19XtQmip6U5g",
            "expiration_time": "2015-05-03T14:13:32.671+08:00",
            "last_login_ip": null,
            "register_status": null,
            "last_sign_in_at": null,
            "language": null,
            "register_type": null,
            "personalized_signature": null,
            "country": null,
            "province": null,
            "city": null,
            "region": null,
            "postcode": null,
            "tel": null,
            "created_at": "2015-04-23T14:13:32.703+08:00",
            "updated_at": "2015-04-23T14:13:32.703+08:00",
            "create_by": null
        }
    },
    "links": null
}
```

用户注册, 不需要认证

### HTTP Request

`POST http://api.thecampus.cc/api/v1/users/register`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
register[mobile] | none | 手机号
register[pass]   | none | 密码

<aside class="success">
</aside>

## 登录

```ruby
```

```java
```

```shell
curl "http://localhost:3000/api/v1/users/login" -d "login[mobile]=13560474456&login[pass]=12345678"
```

> JSON形如:

```json
# fail
{
    "status": "fail",
    "code": 1411,
    "msg": "Invalid mobile or password.",
    "data": null,
    "links": null
}

# success
{
    "status": "success",
    "code": 200,
    "msg": "Login success.",
    "data": {
        "access_token": "O4K4EGheju926VhH67KXOQ",
        "expiration_time": "2015-05-03T10:28:54.000+08:00",
        "current_user": {
            "id": 1,
            "last_name": "杨",
            "first_name": "浮生",
            "nick_name": "浮生",
            "uid": "flowerwrong",
            "avatar": "/test.png",
            "email": "yk@gmail.com",
            "age": 22,
            "university_id": 1,
            "address_current": "12.089, 72.569",
            "birthday": "1993-04-23T10:28:54.000+08:00",
            "mobile": "13560474456",
            "gender": "male",
            "access_token": "O4K4EGheju926VhH67KXOQ",
            "expiration_time": "2015-05-03T10:28:54.000+08:00",
            "last_login_ip": "127.0.0.1",
            "register_status": "active",
            "last_sign_in_at": "2015-04-23T14:28:45.438+08:00",
            "language": "zh_CN",
            "register_type": "mobile",
            "personalized_signature": "flowerwrong",
            "country": "中国",
            "province": "广东",
            "city": "广州",
            "region": "番禺",
            "postcode": "510000",
            "tel": "88888888",
            "created_at": "2015-04-23T10:28:54.000+08:00",
            "updated_at": "2015-04-23T14:28:45.481+08:00",
            "create_by": 0
        }
    },
    "links": null
}
```

用户登录, 不需要认证

### HTTP 请求

`POST http://api.thecampus.cc/api/v1/users/login`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
login[mobile] | none | 手机号
login[pass]   | none | 密码


## 退出登录

```ruby
```

```java
```

```shell
curl -X DELETE "http://localhost:3000/api/v1/users/1/logout" -H "Authorization: Basic O4K4EGheju926VhH67KXOQ"
```

> JSON形如:

```json
# fail1: access_token有误
{
    "status": "fail",
    "code": 401,
    "msg": "Not Authorized.",
    "data": null,
    "links": null
}

# fail2: 发送的用户id和他的access_token没有对应, 即不是当前用户在操作
{
    "status": "fail",
    "code": 403,
    "msg": "Not current user.",
    "data": null,
    "links": null
}

# success
{
    "status": "success",
    "code": 200,
    "msg": "Logout success.",
    "data": null,
    "links": null
}
```

用户退出登录

<aside class="warning">注意: 必须是access_token和发送的ID指向同一个用户.</aside>

### HTTP 请求

`DELETE http://api.thecampus.cc/api/v1/users/<ID>/logout`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
ID | none | 用户id

## 单个用户信息

```ruby
```

```java
```

```shell
curl "http://localhost:3000/api/v1/users/1" -H "Authorization: Basic 7pQOwX_2cHs0zwM7vwo0RA"
```

> JSON形如:

```json
# fail: 发送的用户id和他的access_token没有对应, 即不是当前用户在操作
{
    "status": "fail",
    "code": 403,
    "msg": "Not current user.",
    "data": null,
    "links": null
}

# success
{
    "status": "success",
    "code": 200,
    "msg": "User info.",
    "data": {
        "user": {
            "id": 1,
            "last_name": "杨",
            "first_name": "浮生",
            "nick_name": "浮生",
            "uid": "flowerwrong",
            "avatar": "/test.png",
            "email": "yk@gmail.com",
            "age": 22,
            "university_id": 1,
            "address_current": "12.089, 72.569",
            "birthday": "1993-04-23T10:28:54.000+08:00",
            "mobile": "13560474456",
            "gender": "male",
            "access_token": "7pQOwX_2cHs0zwM7vwo0RA",
            "expiration_time": "2015-05-03T10:28:54.000+08:00",
            "last_login_ip": "127.0.0.1",
            "register_status": "active",
            "last_sign_in_at": "2015-04-23T14:28:45.000+08:00",
            "language": "zh_CN",
            "register_type": "mobile",
            "personalized_signature": "flowerwrong",
            "country": "中国",
            "province": "广东",
            "city": "广州",
            "region": "番禺",
            "postcode": "510000",
            "tel": "88888888",
            "created_at": "2015-04-23T10:28:54.000+08:00",
            "updated_at": "2015-04-23T14:38:37.000+08:00",
            "create_by": 0
        }
    },
    "links": null
}
```

获取单个用户信息

### HTTP 请求

`GET http://api.thecampus.cc/api/v1/users/<ID>`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
ID | none | 用户id

## 上传用户头像

```ruby
```

```java
```

```shell
curl "http://localhost:3000/api/v1/users/1/avatar/update" -F "avatar=@/home/yang/dev/ruby/rails/vote/app/assets/images/bg1.jpg" -H "Authorization: Basic 7pQOwX_2cHs0zwM7vwo0RA"
```

> JSON形如:

```json
{
    "status": "success",
    "code": 200,
    "msg": "User avatar success.",
    "data": null,
    "links": null
}
```

上传用户头像

### HTTP 请求

`POST http://api.thecampus.cc/api/v1/users/<ID>/avatar/update`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
ID | none | 用户id
avatar | none | 用户头像图片

## 更新密码

```ruby
```

```java
```

```shell
curl -X PUT "http://localhost:3000/api/v1/users/1/password/update" -d "user[pass]=12345678" -H "Authorization: Basic 7pQOwX_2cHs0zwM7vwo0RA"
```

> JSON形如:

```json
{
    "status": "success",
    "code": 200,
    "msg": "User pass update success.",
    "data": null,
    "links": null
}
```

更新密码

### HTTP 请求

`PUT http://api.thecampus.cc/api/v1/users/<ID>/password/update`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
ID | none | 用户id
user[pass] | none | 用户新密码


# 推文

## 创建推文

```ruby
```

```java
```

```shell
curl "http://localhost:3000/api/v1/users/register" -d "register[mobile]=13560474457&register[pass]=12345678"
```

> JSON形如:

```json

```

用户注册, 不需要认证

### HTTP Request

`POST http://api.thecampus.cc/api/v1/users/register`

### 参数

参数 | 默认值 | 描述
--------- | ------- | -----------
register[mobile] | none | 手机号
register[pass]   | none | 密码

<aside class="success">
</aside>
