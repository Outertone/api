## 短信下发接口  
### 请求地址：

-     http://ip:port/sendMessage

### 请求方式:

-     POST

### 请求参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
uid |是|String| 客户代号，uid 和 apikey 由管理员统一分配
sign|是|String| 根据平台分配的 apikey 进行组合，sign=md5(uidyyyyMMddHHmmss-"send"-apikey),32 位大写
mobiles|是|String| 手机号,群发时多个手机号以逗号分隔(最多同时发送 1000 个号码)
content|是|String| 短信内容，超过 70 个字符，每 67 个字符计一条短信
timeStamp|是|String| 时间戳,格式 YYYYMMDDHHmmss,不能小于当前时间 3分钟
ext|否|String|纯数字
cusCode|否|String|客户自定义代码，不超过 32 位

### 请求参数示例:

```json
{
  "timeStamp": "20171114160039",
  "ext": "31235",
  "content": "【泰铭】您当前的验证码为 33141，有效期为 15 分钟，请妥善保管。",
  "sign": "78405F8E92A4FFB127277F6D69193276",
  "mobiles": "13212746534",
  "uid": "tmhc02145"
}
```

### 返回参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
resCode| 是| String| 0000 表示成功
resMsg| 是| String| 描述
count |是| String |该条短信计费条数，当短信字数小于 70 时，即数为 1，当短信字数大于 70，每 67 个字作为一条计费
smsId| 是| String| 每条短信的唯一标识
mobile| 是| String| 手机号码
status| 是| String| 状态

### 返回示例:

```json
{
  "data": {
    "count": 2,
    "infoArray": [{
        "smsId": 639429912651709440,
        "mobile": "13971000121",
        "count": 1,
        "status": "SUCCESS"
      },
      {
        "smsId": 639429912655903744,
        "mobile": "13971000122",
        "count": 1,
        "status": "SUCCESS"
      }
    ]
  },
  "resCode": "0000",
  "resMsg": "成功"
}
```