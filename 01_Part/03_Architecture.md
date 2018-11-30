# 整体框架概述

![](/assets/images/chat_architecture_for_web.png)

#### 说明：
- ①获取token
  > **第三方接入系统**请求**客服系统**接口获取聊天的`token`，具体参见
- ②打开聊天页面
  > 从**第三方接入系统**跳转到**聊天页面**(需要带上token参数)，然后再由**聊天页面**请求**客服系统** 获取聊天[`ticket`]()
- ③建立聊天通道
  > 根据**客服系统**返回的`ticket`可以建立起与**聊天服务**的通道。至此，已具备聊天的基础。