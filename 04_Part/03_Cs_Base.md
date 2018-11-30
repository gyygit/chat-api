## § 获取所有用户 {#list_allUser}
```js
nodechat.emit('list', {
  type : 'allUser'
}, function(err, datas) {
      console.log('allUser:' , datas);
});

```

### datas - {Object}
- rooms

```json
{
  "roomid" : '$ROOMID',
  "topic" : 'topic'
  "c" : 1
}
```


---
## § 获取自己用户 {#list_selfUser}

```js
nodechat.emit('list', {
  type : 'selfUser'
}, function(err, datas) {
      console.log('selfUser:' , datas);
});
```

### datas - {Object}
- rooms

```json
{
  "roomid" : '$ROOMID',
  "topic" : 'topic'
  "c" : 1
}
```




---
## § 监听新用户请求 {#Event_Assign}
```js
nodechat.on('assign', function(datas) {
  if (datas.type == 'assign') {
    //TODO
  }
});
```

### datas - {Object}
```json
{
  "type": "assign",
  "roomid": "$ROOMID",
  "userid": "USERID",
  "topic": "NICK",
  "lsttime" : 1539403200348
}
```



---
## § 更新等待人数 {#setWaitCount}
为了能精确的提示新用户加入人工客服时，展示的排队人数，需要定时的将客服页面的等待人数回馈给服务器端。

```js
nodechat.emit('mgr', {
  type : 'setWaitCount',
  c : 4
}, function(err, datas){
});
```
### datas- {Object}
```json
{
  "success" : true
}
```


---
## § 移除某个用户 {#mgr_remove}
当客服不再关注某个用户，可以将其从自己的用户列表中移除

注：此方法不会导致用户从所有用户列表中移除。

```js
nodechat.emit('mgr', {
  type : 'remove',
  roomid : 'roomid'
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
## § 设置在线状态 {#mgr_setStatus}
客服可根据自身的情况，设置在线状态，以便系统的新用户请求的分配。

```js
nodechat.emit(Codes.EVENT_MGR, {
  type : 'setStatus',
  status : 'B'
}, function(err, datas) {
});
```

- status
客服状态， 详见 [客服状态定义](/01_Part/05_Data_Dict.md#dict_csstatus)


### datas - {Object}
```json
{
  "success" : true
}
```




---
## § 获取所有客服状态 {#mgr_allStatus}

获取所有客服的当前状态

```js
nodechat.emit(Codes.EVENT_MGR, {
  type : 'allStatus',
}, function(err, datas) {

});
```
### datas - {Object}
```json
{
  "allCs": {
    "CSID1" : 0,
    "CSID2" : 1,
    "CSID3" : 2
  }
}
```



---

## § 定期获取未读消息条数
```js
nodechat.emit('list', {
  type : 'unreads'
}, function(err, datas) {
  
})
```
### datas - {Object}

```json
{
  "rooms" {
    "roomid1" : 1,
    "roomid2" : 3,
    "roomid3" : 4
  }
}
```


---

## § 客服处理待服务用户
```js
nodechat.emit('mgr', {
  type : 'serveChat',
  roomid : 'roomid',
  chatid : 'chatid'
}, function(err, datas) {
  
});
```

### datas - {Object}
```json
{
  "success" : true
}
```







