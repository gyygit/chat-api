# 工单管理

---


## § 获取工单类型 {#getBusinessType}


### 功能描述

获取工单类型

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/pubType/getBusinessType

### 返回示例
```
{
  "errcode":0,
  "data":[{
    "key": "type1",
    "text":"typeName1"
  },{
    "key": "type2",
    "text":"typeName2"
  }]
}
```

### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
#### data
- key - 工单类型id
- text - 工单类型名称


---
## § 新增工单 {#add}

### 功能描述

新增工单

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/fault/add

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| companyid | string|  Y  | 商家ID   |
| title | string|  Y  | 问题标题  |
| phone | string|  Y  | 联系电话   |
| describe | string|  Y  | 问题描述  |
| businessType | string|  Y  | 工单类型   |
| discoveryTime | string|  Y  | 问题发现时间  |
| faultPicUrl1 | string|  N  | 相关截图1   |
| faultPicUrl1 | string|  N  | 相关截图2   |
| faultPicUrl1 | string|  N  | 相关截图3   |
| faultPicUrl1 | string|  N  | 相关截图4   |
| submitter | string|  Y  | 提交人   |


### 返回示例
```
{
  "errcode":0
}
```

### 返回说明

#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)

---
## § 查询工单 {#list}


### 功能描述

查询工单

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/fault/list

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| submitter  | string|  Y  | 提交人id     |
| createtimestart  | string|  N  | 开始时间     |
| createtimeend  | string|  N  | 结束时间     |
| companyid  | string|  Y  | 商家id     |


### 返回示例
```
{
  "errcode":0,
  "data":[{
    "describe" : "content",
    "faultId":"2c90a78566e2dddd0166e3399aeb0025",
    "faultPicUrl1":"img url1",
    "faultPicUrl2":"img url2",
    "faultPicUrl3":"img url3",
    "faultPicUrl4":"img url4",
    "feedbackConten":"cs feedbackContent",
    "state":"state",
    "submitTime":"2018-11-05 17:34:44",
    "submitter":"U1",
    "title":"title1"
  }]
}
```


### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
#### data
- describe - 问题描述
- faultPicUrl1 - 工单相关截图1
- faultPicUrl2 - 工单相关截图2
- faultPicUrl3 - 工单相关截图3
- faultPicUrl4 - 工单相关截图4
- feedbackConten - 客服回复内容
- state - 工单状态
- submitTime - 工单提交时间
- title - 工单标题
- submitter - 提交人id
- faultId - 工单Id

