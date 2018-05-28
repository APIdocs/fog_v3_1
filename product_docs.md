# 产品模块 接口文档

## 新建产品 接口
**接口地址**

> POST /v3_1/product/product_info/
 
 **请求参数示例**
 ```
{
    "name": "colorful_light",
    "model": "L-001",
    "description": "colorful light product",
    "network": 0,
    "category": 1,
    "app": 1,
    "owner": 1,
    "version": 1,
        "extend": {
            "extend": "none"
        }
}

```

**请求参数说明**
| 参数 | 类型 | 必须 | 说明 |
| ---- | ---- | ---- | ---- |
|name|varchar|是|产品名称|
|model|varchar|no|产品型号|
|description|varchar|是|产品描述|
|network|varchar|no|联网方式|
|category|int|是|产品类别|
|app|int| 是|产品所属应用|
version|int|是|产品版本|


**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "name": "test",
        "model": "test",
        "description": "first product light",
        "network": 0,
        "category": 1,
        "app": "1",
        "owner": 1,
        "version": 1,
        "extend": {
            "extend": "none"
        }
    }
}
```

## 更新产品　接口

**接口地址**

> PUT /v3_1/product/product_info/

**请求参数示例**
```
 {
        "name": "test",
        "model": "test",
        "description": "first product light",
        "network": 0,
        "category": 1,
        "status":0,
        "picture":"http://baidu.com/image/4354543634.jpg"

    }
```
**请求参数说明**
| 参数　| 类型 | 必须 | 说明 |
| ---- | ---- | ---- | ----|
|name|varchar|否|产品名称|
|model|varchar|否|产品型号|
|description|varchar|否|产品秒速|
|network|int|否|产品联网方式，0(wifi),1(buletooth)|
|category|int|否|产品类别|
|status|int|否|产品状态，0(开发中),1(已上线),2(审核中)|
|picture|varchar|no|产品图片url|

**返回参数**
```
{
    "meta": {
        "code": 0,
        "mesage": "ok"
    },
    "data": {
        "name": "music control light",
        "model": "ML-01",
        "description": "first product light",
        "network": 0,
        "category": "台灯",
        "status": "1",
        "product_id": "67da0c26e61b11e79918000c299d4a8e",
        "picture":"http://baidu.com/kdlfjdlfldslfld.png"
        
    }
}

```

## 获取产品详情接口

**接口地址**
> GET /v3_1/product/prodct_info/

**请求示例**
```
GET /v3_1/product/product_info/?product_id=67da0c26e61b11e79918000c299d4a8e
```

**请求参数**
| 参数　| 类型 | 必须 | 说明 |
| ---- | ---- | ---- | ----|
|product_id|varchar|是|产品ID|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "name": "music control light",
        "model": "ML-01",
        "description": "first product light",
        "network": "0",
        "category": "台灯",
        "version": "1",
        "product_id": "67da0c26e61b11e79918000c299d4a8e",
        "status":"0"
    }
}
```

**返回参数说明**
| 参数　| 类型 | 必须 | 说明 |
| ---- | ---- | ---- | ----|
|product_id|varchar|否|产品ID|
|name|varchar|否|产品名称|
|model|varchar|否|产品型号|
|description|varchar|否|产品描述|
|network|int|否|产品联网方式，0(wifi),1(buletooth)|
|category|int|否|产品类别|
|status|int|否|产品状态，0(开发中),1(已上线),2(审核中)|


## 获取产品列表　接口

**接口地址**
> GET /v3_1/product/product_list/

**请求示例**
```
GET /v3_1/product/product_list/?app_id=fdlgjkl566
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 1,
        "next": null,
        "previous": null,
        "results": [
            {
                "name": "colorful light",
                "model": "CL-01",
                "description": "light will change with the color",
                "network": "0",
                "category": "台灯",
                "version": "1",
                "extend": {
                    "extend": "none"
                },
                "product_id": "3e9a81d6e6c211e79918000c299d4a8e",
                "status": "0"
            }            
        ]
    }
}
```

