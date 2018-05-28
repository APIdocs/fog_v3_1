# Atomi API Document
* host: https://cnapitest.fogcloud.io
* api_prefix: /v3_1/dm_v3/
* url: host+api_prefix+api
## 获取Token 接口 
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

## 绑定设备信息更新(别名，图片) 接口(JWT认证)
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


   
