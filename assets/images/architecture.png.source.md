### render by note.youdao.com

```
sequenceDiagram

participant CLIENT as 用户Client(浏览器)
participant THIRD as 第三方接入系统(J2EE)
participant PAGE as 聊天页面系统(J2EE)
participant CS as 客服系统(J2EE)
participant NODE as 聊天服务(Node.js)
participant RDS as Redis


CLIENT-->>THIRD: ①申请登录聊天系统的token
THIRD-->>CS: 带上用户信息，获取token
Note over CS: 生成 token(一次性)
CS-->> RDS: 按照token存储用户信息
CS-->>THIRD: 返回token
THIRD-->>CLIENT: 返回token

CLIENT->>PAGE: ②带上token，打开聊天页面
PAGE-->>CS: 请求开启聊天
Note over CS: 颁发 ticket
CS-->> RDS: 使token失效并按照ticket存储用户信息
CS-->>PAGE: 返回ticket
PAGE->>CLIENT: 返回聊天界面

CLIENT-->>NODE: ③连接聊天系统,使用ticket
NODE-->>RDS: 验证ticket
RDS-->>NODE: 获取用户信息
NODE-->>CLIENT: 建立聊天链接
```