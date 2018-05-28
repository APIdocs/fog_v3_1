# 移动端 产品接口文档

## 应用下可选品类 接口
**接口地址**

> GET /v3_1/enduser/product/category/(JWT认证)
 
 **请求参数示例**
 ```
GET /v3_1/enduser/product/category/?app_id=dlfkl83803jef

```

**请求参数说明**

| 参数 | 类型 | 必须 | 说明 |
| ---- | ---- | ---- | ---- |
|app_id|varchar|yes|应用id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "default_picture": "https://mxchip-fog.oss-cn-beijing.aliyuncs.com/product/productdefault.jpg",
            "type_id": 3,
            "name": "球泡灯"
        },
        {
            "default_picture": "https://mxchip-fog.oss-cn-beijing.aliyuncs.com/product/productdefault.jpg",
            "type_id": 1,
            "name": "景观灯"
        }
    ]
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|name|varchar|类别名称|
|type_id|int|类别id|
|default_picture|varchar|产品类型图标url|


## 按类别获取产品 接口(JWT认证)
**接口地址**
> GET /v3_1/enduser/product/productList/

**请求参数**
```
GET /v3_1/enduser/product/productList/?type_id=1&app_id=cklretk4kndfg
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|type_id|int|yes|产品类别id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "picture": "",
            "product_id": "7405d040f9bf11e7998d000c299d4a8e",
            "name": "test7"
        },
        {
            "picture": "",
            "product_id": "09646efef9a111e7998d000c299d4a8e",
            "name": "test5"
        },
        {
            "picture": "",
            "product_id": "176b4d88f6a411e7998d000c299d4a89",
            "name": "test"
        }
    ]
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|name|varchar|产品名称|
|product_id|varchar|产品id|
|picture|varchar|产品图片url|


## 语音接入状态 接口(JWT认证)
**接口地址**
> GET /v3_1/enduser/product/voiceSupport/

**请求参数**
```
GET /v3_1/enduser/product/voiceSupport/?app_id=3375ba62f1cd11e7998d000c299d4a8e

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|是|应用id|


**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "ali_genie": ["test","test2"],
        "aws_echo": ["test","test2"],
        "google_home": ["test","test2"]
    }
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|product_name|varchar|产品名称|
|product_id|varchar|产品编号|


## 获取关于应用 接口
**接口地址**
> GET /v3_1/enduser/app/aboutApp/

**请求参数**
```
GET /v3_1/enduser/app/aboutApp/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1

```
* 现移动端未配置语言，默认英文的语言id为1,中文的语言id为2

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "app_info": "应用XX是一款智能控制球泡灯应用，用XX应用点亮你的家，让你的家智能起来",
        "detail":[
            {
                contact_title": "热线",
                "contact": "1235546464",
                "contact_display": "0"
                },
            {    
                "website_title": "官网",
                "website": "www.google.com",
                "website_display": "1"
                },
            {
                "email_title": "反馈邮箱",
                "email": "hotpot@hotmail.com",
                "email_display": "1"
                }  
    }
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|app_info|varchar|应用简介|
|contact_title|varchar|热线电话标题|
|contact|varchar|热线电话|
|contact_display|varchar|是否显示热线,0(不显示),1(显示)|
|website_title|varchar|网站标题|
|website|varchar|网站|
|website_display|varchar|是否显示网站,0(不显示),1(显示)|
|email_title|varchar|邮箱标题|
|email|varchar|邮箱|
|email_display|varchar|是否显示邮箱,0(不显示),1(显示)|
