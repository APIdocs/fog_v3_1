# 移动端 产品接口文档

## HOST 说明
* 开发测试 host: https://cnapitest.fogcloud.io
* api prefix: /v3_1/
* 完整 请求path: host + prefix + api

---
## 应用下产品类别 接口(JWT认证)
**接口地址**

> GET /enduser/product/category/
 
 **请求参数示例**
 ```
GET /enduser/product/category/?app_id=dlfkl83803jef

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

---
## 按类别获取产品 接口(JWT认证)
**接口地址**
> GET /enduser/product/productList/

**请求参数**
```
GET /enduser/product/productList/?type_id=1&app_id=cklretk4kndfg
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

---
## 语音接入状态 接口(JWT认证)
**接口地址**
> GET /enduser/product/voiceSupport/

**请求参数**
```
GET /enduser/product/voiceSupport/?app_id=3375ba62f1cd11e7998d000c299d4a8e

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

---
## 关于应用详情 接口
**接口地址**
> GET /enduser/app/aboutApp/

**请求参数**
```
GET /enduser/app/aboutApp/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1

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

---
## 获取帮助列表 接口（JWT认证）
**接口地址**
> GET /enduser/product/helpList/

**请求示例**
```
GET /enduser/product/helpList/?product_id=kdlflrk4lt5kylw3
```

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|product_id|varchar|yes|产品id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": o
    },
    "data": [
    			{"product_id": "kdlflrk4lt5kylw3",
                 "help_id":3,
                 "subject": "网络连接错误的说明"
                 },
                {"product_id":"kdlflrk4lt5kylw3",
                 "help_id": 8,
                 "subject": "使用智能音箱控制灯",
                }
      ]
}
```

**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|product_id|varchar|产品id|
|help_id|varchar|帮助编号|
|subject|varchar|帮助主题|

---
## 获取产品帮助支持详情 接口(JWT认证）

**接口地址**
> GET /v3_1/dm_v3/enduser/product/helpInfo/

**请求示例**
```
GET /v3_1/dm_v3/enduser/product/helpInfo/?help_id=7
```

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|help_id|int|yes|帮助信息编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": o
    },
    "data": 
    			{
                 "help_id":7,
                 "subject": "网络连接错误的说明",
                 "detail": "1.请确认你的设备已连接上网络；2.请尝试重新连接网络"
                 }
}
```

**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|help_id|int|帮助信息编号|
|subject|varchar|帮助主题|
|detail|varcahr|帮助信息详情|

## ~~获取终端语音接入状态 接口(JWT认证)~~

**接口地址**
> GET /v3_1/dm_v3/enduser/voiceStatus/

**请求示例**
```
GET /v3_1/dm_v3/enduser/voiceStatus/
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "enduser_id": "ce7d893a227511e8804bfa163e431402",
        "ali_genie": true,
        "aws_echo": false,
        "google_home": false
    }
}
```

**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|enduser_id|varchar|终端用户ID|
|aws_echo|bool|aws echo音响开关状态|
|google_home|bool|google home 音响开关状态|
|ali_genie|bool|天猫精灵音响开关状态|

---
## 更新终端语音接入状态 接口(JWT认证)

**接口地址**
> PUT /v3_1/dm_v3/enduser/voiceStatus/

**请求示例**
```
{
    "google_home":1
}
```
* 请求参数与需要开启关闭的音响名称一致

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|aws_echo|bool|no|aws echo音响开关状态,1(开启),0(关闭)|
|google_home|bool|no|google home 音响开关状态,1(开启),0(关闭)|
|ali_genie|bool|no|天猫精灵音响开关状态,1(开启),0(关闭)|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "enduser_id": "ce7d893a227511e8804bfa163e431402",
        "ali_genie": true,
        "aws_echo": false,
        "google_home": true
    }
}
```

**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|enduser_id|varchar|终端用户ID|
|aws_echo|bool|aws echo音响开关状态|
|google_home|bool|google home 音响开关状态|
|ali_genie|bool|天猫精灵音响开关状态|

---
## 获取设备位置信息 接口(JWT认证)
**请求地址**
> GET /v3_1/dm_v3/enduser/deviceLocaiton/

**请求示例**
```
GET /v3_1/dm_v3/enduser/deviceLocation/?device_id=kldgjlerkgtl3455l454
```
* 获取设备位置信息接口应在绑定设备时请求

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|device_id|string|yes|设备id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {"location": "310000"}
}
```

---
## 共享设备邀请 接口(JWT认证)

**接口地址**
> POST /v3_1/dm_v3/enduser/inviteUser/

