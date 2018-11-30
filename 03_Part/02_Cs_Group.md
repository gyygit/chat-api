# 客服分组

---

## § 获取客服分组 {#list}

### 功能描述

获取客服分组数据

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/csGroup/list

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| companyid  | string|  Y  | 商家ID     |



### 返回示例
```
{
  "errcode" : 0,
  "data" : [{
    "id" : "groupid1",
    "name" : "group name1"
  }, {
    "id" : "groupid2",
    "name" : "group name2"
  }]
}
```

### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
#### data :
- id - 群组id
- name -群组名称

---

## § 查询分组及客服 {#list_and_cs}

### 功能描述

获取客服分组数据

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/csMg/getCsMgByGroup

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
|companyid| string|  Y  | 商家ID     |



### 返回示例
```
{
  "errcode" : 0,
  "data" : [{
    "id" : "groupid1",
    "name" : "group name1",
    "csMg" : [{
      "id" :"cs1",
      "nickname" : "csname1"
    },{
      "id" :"cs2",
      "nickname" : "csname2"
    }]
  }, {
    "id" : "groupid2",
    "name" : "group name2",
    "csMg" : [{
      "id" :"cs1",
      "nickname" : "csname1"
    },{
      "id" :"cs2",
      "nickname" : "csname2"
    }]
  }]
}
```

### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
#### data :
- id -群组id
- name - 群组名称
- csMg - 群组成员
- csMg - id - 群组成员id
- csMg - nickname - 群组成员名称