** 返回参数说明**
|参数|类型|说明|
|----|----|----|
|name|varchar|产品名称|
|model|varchar|产品类型|
|description|varchar|产品描述|
|network|varchar|产品连网方式|
|category|varchar|产品类别|
|version|int|产品版本|
|extend|dict|产品扩展|
|product_id|varchar|产品ID|
|status|varchar|产品状态|

## 获取产品种类　接口

**接口地址**
> GET /v3_1/product/product_class_list/

**请求示例**
```
GET /v3_1/product/product_class_list/
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
            "id": 1,
            "class_name": "灯"
        },
        {
            "id": 2,
            "class_name": "灯"
        }
    ]
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|class_name|varchar|产品类别名称|


## 获取产品子类　接口

**接口地址**
> GET /v3_1/product/product_subclass_list/

**请求示例**
```
GET /v3_1/product/product_class_list/?class_id=1
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
            "id": 1,
            "class_name": "灯",
            "subclass_name": "台灯"
        }
    ]
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|class_name|varchar|产品所属类别名称|
|subclass_name|varchar|产品所属子类名称|


## 获取产品类别详情　接口

**接口地址**
> GET /v3_1/product/product_class_info/

**请求示例**
```
GET /v3_1/product/product_class_info/?class_id=1
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": 
        {
            "id": 1,
            "class_name": "灯",
            "subclass_name": "台灯"
        }
    
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|class_name|varchar|产品所属类别名称|
|subclass_name|varchar|产品所属子类名称|


## 新建产品功能　接口

**接口地址**
> POST /v3_1/product/function_info/

**请求示例**
```
POST /v3_1/product/function_info/

{
    "indentifier": "test",
    "name": "switch",
    "e_name": "switch",
    "data_type": "int32",
    "min_value": "0",
    "max_value": "1",
    
}
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|identifier|varchar|是|参数标识|
|name|varchar|是|功能名称|
|e_name|varchar|是|功能字段|
|data_type|varchar|是|数据类型|
|min_value|varchar|是|最小参数值|
|max_value|varchar|是|最大参数值|

**返回参数**
```
{
    "id":1,
    "indentifier": "test",
    "name": "switch",
    "e_name": "switch",
    "data_type": "int32",
    "min_value": "0",
    "max_value": "1",
    
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|identifier|varchar|参数标识|
|name|varchar|功能名称|
|e_name|varchar|功能字段|
|data_type|varchar|数据类型|
|min_value|varchar|最小参数值|
|max_value|varchar|最大参数值|


## 更新产品功能　接口

**接口地址**
> PUT /v3_1/product/function_info/

**请求示例**
```
PUT /v3_1/product/function_info/?function_id=1

{
    "indentifier": "test",
    "name": "switch",
    "e_name": "switch",
    "data_type": "int32",
    "min_value": "0",
    "max_value": "1",
    
}
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|identifier|varchar|否|参数标识|
|name|varchar|否|功能名称|
|e_name|varchar|否|功能字段|
|data_type|varchar|否|数据类型|
|min_value|varchar|否|最小参数值|
|max_value|varchar|否|最大参数值|

