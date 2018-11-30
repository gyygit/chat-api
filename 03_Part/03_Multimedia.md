# 多媒体接口
---
## § 获取图片路径 {#loadPicture}

### 功能描述

获取图片路径

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/file/loadPicture

### 返回示例
```
{
  "success":true,
  "picUrl":"http://ip:port/onlinechat/kfxt"
}
```

### 返回说明

- picUrl - 图片路径

---
  
## § 上传图片 {#uploadImage}

### 功能描述

上传图片

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/file/uploadImage

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| cmFile  | file|  Y  | 文件     |



### 返回示例
```
{
  "errcode":0,
  "data":"2018-11-08/onlinechat_1541665700474.png"
}
```
### 返回说明
#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
- data - 图片路径



---

## § 上传文件 {#uploadFile}

### 功能描述

上传文件

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/file/uploadFile

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| ticket  | string|  Y  | ticket凭证 |
| cmFile  | file |  Y  | 文件     |



### 返回示例
```
{
  "errcode":0,
  "fileid":"2c90a78566f12b4a0166f273647f0000",
  "filename":"test.txt",
  "filesize":16668
}
```

### 返回说明

#### errcode&nbsp;详见 [全局错误代码](/01_Part/04_Global_Error.md)
- fileid - 文件id
- filename - 文件名
- filesize - 文件大小


---

## § 下载文件 {#downLoadFile}

### 功能描述

下载文件

### 请求说明
> 请求方式：GET & POST
> 请求URL: onlinechat/api/file/downLoadFile

### 请求参数
|  参数    | 类型  | 必填 | 说明       |
|  ----   | ----  | ---:| -------   |
| id  | string|  Y  | 文件id |






