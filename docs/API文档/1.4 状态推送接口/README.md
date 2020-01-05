## 状态推送接口  
### 请求地址：[由客户提供，默认不开启]

-     http://url 

### 请求方式:

-     POST

### 请求参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
uid |是|String| 描述 
phone| 是| String| 查询的电话号码 
code| 是| String| 短信发送状态，0 表示成功，见状态明细码 
smsId| 是| String| 短信对应的 smsId 与发送返回的 smsId 对应 
remark| 是| String| 状态描述


### 返回参数示例：

```json
{
    "uid": "TMHC102221",
    "data": [{
        "mobile": "13970009121",
        "smsId": "639429912651709440",
        "status": "0",
        "remark": "成功"
    }, {
        "mobile": "13971000122",
        "smsId": "639429912655903744",
        "status": "0",
        "remark": "成功"

    }]
}
```

### 返回参数:
参数名|必填|类型|参数说明
:---:|:---:|:---:|:---:
resCode| 是| String| 0000 表示成功
resMsg| 是| String| 描述


### 返回示例:

```json
{
    "resMsg": "成功",
    "resCode": "0000"
}
```