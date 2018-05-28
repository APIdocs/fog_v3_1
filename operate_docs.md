# 运营管理模块　接口文档

## 
**接口地址**
> 

**请求参数**
```

```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|

**返回参数**
```

```

**返回参数说明**
|参数|类型|说明|
|----|----|----|


## 用户列表 接口
**接口地址**
> GET /v3_1/operate/user_list/

**请求参数**
```
GET /v3_1/operate/user_list/?page=1&page_size=10&user_name=cui&phone=1234567890
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|page|int|yes|页数|
|page_size|int|yes|每页数量|
|user_name|varchar|no|根据用户名搜索|
|phone|int|no|根据电话搜索|
**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "page_size": 10,
        "next": null,
        "previous": null,
        "results": [
            {
                "enduser_id": "c15ac990f9a111e7804bfa163e431402",
                "user_name": "",
                "city": "",
                "phone": "18621343907",
                "create_time": "2018-01-15T11:11:18",
                "last_login": "2018-01-15T12:05:50"
            }
        ]
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|enduser_id|varchar|用户id|
|user_name|varchar|用户名称|
|city|varchar|用户地区|
|phone|varchar|用户电话|
|create_time|datetime|注册时间|
|last_login|datetime|最后活跃时间|


## 用户下的设备列表 接口
**接口地址**
> GET /v3_1/operate/user_device/

**请求参数**
```
GET /v3_1/operate/user_device/?enduser_id=01234567880
```
**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|enduser_id|int|yes|终端用户id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "page_size": 10,
        "next": null,
        "previous": null,
        "results": [
            {
                "enduser_id": "c15ac990f9a111e7804bfa163e431402",
                "device_id": "7367242cf9a111e7804bfa163e431402",
                "dsn": "123123",
                "product": "light_cui",
                "create_time": "2018-01-15T11:09:08.443963",
                "last_login": "2018-01-15T11:09:08.697267"
            }
        ]
    }
}

```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|enduser_id|varchar|终端用户id|
|device_id|varchar|设备编号|
|dsn|varchar|MAC地址|
|product|varchar|产品名称|
|create_time|datetime|激活时间|
|last_login|datetime|最后活跃时间|


## 设备列表 接口
**接口地址**
> GET /v3_1/operate/device_list/

**请求参数**
```
GET /v3_1/operate/device_list/?page=1&page_size=10&dvice_id=&dsn=

```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|page|int|yes|页数|
|page_size|int|yes|每页数量|
|device_id|varchar|no|根据设备ID搜索|
|dsn|varchar|no|根据MAC地址搜索|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "page_size": 10,
        "next": null,
        "previous": null,
        "results": [
            {
                "device_id": "7367242cf9a111e7804bfa163e431402",
                "product": "light_cui",
                "create_time": "2018-01-15T11:09:08.443963",
                "dsn": "123123",
                "last_login": "2018-01-15T11:09:08.697267"
            }
        ]
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|device_id|varchar|设备编号|
|dsn|varchar|MAC地址|
|product|varchar|产品名称|
|create_time|datetime|激活时间|
|last_login|datetime|最后活跃时间|

## 反馈列表 接口
**接口地址**
> GET /v3_1/operate/feedback_list/

**请求参数**
```
GET /v3_1/operate/feedback_list/?page=1&page_size=10

```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|page|int|yes|页数|
|page_size|int|yes|每页数量|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "page_size": 10,
        "next": null,
        "previous": null,
        "results": [
            {
                "user": "",
                "product": "light_cui",
                "updated_at": "2018-01-15T11:09:08.443963",
                "status": 0,
                "feedback": "插座离线之后未断开"
            }
        ]
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|user|varchar|反馈用户|
|product|varchar|产品名称|
|status|int|反馈状态|
|updated_at|datetime|更新时间|
|feedback|varchar|反馈内容|

## 反馈消息列表 接口
**接口地址**
> GET /v3_1/operate/feedback_message/

**请求参数**
```
GET /v3_1/operate/feedback_message/?page=1&page_size=10&feedback_id=3

```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|page|int|yes|页数|
|page_size|int|yes|每页数量|
|feedbace_id|int|yes|反馈id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "page_size": 10,
        "next": null,
        "previous": null,
        "results": [
            {
                "feedback_id": "7",
                "created_at": "2018-01-15T11:09:08.443963",
                "message": "{"text":"how can i cancel the order?","image":["url","url2"]}"
            }
        ]
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|feedback_id|int|反馈编号|
|message|json|反馈消息|
|created_at|datetime|创建时间|

## 新建反馈消息 接口
**接口地址**
> post /v3_1/operate/feedback_message/

**请求参数**
```
{
    "feedback_id": 3,
    "message":{"text":"how can i cancel the order?","image":["url","url2"]}
}

```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|message|json|yes|反馈消息|
|feedbace_id|int|yes|反馈id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
                "feedback_id": "7",
                "message": "{"text":"how can i cancel the order?","image":["url","url2"]}"
            }
        ]
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|feedback_id|int|反馈编号|
|message|json|反馈消息|
|created_at|datetime|创建时间|







