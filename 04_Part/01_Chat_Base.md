
## § 建立聊天通道

创建Nodechat实例以建立聊天服务的通道

```js
var nodechat =  new Nodechat({
  server : 'http://localhost:3100/',
  path : '',
  atype : 'uweb',
  ticket : '',
  connect : function(err, datas) {
    //TODO connection establishment 
  },
  reconnect : function(attempt) {
    //TODO reconnect
  },
  error : function(error) {
    //TODO error
  }
});
```


### 参数说明：
#### server - {String}
nodechat聊天服务地址，例如：`http://localhost:3100/`

#### path - {String}
路径，一般为空即可

#### atype - {String}

账号类型，用以区分用户与客服以及页面环境，[查看详情](/03_Part/99_Data_Dict.md#atype)

#### ticket - {String}
聊天凭证

#### connect(err, datas) - {Function}
- err (Object) 错误信息，为`null`表示无错误
- datas (Object) 

建立聊天通道后的回调，注意:重连后也会触发此回调

#### reconnect(attempt) - {Function}
- attempt (int) 重连尝试次数

重连回调


#### error - {Function}
错误回调

---


## § 进入聊天房间 {#join}

- 进入某个房间

```js
nodechat.emit('join', {
  roomid : '$ROOMID'
}, function(err, datas) {
  
});
```

- 用户咨询某个商家

```js
nodechat.emit('join', {
  shopid : '$COMPANYID',
  shopname: '$COMPANYNAME'
}, function(err, datas) {
  
});
```
### 请求参数说明
#### rooomid - {String}
请求加入的房间ID，当为空时，则根据`companyid`参数自动产生

#### companyid - {String}
咨询的商家ID

**注：**`roomid`与`companyid`不可同时为空，否则回调函数中将收到`err`。


### 回调参数说明：

#### err - {Object}

&nbsp;&nbsp;&nbsp;&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)

#### datas - {Object}
```json
{
  "roomid" : "$ROOMID",
  "data" : {
    "roomid" : "$ROOMID",
    "chat_msgs" : [{}, {}],
    "msg_pos" : 123,
    "topic" : "topic",
    "lsttime" : 1538209333516,
    "members" : [{}, {}]
  }
}
```

- roomid - 房间ID
- chat_msgs - 最近10条聊天记录，[消息格式](/01_Part/06_Data_Structure.md#structure_msg)
- msg_pos - 当前消息记录下标
- topic - 聊天主题(标题)
- lsttime - 最近聊天时间
- members - 房间成员, [成员格式](/01_Part/06_Data_Structure.md#structure_member)

---

## § 发送消息 {#chat}

### 发送文本消息

```js
nodechat.emit('chat', {
  roomid : '$ROOMID',
  type : 'text',
  msg : 'This is a text chat message.'
}, function(err, datas) {
});
```

### 发送图片消息

在发送图片时，需要先调用[图片上传接口](/03_Part/03_Multimedia.md#uploadImage)，获取到图片存储路径后，再调用本接口将图片消息发送出去。

```js
//after uploadImage  
var imagePath = '/path/to/image.png'; 

nodechat.emit('chat', {
  roomid : '$ROOMID',
  type : 'image',
  msg : imagePath,
}, function(err, datas) {
});
```

### 发送文件消息

在发送文件时，需要先调用[文件上传接口](/03_Part/03_Multimedia.md#uploadFile)，获取到文件存储路径后，再调用本接口将文件消息发送出去。

```js
var msg = {
  fileid : 'uuid',
  filename : 'The upload origin file name.'
}

nodechat.emit('chat', {
  roomid : '$ROOMID',
  type : 'file',
  msg : JSON.stringify(filename)
}, function(err, datas) {
});
```



### 回调参数说明：
#### err - {Object} 
  &nbsp;&nbsp;&nbsp;&nbsp;详见 [全局错误代码](/03_Part/99_Global_Error.md)
  
#### datas - {Object}
```json
{
  "success" : true
}
```


## § 接收消息 {#event_chat}

- 添加接收消息的监听

```js
nodechat.on('chat', function(datas) {
});
```
当有新消息时，`nodechat`将会回调此函数，用以通知页面做出相应的响应。

## 参数说明：

### datas - {Object}
```json
{
"roomid" : "$ROOMID",
"data" : {...}
}
```

- msg 聊天消息记录体，[点击查看详细结构](/01_Part/06_Data_Structure.md#structure_msg)


---

# § 查看更多消息
```js
nodechat.emit('user', {
  type : 'viewchat',
  roomid : $scope.roomid,
  start : room.msg_pos =  room.msg_pos - 10
}, function(err, datas) {
});
```

## 参数说明：
### start {int} 
消息游标

### datas - {Object}
```json
{
  "roomid" : "",
  "chat_msgs" : [...]
}
```

---

## § 标记已读 {#mkread}



```js
nodechat.emit('mkread', {
  roomid : '$ROOMID'
}, function(err, datas) {
  
});
```

### datas - {Object}
```json
{
  "success" : true
}
```

---
## § 接收对方已读通知 {#evnet_mkread}

```js
nodechat.on('mkread', function(datas) {
})
```

### datas - {Object}
```json
{
  "roomid": "roomid",
  "type" : "user",
  "time" : 1539935685979
}
```
- type 可取值为`user` 或 `cs`

---
## § 离开聊天房间 {#leave}

离开聊天房间

```js
nodechat.emit('leave', {
  roomid : '$ROOMID'
}, function(err, datas) {
  
});
```

### 请求参数说明
#### rooomid - {String}
请求离开的房间ID

### 回调参数说明：

#### err - {Object}

&nbsp;&nbsp;&nbsp;&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)

#### datas - {Object}
```json
{
  "success": true
}
```





