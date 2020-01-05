## 状态拉取接口  
### 请求地址：

-     http://ip:port/getReport

### 请求方式:

-     POST

### 请求参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
uid |是|String| 客户渠道编号
sign|是|String| 根据平台分配的 apikey 进行组合，sign =md5 (uid-yyyyMMddHHmmss-"report"-密码 key),32 位大写 
timeStamp|是|String| 时间戳,格式 YYYYMMDDHHmmss,不能小于当前时 间 3 分钟 


### 请求参数示例:

```json
{
    "timeStamp": "20180323103400",
    "uid": "TMHC12353",
    "sign": "2DF179D9010334E2F66C8F5D0339911D"
}
```

### 返回参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
resCode| 是| String| 0000 表示成功
resMsg| 是| String| 描述
phone |是| String |查询的电话号码
code| 是| String| 短信发送状态，0 表示成功，见状态明细码 
smsId| 是| String| 短信对应的 smsId 与发送返回的 smsId 对应 
status| 是| String| 状态描述 

### 返回示例:

```json
{
    "resCode": "0000",
    "resMsg": "成功",
    "datas": [{
        "phone": "13970009121",
        "smsId": "639429912651709440",
        "status": "0",
        "remark": "成功"
    }, {
        "phone": "13971000122",
        "smsId": "639429912655903744",
        "status": "0",
        "remark": "成功"

    }]
}
```