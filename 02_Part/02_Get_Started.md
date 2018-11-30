# 开始入手吧

在`onlinechat-web`中新增 用户聊天页面`user_app.html`


## § 导入基础库 {#include_libs}


```html
<script type="text/javascript" src="webjars/socket.io-client/dist/socket.io.js"></script>
<script type="text/javascript" src="webjars/onlinechat/nodechat.js"></script>
<script type="text/javascript" src="webjars/onlinechat/onlinechat.js"></script>
```


## § 获取token {#token}

获取从第三方接入系统通过URL传递的`token`，可直接使用`onlinechat.js`中提供的工具方法：
```js
var token = onlinechat.getParameter('token');
```

## § 获取ticket {#ticket}

进入聊天页面后，通过`token`换取用户信息与`ticket`, 请求地址如下：
```
http://$IP:$PORT/onlinechat/api/ticket?token=$TOKEN
```

> `$IP:$PORT` 为客服系统部署的位置
> `$TOKEN` 为鉴权获取的聊天`token`


用户token返回JSON数据包如下：

```json
{
  "errcode" : 0,
  "ticket" : "This_is_a_ticket",
  "data" : {
    "aid" : "userid",
    "mid" : "memberid",
    "account" : "account",
    "nick" : "nick"
  }
}
```


客服token返回JSON数据包如下：


```json
{
  "errcode" : 0,
  "ticket" : "This_is_a_ticket",
  "data" : {
    "aid" : "userid",
    "mid" : "memberid",
    "shopid" : "shopid"
    "account" : "account",
    "nick" : "nick"
  }
}
```



## § 建立聊天通道 {#connect_nodechat}

以下是简化版的建立聊天通道的代码，详细的参数参见[建立聊天通道](/04_Part/01_Connect.md) 章节

```js
var nodechat =  new Nodechat({
  server : 'http://localhost:3100/',
  path : '',
  atype : 'uweb',
  ticket : '$ticket',
  connect : function(err, datas) {
    //TODO connection establishment
  }
});
```

当正常的建立起连接后，会调用`connect`函数，接下来就可以在此函数中调用其他的业务接口，实现聊天完整的客服系统功能。
