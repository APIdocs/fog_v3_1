# 统计模块 接口文档
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


## 统计概览 接口
**接口地址**
> GET /v3_1/statistics/overview/

**请求示例**
```
> GET /v3_1/statistics/overview/
```

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "device": {
            "active_device_trend": [
                {
                    "2018.02.07": 0
                },
                {
                    "2018.02.06": 0
                },
                {
                    "2018.02.05": 0
                },
                {
                    "2018.02.04": 0
                },
                {
                    "2018.02.03": 0
                },
                {
                    "2018.02.02": 0
                },
                {
                    "2018.02.01": 1
                }
            ],
            "active_devices": 3,
            "yesterday_active_devices": 0
        },
        "data": {
            "yesterday_data": 20,
            "total_data": 100
        },
        "user": {
            "register_user_trend": [
                {
                    "2018.02.07": 0
                },
                {
                    "2018.02.06": 0
                },
                {
                    "2018.02.05": 0
                },
                {
                    "2018.02.04": 0
                },
                {
                    "2018.02.03": 0
                },
                {
                    "2018.02.02": 0
                },
                {
                    "2018.02.01": 0
                }
            ],
            "register_users": 0,
            "yesterday_register_users": 0
        }
    }
}
```

**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|active_devices|int|激活设备数量|
|yesterday_active_devices|int|昨天激活设备数量|
|active_device_trend|list|7天激活设备趋势|
|register_users|int|注册用户数量|
|yesterday_register_users|int|昨天注册用户数量|
|register_user_trend|list|7天注册用户趋势|
|total_data|int|累计产生数据|
|yesterday_data|int|昨天数据新增|

## 数据概览 设备分布 接口
**接口地址**
> GET /v3_1/statistics/overview/device_map/

**请求示例**
```
GET /v3_1/statistics/overview/device_map/
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
            "count": 2,
            "location": "310000"
        },
        {
            "count": 1,
            "location": "510100"
        }
    ]
}

```

**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|location|string|位置编码|
|count|int|设备总数|


## 设备 激活统计 接口
**接口地址**
> GET /v3_1/statistics/activation_count/

**请求示例**
```
GET /v3_1/statistics/activation_count/?start_date=2017-12-30&end_date=2018-02-06&product_id=flglkkd
```

**请求参数说明**
|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|product_id|varchar|no|产品编号,无product_id参数表示所有产品,多个产品需携多个产品ID|
|start_date|varchar|yes|起始日期,格式:2018-01-01|
|end_date|varchar|yes|结束日期,格式:2018-02-01|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": {
            "a85474c6f50c11e7998d000c299d4a8e": {
                "2018-02-01": 1,
            },
            "7405d040f9bf11e7998d000c299d4a8e": {
                "2018-01-16": 2
            }
        },
        "avg_day_count": 0
    }
}
```

**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|count|int|各产品每日激活设备数,数据结构为{产品:{日期:激活设备数量}}|
|avg_day_count|int|平均每天激活设备数|


## 设备 激活统计列表 接口
**接口地址**
> GET /v3_1/statistics/activation_list/

**请求示例**
```
GET /v3_1/statistics/activation_list/?page=1&page_size=10&product_id=flglkkd&product_id=435fdgdg
```

**请求参数说明**
|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|product_id|varchar|no|产品编号,无product_id参数表示所有产品,多个产品需携带多个产品ID|
|page|int|no|页码,最大为10页,默认为1|
|page_size|int|no|每页数量,默认为10|

**返回参数**
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "2018-02-04": {
            "total": 3,
            "day_count": 0
        },
        "2018-02-03": {
            "total": 3,
            "day_count": 0
        },
        "2018-02-02": {
            "total": 3,
            "day_count": 0
        },
        "2018-02-01": {
            "total": 3,
            "day_count": 1
        },
        "2018-01-31": {
            "total": 2,
            "day_count": 0
        }
    }
}
```

**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|day_count|int|产品每日激活设备数|
|total|int|产品累计激活设备数|


## 地区统计 接口
**接口地址**
> GET /v3_1/statistics/region_count/

**请求示例**
* 设备分布地图统计
```
GET /v3_1/statistics/region_count/?product_id=lfkdslf4kj&type=count
```
* 设备分布详情
```
GET /v3_1/statistics/region_count/?product_id=ldkjgk32254dfk&type=detail&page=1&page_size=10
```

**请求参数说明**
|参数|类型|必须|说明|
|:----:|:----:|:----:|:----:|
|product_id|varchar|no|产品编号,无product_id参数表示所有产品|
|type|varchar|yes|请求类型,count(设备分布统计),detail(设备分布详情)|
|page|int|no|页码|
|page_size|int|no|页码数量|
**返回参数**
* 设备分布地图统计
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "data": [
            {
                "count": 2,
                "location": "510100"
            },
            {
                "count": 1,
                "location": "440100"
            },
            {
                "count": 1,
                "location": "320100"
            },
            {
                "count": 1,
                "location": "330100"
            },
            {
                "count": 2,
                "location": "310000"
            },
            {
                "count": 1,
                "location": "321000"
            }
        ]
    }
}
```
* 设备分布详情
```
{
    "meta": {
        "message": "ok",
        "code": 0
    },
    "data": {
        "count": 5,
        "previous": null,
        "results": [
            {
                "count": 2,
                "percentage": 0.38,
                "location": "320000"
            },
            {
                "count": 2,
                "percentage": 0.25,
                "location": "510000"
            }
        ],
        "page_size": 2,
        "next": true
    }
```


**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|location|string|地区编码|
|count|int|地区设备总数|
|percentage|float|地区设备分布量百分比|


##  激活统计 产品列表 接口
**接口地址**
> GET /v3_1/statistics/product_list/

**请求示例**
```
GET /v3_1/statistics/product_list/
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
            "name": "test7",
            "product_id": "7405d040f9bf11e7998d000c299d4a8e"
        },
        {
            "name": "test5",
            "product_id": "09646efef9a111e7998d000c299d4a8e"
        },
        {
            "name": "test2",
            "product_id": "ec9a7a88f99c11e7998d000c299d4a8e"
        }
    ]
}

```

**返回参数说明**
|参数|类型|说明|
|:----:|:----:|:----:|
|name|varchar|产品名称|
|product_id|varchar|产品编号|
