# 全局错误代码

# § err结构 {#error}
```json
{
  "errcode" : 5000,
  "errmsg" : "error message"
}
```

**注意：**`err`为`null`表示没有发生错误。


# § errcode说明
- 3100 - socket.io api调用错误
- 3101 - async api调用错误
- 4001 - 参数为空
- 4002 - 参数无效
- 4004 - resource no found.
- 5000 - java exception
- 5001
- 5004 - 配置错误
- 5005 - 请求接口错误
- 5009 - json parse error

- 5400 - SIZE0,文件内容为空
- 5401 - 不合法的文件后缀
- 5402 - 文件超过设定大小

- 6379 - redis api调用错误
  