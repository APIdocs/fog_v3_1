# 工单模块　接口文档

## 新建工单 接口
**接口地址**
> POST /v3_1/workorder/workorder/

**请求参数**
```
{

"support":1,
"type":"sys",
"question":"how to cancel my order?"
}

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|support|int|yes|是否需要电话支持|
|type|varchar|yes|工单类型,("sys", "系统故障"),("licences", "配额")|
|question|varchar|yes|工单问题描述|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "committer": "3",
        "id": 5,
        "question": "how to cancel my order?",
        "type": "sys",
        "status": "2",
        "support": true,
        "updated_at": "2018-01-26T10:59:52.576973",
        "created_at": "2018-01-26T10:59:52.576931"
    }
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|committer|varchar|工单提交人|
|id|int|工单编号|
|question|varchar|工单问题描述|
|type|varchar|工单类型|
|status|varchar|工单状态|
|support|bool|是否电话支持|
|updated_at|datetime|更新时间|
|created_at|datetime|创建时间|


## 工单列表 接口 
**接口地址**
> GET /v3_1/workorder/workorder_list/

**请求参数**
```
GET /v3_1/workorder/workorder_list/?page=1&page_size=15

# 如果需要分页，page和page_size参数为必须参数
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|page|int|no|分页页数|
|page_size|int|no|每页数量|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 6,
        "page_size": 15,
        "next": null,
        "previous": null,
        "results": [
            {
                "id": 2,
                "committer": 3,
                "question": "test",
                "type": "sys",
                "status": 2,
                "support": true,
                "updated_at": "2018-01-25T14:54:51.542049",
                "created_at": "2018-01-25T14:54:51.541976"
            },
            {
                "id": 3,
                "committer": 3,
                "question": "hello",
                "type": "sys",
                "status": 2,
                "support": true,
                "updated_at": "2018-01-25T16:42:58.278029",
                "created_at": "2018-01-25T16:42:58.277982"
            },
            {
                "id": 4,
                "committer": 3,
                "question": "hello",
                "type": "sys",
                "status": 2,
                "support": true,
                "updated_at": "2018-01-25T18:13:57.400138",
                "created_at": "2018-01-25T18:13:57.400097"
            },
            {
                "id": 1,
                "committer": 3,
                "question": "test",
                "type": "sys",
                "status": 0,
                "support": true,
                "updated_at": "2018-01-26T10:53:31.322729",
                "created_at": "2018-01-25T14:34:00.801412"
            }
        ]
    }
    }    

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|committer|varchar|工单提交人|
|id|int|工单编号|
|question|varchar|工单问题描述|
|type|varchar|工单类型|
|status|varchar|工单状态|
|support|bool|是否电话支持|
|updated_at|datetime|更新时间|
|created_at|datetime|创建时间|


## 工单详情回复 接口 
**接口地址**
> POST /v3_1/workorder/workorder_detail/

**请求参数**
```
{

"workorder_id":1,
"detail":{
            "text":"yeah, please give me your order id", 
            "image":["http://www.baidu.com/image.order.jpg"]
         }
}
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|workorder_id|int|yes|工单编号|
|detail|dict|yes|工单回复详情，格式按请求参数,如没有图像内容，image可以为空列表|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "committer": "hhq",
        "workorder_id": 1,
        "role": 0,
        "detail": {
            "text": "yeah, please give me your order id",
            "image": [
                "http://www.baidu.com/image.order.jpg"
            ]
        },
        "created_at": "2018-01-26T11:29:48.437883"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|committer|varchar|回复详情用户|
|workorder_id|int|工单编号|
|role|int|角色,(0,提问用户),(1,回答用户)|
|detail|dict|回复详情|
|created_at|datetime|回复时间|

## 工单详情列表 接口 
**接口地址**
> GET /v3_1/workorder/workorder_detail/?

**请求参数**
```
GET /v3_1/workorder/workorder_detail/?workorder_id=1&page=1&page_size=15

# 如需分页，需携带参数page和page_size
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|workorder_id|int|yes|工单编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 5,
        "page_size": 15,
        "next": null,
        "previous": null,
        "results": [
            {
                "committer": "hhq",
                "workorder_id": 1,
                "role": 0,
                "detail": {
                    "text": "yeah, please give me your order id",
                    "image": [
                        "http://www.baidu.com/image.order.jpg"
                    ]
                },
                "created_at": "2018-01-26T11:29:48.437883"
            },
            {
                "committer": "hhq",
                "workorder_id": 1,
                "role": 1,
                "detail": {
                    "text": "好啊",
                    "image": []
                },
                "created_at": "2018-01-25T17:05:55.871666"
            },
            {
                "committer": "hhq",
                "workorder_id": 1,
                "role": 1,
                "detail": {
                    "text": "你好，可以取消订单吗",
                    "image": []
                },
                "created_at": "2018-01-25T17:04:26.426863"
            }
        ]
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|committer|varchar|回复详情用户|
|workorder_id|int|工单编号|
|role|int|角色,(0,提问用户),(1,回答用户)|
|detail|dict|回复详情|
|created_at|datetime|回复时间|

## 修改工单状态 接口
**接口地址**
> POST /v3_1/workorder/workorder_status/

**请求参数**
```
{
    "workorder_id": 1,
    "status":2

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|workorder_id|int|yes|工单编号|
|status|int|yes|工单状态，(0, "已解决"),(1, "待解决"),(2, "新提交"),|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {}
}

```

## 工单内容 接口 
**接口地址**
> GET /v3_1/workorder/workorder_content/

**请求参数**
```
GET /v3_1/workorder/workorder_content/?workorder_id=&type=sys
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|workorder_id|int|yes|工单编号|
|type|varchar|yes|工单类型|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 1,
        "type": "sys",
        "status": 0,
        "question": "test"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|id|int|工单编号|
|type|varchar|工单类型, ("sys", "系统故障"),("licences", "配额"),("module", "购买云模块"),("tech", "技术支持"),("test", "测试协助")|
|status|int|工单状态|
|question|varchar|工单问题|
|module|varchar|云模块型号|
|amount|int|购买云模块数量|
|company|varchar|公司名称|
|contact|varchar|联系人|
|cellphone|varchar|联系电话|
|location|varchar|量产地区|
|email|varchar|联系邮箱|
|address|varchar|联系地址|
