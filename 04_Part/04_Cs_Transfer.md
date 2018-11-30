
## § 发起转接 {#mgr_transfer}
```js
nodechat.emit('mgr', {
type : 'transfer',
roomid : 'roomid',
tocsid : 'tocsid',
msg : 'message'
}, function(err, datas) {
})
```

## 请求参数
- type - 固定参数
- roomid - 需要转接的房间
- tocsid - 转给的客服ID
- msg - 留言

### datas - {Object}
```json
{
  "success" : true
}
```


---
## § 接收转接 {#assign_transfer}

```js
nodechat.on('assign', function(datas) {
if (datas.type == 'transfer') {
//TODO
}
})
```
### datas - {Object}
```json
{
"type" : "transfer",
"roomid": "roomid",
"topic": "nick",
"lsttime" : 1539756771605,
"msg" : "message"
}
```
