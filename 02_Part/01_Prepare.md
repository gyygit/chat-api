# 接入前的准备

## § 页面该放置何处？{#where}
聊天页面该归属于哪个系统呢？
其实页面的放置位置是灵活的，可以位于第三方接入系统中，也可以单独出来一个聊天页面的项目，为了体现出页面的低耦合，此文档假定页面系统单独与第三方系统 与 聊天系统 而存在。且假设页面系统为 `onlinechat-web`，大体结构如下：

```
onlinechat-web
└─ src
  └─ main
    └─ webapp
      ├─ themes
      | ├─ lib
      | | ├─ cs_app.js
      | | └─ user_app.js
      | └─ onlinechat
      |   ├─ cs_app.html
      |   └─ user_app.html
      └─ webjars
        ├─ onlinechat
        | ├─ nodechat.js
        | └─ onlinechat.js
        └─ socket.io-client
          └─ dist
            └─ socket.io.js
      
```


## § 加入基础库 {#add_support}

`onlinechat-support.jar`文件为**客服系统**提供给**聊天页面**的基础服务接口支持。主要包括如下的基础库：

|     文件        |        说明              |
|     ---        |         ---             |
| `socket.io.js` | `socket.io`通讯组件基础库  |
| `nodechat.js`  | `nodechat`聊天服务支持库   |
| `onlinechat.js`| `onlinechat`客服系统支持库 |



此`jar`是采用WebJars将Web前端Javascript和CSS等资源打包成Java的Jar包，这样在Java Web开发中我们可以借助Maven这些依赖库的管理，保证这些Web资源版本唯一性。

唯一遗憾的是需要Servlet 3才能自动的识别`webjars`,也就是说如果待部署的目标容器不支持Servlet 3，则需要将`onlinechat-support.jar`里面 `META-INF/resources/webjars`复制到 `$project/webapp`


## § onlinechat工具 {#usage_onlinechat}
此工具已绑定到`window`对象，可直接在自己的js中调用

- onlinechat.getParameter(String name)
> 从当前页面参数中获取指定`name`的参数值


## § nodechat工具 {#usage_nodechat}
此工具在使用前需初始化
- 初始化nodechat
> 详见[建立聊天通道](/04_Part/01_Connect.md)章节

- nodechat.on('event_name', callback);
> 监听某个事件

- nodechat.emit('event_name', callback);
> 主动触发某个事件