**返回参数**
```
{
    "id":1,
    "indentifier": "test",
    "name": "switch",
    "e_name": "switch",
    "data_type": "int32",
    "min_value": "0",
    "max_value": "1",
    
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|identifier|varchar|参数标识|
|name|varchar|功能名称|
|e_name|varchar|功能字段|
|data_type|varchar|数据类型|
|min_value|varchar|最小参数值|
|max_value|varchar|最大参数值|


## 查看产品功能详情　接口

**接口地址**
> GET /v3_1/product/function_info/?function_id=[id]

**请求示例**
```
GET /v3_1/product/function_info/?function_id=1
```

**返回参数**
```
{
    "id":1,
    "indentifier": "test",
    "name": "switch",
    "e_name": "switch",
    "data_type": "int32",
    "min_value": "0",
    "max_value": "1",
    
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|identifier|varchar|参数标识|
|name|varchar|功能名称|
|e_name|varchar|功能字段|
|data_type|varchar|数据类型|
|min_value|varchar|最小参数值|
|max_value|varchar|最大参数值|


## 查看产品功能列表　接口
**接口地址**
> GET /v3_1/product/function_list/

**请求示例**
```
GET /v3_1/product/function_list/?version_id=1
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
            "function": [
                {
                    "id": 14,
                    "identifier": "test",
                    "name": "test",
                    "e_name": "test",
                    "data_type": "int32",
                    "min_value": null,
                    "max_value": null,
                    "attributes": {}
                },
                {
                    "id": 15,
                    "identifier": "switch",
                    "name": "switch",
                    "e_name": "switch",
                    "data_type": "uint32",
                    "min_value": "0.00",
                    "max_value": "1.00",
                    "attributes": {}
                }
            ]
        }
    ]
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|id|int|产品类别编号|
|identifier|varchar|参数标识|
|name|varchar|功能名称|
|e_name|varchar|功能字段|
|data_type|varchar|数据类型|
|min_value|varchar|最小参数值|
|max_value|varchar|最大参数值|
|attributes|dict|功能属性|

## 删除产品功能　接口

**接口地址**
> DELETE /v3_1/product/function_info/

**请求示例**
```

DELETE /v3_1/product/function_info/?function_id=1

```

**返回参数**
```
{
     "meta": {
        "message": "删除成功",
        "code": 0
    },
    "data": {}
}
```

## 获取产品版本列表 接口
**接口地址**
> GET /v3_1/product/product_version_list/

**请求示例**
```
GET /v3_1/product/product_version_list/?category=5
```

**请求参数**
|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|category|int|yes|产品类别id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "id": 1,
            "version": "公版版本"
        },
        {
            "id": 2,
            "version": "私有定制"
        }
    ]
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|版本ID|
|version|varchar|版本名称|


## 产品版本详情 接口
**接口地址**
> GET /v3_1/product/product_version_info/

**请求参数**
```
GET /v3_1/product/product_version_info/?version_id=1
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 1,
        "version": "公版版本",
        "is_common": 1,
        "category": null,
        "qkb_module": null,
        "function": []
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|版本ID|
|version|varchar|版本名称|
|is_common|int|是否是公版|
|function|list|功能点列表|
|qkb_module|varchar|庆科模块信息|
|description|varchar|版本描述|


## 获取区域列表 接口
**接口地址**
> GET /v3_1/product/region_list/

**请求参数**
```
GET /v3_1/product/region_list/
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
            "id": 1,
            "domain": "103.235.46.39",
            "region": "中国"
        },
        {
            "id": 2,
            "domain": "103.235.46.40",
            "region": "中东东部"
        }
    ]
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|地区id|
|domain|varchar|地区节点|
|region|varchar|地区名称|

## 产品区域选择 接口
**接口地址**
> POST /v3_1/product/product_region/

**请求参数**
```
POST /v3_1/product/product_region/

{
    "product_id": "7405d040f9bf11e7998d000c299d4a8e",
    "region":[1,3]
}
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|product_id|varchar|yes|产品id|
|region|list|yes|产品地区|

**返回参数**
```
{
    "meta": {
        "message": "Ok",
        "code": 0
    },
    "data": {}
}
```


## 获取产品的区域详情 接口
**接口地址**
> GET /v3_1/product/product_region_info/

**请求参数**
```
GET /v3_1/product/product_region_info/?product_id=7405d040f9bf11e7998d000c299d4a8e
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|product_id|varchar|yes|产品id|
**返回参数**
```
{
    "meta": {
        "message": "Ok",
        "code": 0
    },
    "data": {
        "region": [
            {
                "id": 1,
                "domain": "103.235.46.39",
                "region": "中国"
            },
            {
                "id": 2,
                "domain": "103.235.46.40",
                "region": "中东东部"
            }
        ],
        "product_id": "7405d040f9bf11e7998d000c299d4a8e"
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|product_id|varchar|产品id|
|id|int|地区id|
|region|varchar|产品地区|
|domain|varchar|区域节点|


## 获取庆科模块列表 接口
**接口地址**
> GET /v3_1/product/qingke_module/

**请求示例**
```
GET /v3_1/product/qingke_module/
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
            "id": 1,
            "model": "EMW3060",
            "format": "120*240",
            "name": "EMW3060",
            "image": null,
            "description": "EMW3060",
            "feature": [
                "flask:2M",
                "RAM:256k"
            ],
            "price": null
        }
    ]
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|模块id|
|model|varchar|模块型号|
|format|varchar|模块规格|
|name|varchar|模块名称|
|image|varchar|产品图片url|
|description|varchar|模块描述|
|feature|list|模块特性|
|price|varchar|模块单价|


## 产品量产提交工单 接口
**接口地址**
> POST /v3_1/product/production/

**请求参数**
```
1.购买云模块参数
{

"type":"module",
"module":"EMW3060",
"amount":1000,
"company":"test",
"contact":"admin",
"cellphone":"1372156232256",
"location":"210000",
"address": "上海市普陀区金沙江路256号"

}
2.量产技术支持参数
{

"type":"tech",
"company":"test",
"contact":"admin",
"cellphone":"1372156232256",
"email":"wongkeqing@mxchip.com",
"location":"210000",
"address": "上海市普陀区金沙江路256号"

}
3.量产测试支持参数
{

"type":"test",
"company":"test",
"contact":"admin",
"cellphone":"1372156232256",
"email":"wongkeqing@mxchip.com",
"location":"210000",
"address": "上海市普陀区金沙江路256号"

}
4.语音支持参数
3.量产测试支持参数
{

"type":"voice",
"company":"test",
"contact":"admin",
"cellphone":"1372156232256",
"email":"wongkeqing@mxchip.com",
"address": "上海市普陀区金沙江路256号"

}
请求根据type的不同，请求参数不同
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|type|varchar|yes|提交量产工单类型,("module","购买云模块"),("test","测试支持"),("tech","技术支持")|
|module|varchar|no|云模块型号, 当类型是module时，该参数为必须|
|amount|int|no|购买云模块数量, 当类型是module时，该参数为必须|
|company|varchar|yes|公司名称|
|contact|varchar|yes|联系人|
|cellphone|varchar|yes|联系电话|
|location|varchar|no|量产地区|
|email|varchar|yes|联系邮箱|
|address|varchar|no|联系地址|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "module": null,
        "amount": null,
        "company": "test",
        "contact": "admin",
        "cellphone": "1372156232256",
        "location": "210000",
        "email": "wongkeqing@mxchip.com",
        "address": "上海市普陀区金沙江路256号",
        "type": "test"
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|type|varchar|提交量产工单类型,("module","购买云模块"),("test","测试支持"),("tech","技术支持"),("voice", "语音支持")|
|module|varchar|云模块型号, 当类型是module时，该参数为必须|
|amount|int|购买云模块数量, 当类型是module时，该参数为必须|
|company|varchar|公司名称|
|contact|varchar|联系人|
|cellphone|varchar|联系电话|
|location|varchar|量产地区|
|email|varchar|联系邮箱|
|address|varchar|联系地址|


## 查看语音支持状态 接口
**接口地址**
> GET /v3_1/product/voice_support/

**请示例数**
```
GET /v3_1/product/voice_support/?product_id=90909gfd90fdfdo0304
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|product_id|varchar|yes|产品id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "ali_genie": 0,
        "aws_echo": 2,
        "google_home":0,
        "product_id": "fdlkej043tret4t9rjfdl"
        }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|ali_genie|int|支持天猫精灵, 1(开通)， 0(关闭),2(开通中)|
|aws_echo|int|支持aws echo音箱, 1(开通)， 0(关闭),2(开通中)|
|google_home|int|支持google home音箱, 1(开通)， 0(关闭),2(开通中)|
|product_id|varchar|产品id|

## 开通关闭以产品语音支持 接口
**接口地址**
> PUT /v3_1/product/voice_support/

**请求参数**
```
{
    "product_id": "jflgsjfkj3456f",
    "voice_status":1,
    "voice_vendor": "aws_echo"
    }

```
* voice_vendor 对应要开通的语音供应商

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|voice_status|int|yes|支持google home音箱, 1(开通)， 0(关闭)|
|product_id|varchar|yes|产品id|
|voice_vendor|varchar|yes|语音供应商|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "ali_genie": 0,
        "aws_echo": 2,
        "google_home":0,
        "product_id": "fdlkej043tret4t9rjfdl"
        }
}

```

* 返回码为10170,代表first开通,提醒提交工单

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|ali_genie|int|支持天猫精灵, 1(开通)， 0(关闭),2(开通中)|
|aws_echo|int|支持aws echo音箱, 1(开通)， 0(关闭),2(开通中)|
|google_home|int|支持google home音箱, 1(开通)， 0(关闭),2(开通中)|
|product_id|varchar|产品id|


## 查看帮助支持列表 接口
**接口地址**
> GET /v3_1/product/help_support/

**请求参数**
```
GET /v3_1/product/help_support/?product_id=43255fdklfgl34jklrl44
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|product_id|varchar|yes|产品id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 2,
        "page_size": 15,
        "next": null,
        "previous": null,
        "results": [
            {
                "id": 6,
                "subject": "产品类型",
                "status": "draft"
            },
            {
                "id": 4,
                "subject": "配网失败原因",
                "status": "publish"
            }
        ]
    }
}

```
* 分页需携带page和page_size参数

**返回参数说明**
|参数|类型|说明|
|----|----|----|


## 新建产品帮助支持 接口
**接口地址**
> POST /v3_1/product/help_support/

**请求参数**
```
{
	"product_id":"09646efef9a111e7998d000c299d4a8e",
	"subject": "怎么使用Echo音响控制灯？",
	"detail":"1.首先你得买一款echo音响；2.你需要学习alexa得发音",
	"status": "publish"

}


```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|product_id|varchar|yes|产品id|
|subject|varchar|yes|帮助主题|
|detail|varchar|yes|帮助得详情说明|
|status|varchar|yes|帮助支持得发布状态，draft(草稿), publish(发布)|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 7,
        "subject": "怎么使用Echo音响控制灯？",
        "detail": "1.首先你得买一款echo音响；2.你需要学习alexa得发音",
        "status": "publish"
    }
}
```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|帮助信息id|
|subject|varchar|帮助主题|
|detail|varchar|帮助详情说明|
|status|varchar|帮助支持发布状态，draft(草稿), publish(发布)|


## 获取帮助支持详情 接口
**接口地址**
> GET /v3_1/product/help_support/[id]/

**请求示例**
```
GET /v3_1/product/help_support/7/
```
**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|id|int|yes|帮助信息id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 7,
        "subject": "怎么使用Echo音响控制灯？",
        "detail": "1.首先你得买一款echo音响；2.你需要学习alexa得发音",
        "status": "publish"
    }
}

```

**返回参数说明**
|参数|类型|说明|
|----|----|----|
|id|int|帮助信息id|
|subject|varchar|帮助主题|
|detail|varchar|帮助详情说明|
|status|varchar|帮助支持发布状态，draft(草稿), publish(发布)|

## 更新帮助信息状态 接口
**接口地址**
> PUT /v3_1/product/help_support/[id]/

**请求参数**
```
{
    "status": "draft"
}
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|status|varchar|yes|帮助支持发布状态，draft(草稿), publish(发布)|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 7,
        "subject": "怎么使用Echo音响控制灯？",
        "status": "draft"
    }
}
```

## 删除帮助支持 接口
**接口地址**
> DELETE /v3_1/product/help_support/[id]/?product_id=delkf3lfgl

**请求示例**
```
DELETE /v3_1/product/help_support/6/?product_id=delkf31fg1
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|id|int|yes|帮助编号|
|product_id|varchar|yes|产品id|

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