**请求示例**
```
* POST /v3_1/dm_v3/enduser/inviteUser/

{
	"app_id":"0b4c4e80f73f11e7804bfa163e431403",
	"device_id":"6ee2d4680d8411e8804bfa163e431402",
	"invitee":"13918846727"
	
}
```

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|device_id|string|yes|设备id|
|app_id|string|yes|应用id|
|invitee|string|yes|被邀请人手机号码|

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

---
## 登陆查看是否有邀请 接口(JWT认证)

**接口地址**
> GET /v3_1/dm_v3/enduser/invitationState/

**请求示例**
```
GET /v3_1/dm_v3/enduser/invitationState/
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "inviter": "17656677890",
            "invitee": "18321937749",
            "app_id": "0b4c4e80f73f11e7804bfa163e431403",
            "device_id": "6ee2d4680d8411e8804bfa163e431402"
        }
    ]
}
```
**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|inviter|string|邀请人|
|invitee|string|受邀人|
|app_id|string|应用id|
|device_id|string|设备id|

---
## 确认邀请 接口(JWT认证)

**接口地址**
> POST /v3_1/dm_v3/enduser/invitationConfirm/

**请求示例**
```
* POST /v3_1/dm_v3/enduser/invitationConfirm/
{
	"is_accept": 1,
    "app_id": "0b4c4e80f73f11e7804bfa163e431402",
    "device_id": "6ee2d4680d8411e8804bfa163e431402"
	
}
```

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|device_id|string|yes|设备id|
|app_id|string|yes|应用id|
|is_accept|bool|yes|是否接受邀请,1(是),0(否)|

**返回参数**
{
    "meta": {
        "message": "Bind success",
        "code": 0
    },
    "data": {}
}

---
## 获取产品type_id 接口
**接口地址**
> GET /v3_1/dm_v3/enduser/product/productType/

**请求示例**
```
GET /v3_1/dm_v3/enduser/product/productType/?product_id=dlkflsdfjllds
```

**请求参数说明**

|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|product_id|string|yes|产品id|


**返回参数**
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "product_id": "5ab4642b3hpfrqd7",
        "type_id": "1102"
    }
}

**返回参数说明**

|参数|类型|说明|
|:----:|:----:|:----:|
|product_id|string|产品id|
|type_id|string|产品类型标识id|

---
## Atomi获取Token 接口 
**接口地址**
> POST /atomi/obtainToken/

**请求示例**
```
{
    "app_id": "0b4c4e80f73f11e7804bfa163e431402",
    "enduser_id":"thisisatokentestofatomi2018",
    "time_zone":"+8",
    "token": ""
}
```
**请求参数说明**

|参数 |类型|必须|说明|
|:----:|:----:|:----:|:----:|
|app_id|string|yes|应用ID|
|enduser_id|string|yes|移动端应用唯一编码|
|time_zone|string|no|时区,如时区不为+8,须携带此参数|
|token|string|yes|非首次登陆时携带token,首次登陆时token传空字符串|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbmR1c2VyX2lkIjoidGhpc2lzYXRva2VudGVzdG9mYXRvbWkyMDE4Iiwib3JpZ19pYXQiOjE1MjIwNDIxOTIsImlkZW50aWZpY2F0aW9uIjoiYXRvbWkiLCJhcHBfaWQiOiIwYjRjNGU4MGY3M2YxMWU3ODA0YmZhMTYzZTQzMTQwMiIsImV4cCI6MTUyMjY0Njk5Mn0.soanSVa22VncMuYY9Jm5Z3Nfzbn4aNn4kTKEkaAWStA",
        "enduser_id": "thisisatokentestofatomi2018"
    }
}
```
**返回参数说明**

|参数 |类型|说明|
|:----:|:----:|:----:|
|token|string|jwt认证Token|
|enduser_id|string|移动端应用唯一编码|

**错误信息说明**

|错误码|说明|
|:----:|:----:|
|10001|请求参数错误|

---
## atomi绑定设备信息更新(别名，图片) 接口(JWT认证)
**接口地址**
> PUT /atomi/boundDeviceInfo/

**请求示例**
```
{
    "device_id": "ldkgjl43t40trrefjklefje",
    "alias": "Smart Light",
    "device_image": "http://baidu.com/image/23l4k345f.png"
}
```
**请求参数说明**

|参数 |类型|必须|说明|
|:----:|:----:|:----:|:----:|
|device_id|string|yes|设备ID|
|alias|string|no|自定义设备别名|
|device_image|string|no|自定义设备图片|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    }
}
```

---
