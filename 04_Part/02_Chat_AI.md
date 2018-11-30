# § 展示默认FQA {#AI_FQA}

当用户端调用 `nodechat.emit('join', function(err, datas))`后，如果对应的商家有配置默认的FQA，则会在此回调函数中包含如下的chat_msg信息：

### datas - {Object}
```json
{
  "roomid" : "roomid",
  "data" : {
    ...
    "chat_msgs" : [{...}, {...}]
    ...
  }
}

```

默认的FAQ将会位于chat_msgs数组的其中一个元素，结构如下：
```json
{
  "id" : "uuid",
  "type" : "csrmsg"
  "time" : 1538211413370,
  "aid" : "shopid",
  "mid" : "Sshopid",
  "nick" : "shopname",
  "mtype" : "custom",
  "msg" : {
    "subType" : "defFQA",
    "items" : [{
      "title" : "How to xx",
      "subItmes" : [{
        "id" : "id1",
        "subTitle" : ""
      }, {
        "id" : "id1",
        "subTitle" : ""
      }]
    }, {
      "title" : "How to xx",
      "subItmes" : [{
        "id" : "id1",
        "subTitle" : ""
      }, {
        "id" : "id1",
        "subTitle" : ""
      }]
    }]
  }
}
```

# § 查询条目详情 {#query} 
当用户点击某个具体的FQA后，调用如下的接口可以获取该FAQ的详情：

```js
socket.emit(Codes.EVENT_QUERY, {
  roomid : 'roomid',
  queryId : 'subItem id',
  queryTitle : 'subItem title'
}, function(err, datas) {
}
```

### datas - {Object}
```json
{
  "roomid" : "roomid",
  "data" : {
    "id" : "uuid",
    "roomid" : "roomid",
    "type" : "csmsg",
    "mtype" : "text",
    "msg" : "query result data",
    "aid" : "shopid",
    "mid" : "mid",
    "nick" : "shopname",
    "time" : 1539745042565
  }
}
```


# § 智能查询 {#aiFQA}
当用户发送普通文本时，且当前没有申请联系人工客服，系统将会对用户输入的文本作为问题查找的内容。
```js
nodechat.emit('chat', {
  mtype : 'text',
  msg : 'Search Text'
  ...
}, function(err, datas) {
  
});
```

### datas - {Object} 

- 情形1：`ERROR`当前智能客服异常，请稍后再试
```json
{
  "roomid" : "roomid",
  "result" : 'ERROR',
  "msg" : 'msg'
}
```

- 情形2：`EMPTY`抱歉，没有找到您要查询的问题
```json
{
  "roomid" : "roomid",
  "result" : 'EMPTY',
  "msg" : 'msg'
}
```

- 情形3：`FOUND` 查到相关问题
```json
{
  "roomid" : "roomid",
  "result" : 'FOUND',
  "items" : [{...}]
}
```
items结构详情默认问题相关部分



