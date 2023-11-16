---
title: 公益 API 接口
abbrlink: d6469eb3
date: 2023-11-14 21:12:31
tags:
  - API
categories:
  - 科技前沿
top_img: 'https://s3.qjqq.cn/37/6555af8930dec.webp!color'
cover: 'https://s3.qjqq.cn/37/6555af8930dec.webp!color'
ai:
  - 致力于为用户提供稳定、快速的免费API数据接口服务。公益API接口为社会服务提供数据支持，包括慈善机构信息、捐赠统计等，促进公益信息传递与分享，推动社会公益事业发展。
---
- 引用
{% link 青桔 api,青桔-API，我们致力于为用户提供稳定、快速的免费API数据接口服务。,https://api.qjqq.cn/,https://api.qjqq.cn/assets/img/favicons/favicon.ico %}

# 一、获取IP信息（IPv4/IPv6）
- 接口详情 获取IP信息（IPv4/IPv6）
  
|             接口地址             | 请求方法 | 返回格式 |
| :------------------------------: | :------: | :------: |
| https://api.qjqq.cn/api/district |   GET    |   JSON   |

- 请求参数说明

  

| 名称 | 必填 |  类型  |  说明  |
| :--: | :--: | :----: | :----: |
|  ip  |  是  | string | IP地址 |

- 返回示例

``` json
{
    "code": "Success",
    "data": {
        "continent": "亚洲",
        "country": "中国",
        "owner": "中国联通",
        "isp": "中国联通",
        "zipcode": "200240",
        "timezone": "UTC+8",
        "accuracy": "区县",
        "source": "数据挖掘",
        "areacode": "CN",
        "adcode": "310112",
        "asnumber": "17621",
        "lat": "31.089290",
        "lng": "121.413921",
        "radius": "22.6397",
        "prov": "上海市",
        "city": "上海市",
        "district": "闵行区"
    },
    "charge": false,
    "msg": "查询成功",
    "ip": "112.64.62.37",
    "coordsys": "WGS84"
}
```

- 返回参数说明

|      名称      |  类型   |       说明       |      |
| :------------: | :-----: | :--------------: | ---- |
|      code      | string  |      状态码      |      |
|      data      | object  |   结果数据对象   |      |
| data.continent | string  |       大洲       |      |
|  data.country  | string  |       国家       |      |
|   data.owner   | string  |      所有者      |      |
|    data.isp    | string  | 互联网服务提供商 |      |
|  data.zipcode  | string  |     邮政编码     |      |
| data.timezone  | string  |       时区       |      |
| data.accuracy  | string  |      精确度      |      |
|  data.source   | string  |     数据来源     |      |
| data.areacode  | string  |     区域代码     |      |
|  data.adcode   | string  |   行政区划代码   |      |
| data.asnumber  | string  |   自治系统号码   |      |
|    data.lat    | string  |       纬度       |      |
|    data.lng    | string  |       经度       |      |
|  data.radius   | string  |       半径       |      |
|   data.prov    | string  |       省份       |      |
|   data.city    | string  |       城市       |      |
| data.district  | string  |       区县       |      |
|     charge     | boolean |     是否收费     |      |
|      msg       | string  |     返回消息     |      |
|       ip       | string  |      IP地址      |      |
|    coordsys    | string  |     坐标系统     |      |

- 代码示例

``` 
https://api.qjqq.cn/api/district?ip=2408:820c:681b:5ad0:585f:2fc:346a:4bb4
```

# 二、随机图
- 接口详情 随机图
| 接口地址                    | 请求方法 | 返回格式   |
| --------------------------- | -------- | ---------- |
| https://api.qjqq.cn/api/Img | GET      | image/jpeg |

- 请求参数说明

  

| 名称 | 必填 |  类型  | 说明 |
| :--: | :--: | :----: | :--: |
| acg  |  是  | string | 动漫 |

- 返回示例

``` 
返回为图片
```

- 返回参数说明

| 名称 |  类型  |  说明  |
| :--: | :----: | :----: |
| 200  | string | 状态码 |

- 代码示例

``` 
https://api.qjqq.cn/api/Img（默认）
https://api.qjqq.cn/api/Img?category=acg（动漫）
```



# 三、获取图片的主题色
- 接口详情 获取图片的主题色
| 接口地址                         | 请求方法 | 返回格式 |
| -------------------------------- | -------- | -------- |
| https://api.qjqq.cn/api/Imgcolor | GET      | JSON     |



- 请求参数说明

  

| 名称 | 必填 |  类型  |             说明             |
| :--: | :--: | :----: | :--------------------------: |
|  qq  |  是  | string | 需要获取的QQ，如：2922619853 |

- 返回示例

``` 
{"RGB":"#545368"}
```

- 返回参数说明

| 名称 |  类型  |  说明  |
| :--: | :----: | :----: |
| code | string | 状态码 |

- 代码示例

``` 
https://api.qjqq.cn/api/Imgcolor?img=URL
```

# 四、获取客户端IP信息（IPv4/IPv6）
- 用于获取指定IPv4/IPv6地址的详细信息-由腾讯提供
- 接口详情 获取客户端IP信息（IPv4/IPv6）
| 接口地址                     | 请求方法 | 返回格式 |
| ---------------------------- | -------- | -------- |
| https://api.qjqq.cn/api/Info | GET      | JSON     |



- 请求参数说明

  

| 名称 | 必填 |  类型  | 说明 |
| :--: | :--: | :----: | :--: |
|  无  |  否  | string |  无  |

- 返回示例

``` json
{
    "status": 0,
    "message": "Success",
    "request_id": "775ba6ff2df047ffb3c99ccdd94352a0",
    "result": {
        "ip": "180.158.11.237",
        "location": {
            "lat": 31.11325,
            "lng": 121.38206
        },
        "ad_info": {
            "nation": "中国",
            "province": "上海市",
            "city": "上海市",
            "district": "闵行区",
            "adcode": 310112,
            "nation_code": 156
        }
    }
}
```

- 返回参数说明

|            名称            |  类型   |     说明     |
| :------------------------: | :-----: | :----------: |
|           status           | integer |    状态码    |
|          message           | string  |   返回消息   |
|         request_id         | string  |    请求ID    |
|           result           | object  | 结果数据对象 |
|         result.ip          | string  |    IP地址    |
|      result.location       | object  |   位置信息   |
|    result.location.lat     |  float  |     纬度     |
|    result.location.lng     |  float  |     经度     |
|       result.ad_info       | object  |   地区信息   |
|   result.ad_info.nation    | string  |     国家     |
|  result.ad_info.province   | string  |     省份     |
|    result.ad_info.city     | string  |     城市     |
|  result.ad_info.district   | string  |    区/县     |
|   result.ad_info.adcode    | string  | 行政区划代码 |
| result.ad_info.nation_code | integer |   国家代码   |

- 代码示例

``` 
https://api.qjqq.cn/api/Info
```

# 五、获取客户端IP信息（IPv4/IPv6）
- 获取本机IP信息（IPv4/IPv6）-数据由埃文科技提供
- 接口详情 获取客户端IP信息（IPv4/IPv6）
| 接口地址                      | 请求方法 | 返回格式 |
| ----------------------------- | -------- | -------- |
| https://api.qjqq.cn/api/Local | GET/POST | JSON     |



- 请求参数说明

  

| 名称 | 必填 |  类型  | 说明 |
| :--: | :--: | :----: | :--: |
|  无  |  否  | string |  无  |

- 返回示例

``` json
{
    "code": "Success",
    "data": {
        "continent": "亚洲",
        "country": "中国",
        "owner": "中国联通",
        "isp": "中国联通",
        "zipcode": "200240",
        "timezone": "UTC+8",
        "accuracy": "区县",
        "source": "数据挖掘",
        "areacode": "CN",
        "adcode": "310112",
        "asnumber": "17621",
        "lat": "31.089290",
        "lng": "121.413921",
        "radius": "22.6397",
        "prov": "上海市",
        "city": "上海市",
        "district": "闵行区"
    },
    "charge": false,
    "msg": "查询成功",
    "ip": "112.64.62.37",
    "coordsys": "WGS84"
}
```

- 返回参数说明

|      名称      |  类型   |       说明       |
| :------------: | :-----: | :--------------: |
|      code      | string  |      状态码      |
|      data      | object  |   结果数据对象   |
| data.continent | string  |       大洲       |
|  data.country  | string  |       国家       |
|   data.owner   | string  |      所有者      |
|    data.isp    | string  | 互联网服务提供商 |
|  data.zipcode  | string  |     邮政编码     |
| data.timezone  | string  |       时区       |
| data.accuracy  | string  |      精确度      |
|  data.source   | string  |     数据来源     |
| data.areacode  | string  |     区域代码     |
|  data.adcode   | string  |   行政区划代码   |
| data.asnumber  | string  |   自治系统号码   |
|    data.lat    | string  |       纬度       |
|    data.lng    | string  |       经度       |
|  data.radius   | string  |       半径       |
|   data.prov    | string  |       省份       |
|   data.city    | string  |       城市       |
| data.district  | string  |       区县       |
|     charge     | boolean |     是否收费     |
|      msg       | string  |     返回消息     |
|       ip       | string  |      IP地址      |
|    coordsys    | string  |     坐标系统     |

- 代码示例

``` 
https://api.qjqq.cn/api/Local
```


# 六、米游社随机头像
- 接口详情 米游社随机头像
| 接口地址                         | 请求方法 | 返回格式   |
| -------------------------------- | -------- | ---------- |
| https://api.qjqq.cn/api/MiYouShe | GET      | image/jpeg |



- 请求参数说明

  

|   名称    | 必填 |  类型  |   说明   |
| :-------: | :--: | :----: | :------: |
|  绝区零   |  否  | string | 头像分类 |
|  崩坏RPG  |  否  | string | 头像分类 |
|   NOVA    |  否  | string | 头像分类 |
| 崩坏3官方 |  否  | string | 头像分类 |
|   原神    |  否  | string | 头像分类 |
| 崩坏3画师 |  否  | string | 头像分类 |
|    崩2    |  否  | string | 头像分类 |
|   未定    |  否  | string | 头像分类 |
|  大别野   |  否  | string | 头像分类 |

- 返回示例

``` json
返回头像ing
```

- 返回参数说明

 `返回头像ing`

- 代码示例

``` 
https://api.qjqq.cn/api/MiYouShe
https://api.qjqq.cn/api/MiYouShe?stor=大别野（米游社默认头像）
https://api.qjqq.cn/api/MiYouShe?stor=绝区零
```

  
# 七、QQ信息
- QQ昵称、头像、邮箱获取
- 接口详情 QQ信息
| 接口地址                       | 请求方法 | 返回格式 |
| ------------------------------ | -------- | -------- |
| https://api.qjqq.cn/api/qqinfo | GET/POST | JSON     |



- 请求参数说明

  

| 名称 | 必填 |  类型  |  说明  |
| :--: | :--: | :----: | :----: |
|  qq  |  是  | string | QQ号码 |

- 返回示例

``` json
{
    "code": 200,
    "imgurl": "https://q1.qlogo.cn/headimg_dl?dst_uin=1645253&spec=100",
    "name": "-你呀",
    "mail": "1645253@qq.com"
}
```

- 返回参数说明

|  名称  |  类型  |        说明         |
| :----: | :----: | :-----------------: |
|  code  | number | 状态码，200代表成功 |
| imgurl | string |   QQ用户的头像URL   |
|  name  | string |    QQ用户的昵称     |
|  mail  | string |  QQ用户的邮箱地址   |

- 代码示例

``` 
https://api.qjqq.cn/api/qqinfo?qq=1645253
```

# 八、天气查询
- 自定义地区天气信息查询
- 接口详情 天气查询
| 接口地址                        | 请求方法 | 返回格式 |
| ------------------------------- | -------- | -------- |
| https://api.qjqq.cn/api/Weather | GET      | JSON     |



- 请求参数说明

  

|   名称    | 必填 |  类型  | 说明 |
| :-------: | :--: | :----: | :--: |
| city_name |  是  | string |  市  |

- 返回示例

``` json
{
    "data": {
        "code": 200,
        "result": {
            "alert": null,
            "aqi": 29,
            "city_name": "上海",
            "current_condition": "多云",
            "current_temperature": 22,
            "current_time": 1696753762,
            "dat_condition": "多云",
            "dat_high_temperature": 24,
            "dat_low_temperature": 19,
            "dat_weather_icon_id": "1",
            "day_condition": "多云",
            "download_icon": 1,
            "forecast_list": [
                {
                    "condition": "小雨",
                    "date": "2023-10-07",
                    "high_temperature": "22",
                    "low_temperature": "17",
                    "weather_icon_id": "7",
                    "wind_direction": "东北风",
                    "wind_level": "1"
                },
                {
                    "condition": "多云",
                    "date": "2023-10-08",
                    "high_temperature": "23",
                    "low_temperature": "17",
                    "weather_icon_id": "1",
                    "wind_direction": "北风",
                    "wind_level": "1"
                },
                {
                    "condition": "多云",
                    "date": "2023-10-09",
                    "high_temperature": "24",
                    "low_temperature": "19",
                    "weather_icon_id": "1",
                    "wind_direction": "北风",
                    "wind_level": "2"
                },
                {
                    "condition": "多云",
                    "date": "2023-10-10",
                    "high_temperature": "24",
                    "low_temperature": "19",
                    "weather_icon_id": "1",
                    "wind_direction": "东北风",
                    "wind_level": "1"
                },
                {
                    "condition": "晴",
                    "date": "2023-10-11",
                    "high_temperature": "24",
                    "low_temperature": "18",
                    "weather_icon_id": "0",
                    "wind_direction": "北风",
                    "wind_level": "1"
                },
                {
                    "condition": "多云转阴",
                    "date": "2023-10-12",
                    "high_temperature": "24",
                    "low_temperature": "18",
                    "weather_icon_id": "1",
                    "wind_direction": "北风",
                    "wind_level": "1"
                },
                {
                    "condition": "多云",
                    "date": "2023-10-13",
                    "high_temperature": "23",
                    "low_temperature": "17",
                    "weather_icon_id": "1",
                    "wind_direction": "西北风",
                    "wind_level": "2"
                },
                {
                    "condition": "晴",
                    "date": "2023-10-14",
                    "high_temperature": "23",
                    "low_temperature": "17",
                    "weather_icon_id": "0",
                    "wind_direction": "西北风",
                    "wind_level": "2"
                },
                {
                    "condition": "小雨转晴",
                    "date": "2023-10-15",
                    "high_temperature": "23",
                    "low_temperature": "15",
                    "weather_icon_id": "7",
                    "wind_direction": "西北风",
                    "wind_level": "1"
                },
                {
                    "condition": "晴",
                    "date": "2023-10-16",
                    "high_temperature": "25",
                    "low_temperature": "15",
                    "weather_icon_id": "0",
                    "wind_direction": "东风",
                    "wind_level": "2"
                },
                {
                    "condition": "晴",
                    "date": "2023-10-17",
                    "high_temperature": "25",
                    "low_temperature": "17",
                    "weather_icon_id": "0",
                    "wind_direction": "东风",
                    "wind_level": "1"
                },
                {
                    "condition": "阴",
                    "date": "2023-10-18",
                    "high_temperature": "24",
                    "low_temperature": "18",
                    "weather_icon_id": "2",
                    "wind_direction": "东南风",
                    "wind_level": "2"
                },
                {
                    "condition": "阴",
                    "date": "2023-10-19",
                    "high_temperature": "25",
                    "low_temperature": "19",
                    "weather_icon_id": "2",
                    "wind_direction": "东南风",
                    "wind_level": "2"
                },
                {
                    "condition": "多云",
                    "date": "2023-10-20",
                    "high_temperature": "25",
                    "low_temperature": "17",
                    "weather_icon_id": "1",
                    "wind_direction": "东北风",
                    "wind_level": "2"
                },
                {
                    "condition": "多云转晴",
                    "date": "2023-10-21",
                    "high_temperature": "23",
                    "low_temperature": "16",
                    "weather_icon_id": "1",
                    "wind_direction": "北风",
                    "wind_level": "3-4"
                },
                {
                    "condition": "多云转晴",
                    "date": "2023-10-22",
                    "high_temperature": "23",
                    "low_temperature": "16",
                    "weather_icon_id": "1",
                    "wind_direction": "北风",
                    "wind_level": "1"
                }
            ],
            "high_temperature": 23,
            "hourly_forecast": [
                {
                    "condition": "多云",
                    "hour": "15",
                    "temperature": "22",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "5.40"
                },
                {
                    "condition": "多云",
                    "hour": "16",
                    "temperature": "23",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "16.70"
                },
                {
                    "condition": "多云",
                    "hour": "17",
                    "temperature": "23",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "16.70"
                },
                {
                    "condition": "多云",
                    "hour": "18",
                    "temperature": "22",
                    "weather_icon_id": "31",
                    "wind_direction": "N",
                    "wind_level": "16.70"
                },
                {
                    "condition": "多云",
                    "hour": "19",
                    "temperature": "20",
                    "weather_icon_id": "31",
                    "wind_direction": "N",
                    "wind_level": "14.80"
                },
                {
                    "condition": "多云",
                    "hour": "20",
                    "temperature": "20",
                    "weather_icon_id": "31",
                    "wind_direction": "N",
                    "wind_level": "13.00"
                },
                {
                    "condition": "多云",
                    "hour": "21",
                    "temperature": "19",
                    "weather_icon_id": "31",
                    "wind_direction": "N",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "22",
                    "temperature": "19",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "23",
                    "temperature": "19",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "0",
                    "temperature": "19",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "1",
                    "temperature": "19",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "2",
                    "temperature": "17",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "3",
                    "temperature": "17",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "4",
                    "temperature": "17",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "5",
                    "temperature": "17",
                    "weather_icon_id": "31",
                    "wind_direction": "NW",
                    "wind_level": "11.09"
                },
                {
                    "condition": "多云",
                    "hour": "6",
                    "temperature": "17",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "13.00"
                },
                {
                    "condition": "多云",
                    "hour": "7",
                    "temperature": "19",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "13.00"
                },
                {
                    "condition": "多云",
                    "hour": "8",
                    "temperature": "21",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "13.00"
                },
                {
                    "condition": "多云",
                    "hour": "9",
                    "temperature": "22",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "14.80"
                },
                {
                    "condition": "多云",
                    "hour": "10",
                    "temperature": "23",
                    "weather_icon_id": "1",
                    "wind_direction": "NW",
                    "wind_level": "16.70"
                },
                {
                    "condition": "多云",
                    "hour": "11",
                    "temperature": "24",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "16.70"
                },
                {
                    "condition": "多云",
                    "hour": "12",
                    "temperature": "24",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "18.50"
                },
                {
                    "condition": "多云",
                    "hour": "13",
                    "temperature": "24",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "18.50"
                },
                {
                    "condition": "多云",
                    "hour": "14",
                    "temperature": "24",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "20.41"
                },
                {
                    "condition": "多云",
                    "hour": "15",
                    "temperature": "24",
                    "weather_icon_id": "1",
                    "wind_direction": "N",
                    "wind_level": "20.41"
                }
            ],
            "low_temperature": 17,
            "moji_city_id": 39,
            "night_condition": "多云",
            "origin_data": [],
            "quality_level": "优",
            "tips": "冷热适宜，感觉很舒适。",
            "tomorrow_aqi": 57,
            "tomorrow_condition": "多云",
            "tomorrow_high_temperature": 24,
            "tomorrow_low_temperature": 19,
            "tomorrow_quality_level": "良",
            "tomorrow_weather_icon_id": "1",
            "update_time": "2023-10-08 16:15:03",
            "weather_icon_id": "1",
            "wind_direction": "西风",
            "wind_level": 2
        },
        "msg": "success"
    }
}
```

- 返回参数说明

|        名称         |  类型  |        说明        |
| :-----------------: | :----: | :----------------: |
|      city_name      | string |        地区        |
|  current_condition  | string |      当前天气      |
| current_temperature | number |    当前天气温度    |
|    current_time     | number |    数据更新时间    |
|        tips         | string |    天气温馨提示    |
|    forecast_list    | object | 未来16天，天气预测 |


- 代码示例

``` 
https://api.qjqq.cn/api/Weather?city_name=上海
```

# 九、随机一言
- 一言，代表着言语的触动，灵魂的交流
- 接口详情 随机一言
| 接口地址                   | 请求方法 | 返回格式  |
| -------------------------- | -------- | --------- |
| https://api.qjqq.cn/api/Yi | GET      | JSON/TEXT |



- 请求参数说明

  

|  名称  | 必填 |  类型  |   说明   |
| :----: | :--: | :----: | :------: |
|   c    |  否  | string | 句子类型 |
| encode |  否  | string | 返回编码 |
|   a    |  否  | string |   动画   |
|   b    |  否  | string |   漫画   |

- 返回示例

``` json
{
    "id": 758,
    "uuid": "fcfe3b0d-5214-4b33-b330-8201a407a86f",
    "hitokoto": "我本来不想使出这一招的",
    "type": "b",
    "from": "少年JUMP",
    "from_who": null,
    "creator": "hitokoto",
    "creator_uid": 1775,
    "reviewer": 0,
    "commit_from": "web",
    "created_at": "1478787580",
    "length": 11
}
```

- 返回参数说明

|    名称     |  类型  |             说明             |
| :---------: | :----: | :--------------------------: |
|     id      | string |       句子的唯一标识符       |
|    uuid     | string | 句子的UUID，一个唯一的标识符 |
|  hitokoto   | string |           句子内容           |
|    type     | string |           句子类型           |
|    from     | string |           句子来源           |
|  from_who   | string |        句子来源的作者        |
|   creator   | string |          句子提交者          |
| creator_uid | number |    句子提交者的唯一标识符    |
|  reviewer   | number |          句子审核者          |
| commit_from | string |         句子提交来源         |
| created_at  | string |         句子创建时间         |
|   length    | number |           句子长度           |

- 代码示例

``` 
https://api.qjqq.cn/api/Yi （从7种分类中随机抽取）
https://api.qjqq.cn/api/Yi?c=b （请求获得一个分类是漫画的句子）
https://api.qjqq.cn/api/Yi?c=f&encode=text （请求获得一个来自网络的句子，并以纯文本格式输出））
https://api.qjqq.cn/api/Yi?c=f&encode=json （请求获得一个来自网络的句子，并以json格式输出）
```


