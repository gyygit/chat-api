
## § 聊天消息结构 {#structure_msg}

|  属性   | 说明         |
|  ---   |    ---       |
| id     | 消息ID       |
| type   | [消息发送类型](/01_Part/05_Data_Dict.md#dict_type) |
| mtype  | [消息记录类型](/01_Part/05_Data_Dict.md#dict_mtype) |
| aid    | 消息发送者账号id  |
| mid    | 消息发送者成员id  |
| nick   | 消息发送者昵称 |
| time   | 消息记录时间   |
| msg    | 消息内容      |

### 公共属性
```json
{
  "id" : "uuid",
  "type" : "usermsg"
  "time" : 1538211413370,
  "aid" : "U1",
  "mid" : "UU1",
  "nick" : "ZhangSan"
}
```


### text - 纯文本
```json
{
  "mtype" : "text",
  "msg" : "Hi, I send a text message to you!"
}
```

## image - 图片

```json
{
  "mtype" : "image",
  "msg" : "/path/to/image.png"
}
```


### file - 文件
```json
{
  "mtype" : "file",
  "msg" : {
    "fileid" : "",
    "filename": "",
    "filesize" : 1024000
  }
}
```

- fileid - 文件存储的唯一标识
- filename - 文件原始名称

### voice - 语音
```json
{
  "mtype" : "voice",
  "msg" : {
    "val" : "The voice text",
    "url" : "/path/to/voice.mp3",
    "duration": "3"
  }    
}
```

### video - 视频
```json
{
  "mtype" : "video",
  "msg" : {
    "duration": "10",
    "url" : "/path/to/video.mp4"
  }
}
```

### custom - 其他自定义类型
```json
{
  "mtype" : "custom",
  "msg" : {
    "custom_attr1" : "xxx",
    "custom_attr2" : "xxx",
    "Any Attribute" : "Any Value"
  }
}
```
 
--- 

## § 房间成员结构 {#structure_member}

|  属性   |可选项| 说明         |
|  ---   | --- |    ---       |
| type   | N   |成员类型`user` or `cs` |
| aid    | N   | 登陆账号id  |
| mid    | N   | 登陆成员id  |
|account | N   | account  |
| nick   | N   | 昵称    |
| status | Y   | 客服状态（仅限客服）|
