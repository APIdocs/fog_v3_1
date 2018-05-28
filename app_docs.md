# 应用模块　接口文档

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

## 新建应用　接口

**接口地址**
> POST /v3_1/app/app_info/

**请求参数**
```
POST /v3_1/app/app_info/

{
    "app_name": "test",
    "e_name": "test",
    "package_name": "test",
    "description": "this is description for app",
    "identifier": "test",
    "extend": {},
    "language": [1,2]
}
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_name|varchar|yes|应用名称|
|e_name|varchar|yes|应用英文名称|
|package_name|varchar|yes|应用包名称|
|description|varchar|yes|应用描述|
|identifier|varchar|yes|应用标识|
|extend|dict|yes|应用扩展|
|language|list|yes|语言选择|

**返回参数**
```
{
    "meta": {
        "message": "create app successful",
        "code": 0
    },
    "data": {
        "app_name": "test",
        "e_name": "test",
        "package_name": "test",
        "description": "this is description for app",
        "identifier": "test",
        "interface": 1,
        "extend": {},
        "owner": 1,
        "language": [
        {
            "id": 2,
            "identifier": "en",
            "chinese": "英语",
            "english": "English"
        },
        {
            "id": 3,
            "identifier": "zh-hant",
            "chinese": "繁体中文",
            "english": "traditional Chinese"
        }
        ]
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_name|varchar|应用名称|
|e_name|varchar|应用英文名称|
|package_name|varchar|应用包名称|
|description|varchar|应用描述|
|identifier|varchar|应用标识|
|certificate|int|应用证书|
|extend|dict|应用扩展|
|owner|int|应用用户|
|language|list|应用语言编号|

## 获取应用详情　接口
**接口地址**
> GET /v3_1/app/app_info/

**请求参数**
```
GET /v3_1/app/app_info/?app_id=7d38d76aea1611e79918000c299d4a8e
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用编号|

**返回参数**
```
{
    "meta": {
        "message": "get app information successful",
        "code": 0
    },
    "data": {
        "app_id": "7d38d76aea1611e79918000c299d4a8e",
        "app_name": "ge power",
        "e_name": "ge power",
        "package_name": "gg.apk",
        "description": "light control app",
        "identifier": "test",
        "interface": 1,
        "certificate": 1,
        "extend": {
            "version": "1"
        },
        "owner": 1,
        "language": [
        {
            "id": 2,
            "identifier": "en",
            "chinese": "英语",
            "english": "English"
        }
        ]
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_name|varchar|应用名称|
|e_name|varchar|应用英文名称|
|package_name|varchar|应用包名称|
|description|varchar|应用描述|
|identifier|varchar|应用标识|
|interface|int|应用界面|
|certificate|int|应用证书|
|extend|dict|应用扩展|
|owner|int|应用用户|
|language|list|应用语言|

## 获取应用列表　接口 
**接口地址**
> GET /v3_1/app/app_list/

**请求参数**
```
GET /v3_1/app/app_list/
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 3,
        "next": null,
        "previous": null,
        "results": [
                        {
                "app_id": "6bdd4c4eeab111e79918000c299d4a8e",
                "app_name": "test",
                "e_name": "test",
                "package_name": "test",
                "description": "this is description for app",
                "identifier": "test",
                "interface": 1,
                "certificate": 1,
                "extend": {},
                "owner": 1,
                "language": [
                    {
                        "id": 2,
                        "identifier": "en",
                        "chinese": "英语",
                        "english": "English"
                    }
                    ]
            }
        ]
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_name|varchar|应用名称|
|e_name|varchar|应用英文名称|
|package_name|varchar|应用包名称|
|description|varchar|应用描述|
|identifier|varchar|应用标识|
|interface|int|应用界面|
|certificate|int|应用证书|
|extend|dict|应用扩展|
|owner|int|应用用户|

## 更新应用信息　接口
**接口地址**
> PUT /v3_1/app/app_info/

**请求参数**
```
PUT /v3_1/app/app_info/

{   
    "app_id": "4325fkkl",
    "app_name": "",
    "e_name": "",
    "model": "L-1",
    "package_name": "",
    "description": "",
    "identifier": "",
    "extend": {},
    "owner": null
    "language":[1,2]
}
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_name|varchar|no|应用名称|
|e_name|varchar|no|应用英文名称|
|package_name|varchar|no|应用包名称|
|description|varchar|no|应用描述|
|identifier|varchar|no|参数标识|
|extend|varchar|no|应用扩展|
|language|list|no|应用语言编号|
|model|varchar|no|产品型号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_name": "ge power",
        "e_name": "ge power",
        "model": "L-1",
        "package_name": "app.apk",
        "description": "light control app",
        "identifier": "test",
        "extend": {
            "version": "1"
        }
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_name|varchar|应用名称|
|e_name|varchar|应用英文名称|
|package_name|varchar|应用包名称|
|description|varchar|应用描述|
|identifier|varchar|参数标识|
|interface|int|应用界面|
|extend|varchar|应用扩展|
|languages|list|语言列表|
|model|varchar|产品型号|

## 获取证书 接口
**接口地址**
> GET /v3_1/app/certificate/

**请求参数**
```
GET /v3_1/app/certificate/?app_id=437ce59eec5e11e7af9b000c299d4a8e
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|是|应用ID|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 1,
        "ios_dev": "return test",
        "ios_push": "test",
        "android_secret": "test",
        "app_id": "437ce59eec5e11e7af9b000c299d4a8e",
        "updated_at": "2018-01-02T14:09:16.822813"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用ID|
|ios_dev|varchar|ios开发者证书URL链接|
|ios_push|varchar|iOS开发者推送|
|android_secret|varchar|安卓开发者证书|
|updated_at|datetime|更新证书时间|


## 上传证书 接口 
**接口地址**
> POST /v3_1/app/certificate/

**请求参数**
```
{
    "app_id":"ke543lkldfk32",
    "ios_dev":"ios developer profile",
    "ios_push":"ios push",
    "android_secret":"android_secret"
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用ID|
|ios_dev|varchar|no|IOS开发者证书URL链接|
|ios_push|varchar|no|ios推送|
|android_secret|varchar|no|android开发证书|
**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "id": 1,
        "ios_dev": "return test"
      }
}
```

## 获取语言列表 接口

**接口地址**
> GET /v3_1/app/language/

**请求参数**
```
GET /v3_1/app/language/
```

**返回参数**
```
{
    "count": 3,
    "next": null,
    "previous": null,
    "results": [
        {
            "id": 2,
            "identifier": "en",
            "chinese": "英语",
            "english": "English"
        },
        {
            "id": 3,
            "identifier": "zh-hant",
            "chinese": "繁体中文",
            "english": "traditional Chinese"
        },
        {
            "id": 1,
            "identifier": "zh-hans",
            "chinese": "简体中文",
            "english": "Chinese"
        }
    ]
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|id|int|语言编号|
|identifier|varchar|语言识别码|
|chinese|varchar|语言中文名称|
|english|varchar|语言英文名称|


## ~~获取基础语言模板列表 接口~~
**接口地址**
> GET /v3_1/app/template_base_ist/

**请求参数**
```
GET /v3_1/app/template_base_list/?language=3
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|language|int|yes|语言编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "id": 3,
            "language": 3,
            "language_code": "法语",
            "chinese": "設置",
            "english": "Settings"
        }
    ]
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|id|int|模板编号|
|language|int|语言编号|
|language_code|varchar|语言名称|
|chinese|varchar|中文模板|
|english|varchar|英语模板|


## ~~自定义应用语言模板 接口~~
**接口地址**
> POST /v3_1/app/app_language_temp/

**请求参数**
```
{
"template":
    [
        {
            
            "template_base_id":1,
            "app_id": "c3341468f1c911e7998d000c299d4a8e",
            "translate":"按鈕",
            "custom":"按鈕"
        },
    {
        "template_base_id":2,
        "app_id": "c3341468f1c911e7998d000c299d4a8e",
        "translate":"button",
        "custom":"button"
    
    }
]
}
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|template_base_id|int|yes|语言基础模板编号|
|app_id|varchar|yes|应用编号|
|translate|varchar|yes|语言翻译|
|custom|varchar|no|自定义翻译名称|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "template": [
            {
                "template_base_id": 1,
                "app_id": "c137c330f03411e7bb63000c299d4a8e",
                "translate": "按鈕",
                "custom": "按鈕"
            },
            {
                "template_base_id": 2,
                "app_id": "c137c330f03411e7bb63000c299d4a8e",
                "translate": "button",
                "custom": "button"
            }
        ]
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|


## ~~应用语言模板列表 接口~~
**接口地址**
> GET /v3_1/app/app_language_temp_list/

**请求参数**
```
GET /v3_1/app/app_language_temp_list/?app_id=c137c330f03411e7bb63000c299d4a8e&language=3
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language|int|yes|语言id|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "id": 22,
            "app_id": "c137c330f03411e7bb63000c299d4a8e",
            "language": 1,
            "language_code": "简体中文",
            "chinese": "設置",
            "english": "Settings",
            "translate": "按鈕",
            "custom": "按鈕"
        }
    ]
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|id|int|模板id|
|app_id|varchar|应用id|
|language|int|语言编号|
|language_code|varchar|语言名称|
|chinese|varchar|中文文本|
|english|varchar|英文文本|
|translate|varchar|语言翻译文本|
|custom|varchar|自定义文本|

## 获取应用图标
**接口地址**
> GET /v3_1/app/app_icon/

**请求参数**
```
GET /v3_1/app/app_icon/?app_id=3375ba62f1cd11e7998d000c299d4a8e
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "logo": "tldkflfkdlf.jpg",
        "icon": "fkldfkelgkgd33.png"
    }
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|logo|varchar|应用logo|
|icon|varchar|应用图标|

## 上传修改应用图标 接口
**接口地址**
> PUT /v3_1/app/app_icon/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "logo": "tldkflfkdlf.jpg",
        "icon": "fkldfkelgkgd33.png"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|logo|varchar|yes|应用logo|
|icon|varchar|yes|应用图标|
**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "logo": "tldkflfkdlf.jpg",
        "icon": "fkldfkelgkgd33.png"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|logo|varchar|应用logo|
|icon|varchar|应用图标|

## 新建主界面 接口
**接口地址**
> POST /v3_1/app/main_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|yes|顶部标题|
|top_style|varchar|yes|顶部样式|
|top_display|int|yes|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|yes|底部标题|
|bottom_icon|varchar|yes|底部图标|


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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 获取主界面 接口
**接口地址**
> GET /v3_1/app/main_interface/

**请求参数**
```
GET /v3_1/app/main_interface/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1
        
```

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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 更新主界面 接口
**接口地址**
> PUT /v3_1/app/main_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|no|顶部标题|
|top_style|varchar|no|顶部样式|
|top_display|int|no|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|no|底部标题|
|bottom_icon|varchar|no|底部图标|


**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|


## 新建设置界面 接口
**接口地址**
> POST /v3_1/app/settings_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|yes|顶部标题|
|top_style|varchar|yes|顶部样式|
|top_display|int|yes|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|yes|底部标题|
|bottom_icon|varchar|yes|底部图标|


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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 获取设置界面 接口
**接口地址**
> GET /v3_1/app/settings_interface/

**请求参数**
```
GET /v3_1/app/settings_interface/?app_id=3375ba62f1cd11e7998d000c299d4a8e&langauge_id=1
        
```

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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 更新设置界面 接口
**接口地址**
> PUT /v3_1/app/settings_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|no|顶部标题|
|top_style|varchar|no|顶部样式|
|top_display|int|no|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|no|底部标题|
|bottom_icon|varchar|no|底部图标|


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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|


## 新建设备管理界面 接口
**接口地址**
> POST /v3_1/app/device_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|yes|顶部标题|
|top_style|varchar|yes|顶部样式|
|top_display|int|yes|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|yes|底部标题|
|bottom_icon|varchar|yes|底部图标|


**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 获取设备管理界面 接口
**接口地址**
> GET /v3_1/app/device_interface/

**请求参数**
```
GET /v3_1/app/device_interface/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1
        
```

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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|

## 更新设备管理界面 接口
**接口地址**
> PUT /v3_1/app/device_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|top_title|varchar|no|顶部标题|
|top_style|varchar|no|顶部样式|
|top_display|int|no|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|no|底部标题|
|bottom_icon|varchar|no|底部图标|


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
        "top_title": "test",
        "top_style": "test",
        "top_display": "1",
        "bottom_title": "test",
        "bottom_icon": "no icon"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|top_title|varchar|顶部标题|
|top_style|varchar|顶部样式|
|top_display|int|是否显示顶部,0(不显示),1(显示)|
|bottom_title|varchar|底部标题|
|bottom_icon|varchar|底部图标|


## 新建帮助界面 接口
**接口地址**
> POST /v3_1/app/help_interface/

**请求参数**
```
{
"app_id":"3375ba62f1cd11e7998d000c299d4a8e",
"language_id":1,
"help_title": "Q&A",
"help_content":"1.请确认是否已连接WiFi"|
}
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|help_title|varchar|yes|帮助标题|
|help_content|varchar|yes|帮助内容|

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
        "help_title": "Q&A",
        "help_content": "1.请确认是否已连接WiFi"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|help_title|varchar|帮助标题|
|help_content|varchar|帮助内容|

## 新建帮助界面 接口
**接口地址**
> GET /v3_1/app/help_interface/

**请求参数**
```
GET /v3_1/app/help_interface/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1
```

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
        "help_title": "Q&A",
        "help_content": "1.请确认是否已连接WiFi"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|help_title|varchar|帮助标题|
|help_content|varchar|帮助内容|

## 更新 帮助界面 接口
**接口地址**
> PUT /v3_1/app/help_interface/

**请求参数**
```
{
"app_id":"3375ba62f1cd11e7998d000c299d4a8e",
"language_id":1,
"help_title": "Q&A",
"help_content":"1.请确认是否已连接WiFi"|
}
```

**请求参数说明**
|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|help_title|varchar|no|帮助标题|
|help_content|varchar|no|帮助内容|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id": "2",
        "help_title": "Feedback",
        "help_content": "If you have any question, please call 400-567-897"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int语言编号|
|help_title|varchar|帮助标题|
|help_content|varchar|帮助内容|

## 新建关于界面 接口
**接口地址**
> POST /v3_1/app/about_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "app_info": "应用XX是一款智能控制球泡灯应用，用XX应用点亮你的家，让你的家智能起来",
        "contact_title": "热线",
        "contact": "1235546464",
        "contact_display": "0",
        "website_title": "官网",
        "website": "www.google.com",
        "website_display": "1",
        "email_title": "反馈邮箱",
        "email": "hotpot@hotmail.com",
        "email_display": "1"
    }


```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|app_info|varchar|yes|应用简介|
|contact_title|varchar|yes|热线电话标题|
|contact|varchar|yes|热线电话|
|contact_display|int|yes|是否显示热线,0(不显示),1(显示)|
|website_title|varchar|yes|网站标题|
|website|varchar|yes|网站|
|website_display|varchar|yes|是否显示网站,0(不显示),1(显示)|
|email_title|varchar|yes|邮箱标题|
|email|varchar|yes|邮箱|
|email_display|int|yes|是否显示邮箱,0(不显示),1(显示)|


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
        "contact_title": "热线",
        "contact": "1235546464",
        "contact_display": "0",
        "website_title": "官网",
        "website": "www.google.com",
        "website_display": "1",
        "email_title": "反馈邮箱",
        "email": "hotpot@hotmail.com",
        "email_display": "1"
    }
}

```

**返回参数说明**

|参数|类型|说明|
|----|----|----|


## 更新关于界面 接口
**接口地址**
> PUT /v3_1/app/about_interface/

**请求参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "app_info": "应用XX是一款智能控制球泡灯应用，用XX应用点亮你的家，让你的家智能起来",
        "contact_title": "热线",
        "contact": "1235546464",
        "contact_display": "0",
        "website_title": "官网",
        "website": "www.google.com",
        "website_display": "1",
        "email_title": "反馈邮箱",
        "email": "hotpot@hotmail.com",
        "email_display": "1"
    }


```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|app_info|varchar|no|应用简介|
|contact_title|varchar|no|热线电话标题|
|contact|varchar|no|热线电话|
|contact_display|int|no|是否显示热线,0(不显示),1(显示)|
|website_title|varchar|no|网站标题|
|website|varchar|no|网站|
|website_display|varchar|no|是否显示网站,0(不显示),1(显示)|
|email_title|varchar|no|邮箱标题|
|email|varchar|no|邮箱|
|email_display|int|no|是否显示邮箱,0(不显示),1(显示)|


**返回参数**
```
{
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "app_info": "应用XX是一款智能控制球泡灯应用，用XX应用点亮你的家，让你的家智能起来",
        "contact_title": "热线",
        "contact": "1235546464",
        "contact_display": "0",
        "website_title": "官网",
        "website": "www.google.com",
        "website_display": "1",
        "email_title": "反馈邮箱",
        "email": "hotpot@hotmail.com",
        "email_display": "1"
    }


```


## 获取关于界面 接口

**接口地址**
> GET /v3_1/app/about_interface/

**请求参数**
```
GET /v3_1/app/about_interface/?app_id=3375ba62f1cd11e7998d000c299d4a8e&language_id=1

```

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
        "contact_title": "热线",
        "contact": "1235546464",
        "contact_display": "0",
        "website_title": "官网",
        "website": "www.google.com",
        "website_display": "1",
        "email_title": "反馈邮箱",
        "email": "hotpot@hotmail.com",
        "email_display": "1"
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

## 获取通用界面 接口
**接口地址**
> GET /v3_1/app/general_interface/

**请求参数**
```
GET /v3_1/app/gernaeral_interface/?app_id=337dfkljdslfjdlsklhdlfs&language_i=1

```

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
        "theme_color": "#ffffff",
        "network_button_title": "下一步"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|theme_color|varchar|主题颜色值|
|network_button_title|varchar|联网按钮标题|

## 新建通用界面 接口
**接口地址**
> POST  /v3_1/app/general_interface/

**请求参数**
```
 {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "theme_color": "#ffffff",
        "network_button_title": "下一步"
    }

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|theme_color|varchar|yes|主题颜色值|
|network_button_title|varchar|yes|联网按钮标题|
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
        "theme_color": "#ffffff",
        "network_button_title": "下一步"
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|language_id|int|语言编号|
|theme_color|varchar|主题颜色值|
|network_button_title|varchar|联网按钮标题|


## 更新通用界面 接口
**接口地址**
> PUT /v3_1/app/general_interface/

**请求参数**
```
 {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "language_id":1,
        "theme_color": "#ffffff",
        "network_button_title": "下一步"
    }

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用id|
|language_id|int|yes|语言编号|
|theme_color|varchar|no|主题颜色值|
|network_button_title|varchar|no|联网按钮标题|
**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "theme_color": "#ffffff",
        "network_button_title": "下一步",
        "language_id":1
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用id|
|theme_color|varchar|主题颜色值|
|network_button_title|varchar|联网按钮标题|
|language_id|int|yes|语言编号|


## 获取界面默认基础配置 接口
**接口地址**
> GET  /v3_1/app/interface_base/

**请求参数**
```
GET  /v3_1/app/interface_base/?interface=help&language_id=1
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|interface|varchar|yes|界面名称，可选(general,main,settings,device,about,help)|
|language_id|int|yes|语言编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "",
        "language_id": "2",
        "help_title": "Help Text for Network",
        "help_content": " 1.Make sure your device is in network configuration mode;2.Make sure the Wi-Fi password you entered is correct;3.Make sure the wireless router to which your phone is connected is a 2.4GHz network;4. Make sure the wireless router has turned off blacklist (MAC address filtering)function;5. Try to modify the wireless router advanced settings to 11bg or 20MHz bandwidth; After the network config is successful, reset the router to the original configuration;"
    }
}
```

**返回参数说明**
```javascript
返回参数对应请求界面字段
app_id字段为默认参数无实际意义
```


## 新建产品版本
**接口地址**
> POST /v3_1/app/new_version/

**请求参数**
```
{
"app_id": "3375ba62f1cd11e7998d000c299d4a8e",
"version":"1.5",
"description":"test"
}

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用编号|
|version|varchar|yes|版本编号|
|description|varchar|yes|版本描述|

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


##  应用版本列表 接口
**接口地址**
> GET /v3_1/app/version_list/

**请求参数**
```
GET /v3_1/app/version_list/?app_id=
```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": [
        {
            "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
            "version": "1.5",
            "created_at": "2018-02-05 09:57:54",
            "status": "0"
        },
        {
            "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
            "version": "1.3",
            "created_at": "2018-02-02 17:45:04",
            "status": "1"
        }
    ]
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用编号|
|version|varchar|应用编号|
|created_at|datetime|创建时间|
|status|varchar|版本状态, (0, "已生成"), (1, "正在生成"), (2, "异常")|

## 应用版本详情 接口
**接口地址**
> GET /v3_1/app/version_info/

**请求参数**
```
GET /v3_1/app/version_info/?app_id=&version=

```

**请求参数说明**

|参数|类型|必须|说明|
|----|----|----|----|
|app_id|varchar|yes|应用编号|
|version|varchar|yes|版本编号|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "app_id": "3375ba62f1cd11e7998d000c299d4a8e",
        "version": "1.0",
        "created_at": "2018-02-02 17:02:30",
        "status": 1,
        "app_info": null,
        "app_interface": null,
        "app_certificate": null
    }
}
```

**返回参数说明**

|参数|类型|说明|
|----|----|----|
|app_id|varchar|应用编号|
|version|varchar|版本编号|
|app_info|json|产品信息|
|app_interface|json|产品界面配置|
|app_certificate|json|产品证书配置|
|created_at|datetime|创建时间|



