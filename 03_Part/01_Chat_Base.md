## § 查询聊天历史 {#chatMsg}

### 功能描述
查询聊天历史记录

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/msg/list

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| roomid  | string|  Y  | 房间ID     |
| page    | int   |  N  | 查询第N页，默认为`1` |
| size    | int   |  N  | 查询返回的记录条数，默认为`10` |
| mtype   | string|  N  | 查询消息类型，默认全部类型 |
| fTimeStr| string|  N  | 查询的开始日期，包含当天，格式`yyyy-MM-dd` |
| tTimeStr| string|  N  | 查询的截止日期，包含当天，格式`yyyy-MM-dd` |


### 返回示例
```
{
  "errcode":0,
  "msgs":[{
    "id":"07984240dc3011e898ec4bf9027aa5e5",
    "roomid":"/U2S_U1#C1",
    "utype":"usermsg",
    "mtype":"text",
    "aid":"U1",
    "nick":"User1",
    "msg":"Hi",
    "time":"2018-10-30 18:39:07"
  },{
    "id":"04949f30dc3011e898ec4bf9027aa5e5",
    "roomid":"/U2S_U1#C1",
    "utype":"usermsg",
    "mtype":"text",
    "aid":"U1",
    "nick":"User1",
    "msg":"Hi",
    "time":"2018-10-30 18:39:02"
  }]
}
```

### 返回说明
具体字段参见[聊天消息结构](/01_Part/06_Data_Structure.md#structure_msg)章节

---

## § 用户评价 {#rate}

### 功能描述
保存用户评价结果

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/userChat/saveRate

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| chatid  | string|  Y  | 聊天chatid |
| roomid  | string|  Y  | 房间ID     |
| ratetype| string|  Y  | [评价类型](/01_Part/05_Data_Dict.md#dict_rateType)    |
|rateresult|string|  Y  | [评价结果](/01_Part/05_Data_Dict.md#dict_rateLevel)|
|companyid| string|  Y  | 商家ID     |


### 返回示例
```
{
  "errcode" : 0
}
```

### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)


