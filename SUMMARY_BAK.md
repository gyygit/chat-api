# Summary

## 第一部分 整体概述

* [1.1 前言](README.md)
* [1.2 名词解释](01_Part/02_Term.md)
* [1.3 整体框架概述](01_Part/03_Architecture.md)
* [1.4 全局错误代码](01_Part/04_Global_Error.md)
* [1.5 基础数据字典](01_Part/05_Data_Dict.md)
  * [§ 接入类型](01_Part/05_Data_Dict.md#dict_atype)
  * [§ 消息类型](01_Part/05_Data_Dict.md#dict_type)
  * [§ 消息记录类型](01_Part/05_Data_Dict.md#dict_mtype)
  * [§ 客服状态](01_Part/05_Data_Dict.md#dict_csstatus)
  * [§ 评价方式](01_Part/05_Data_Dict.md#dict_rateType)
  * [§ 评价结果](01_Part/05_Data_Dict.md#dict_rateLevel)
* [1.6 基础数据结构](01_Part/06_Data_Structure.md)
  * [§ 聊天消息结构](01_Part/06_Data_Structure.md#structure_msg)
  * [§ 房间成员结构](01_Part/06_Data_Structure.md#structure_member)

## 第二部分 接入篇

* [2.1 接入前的准备](02_Part/01_Prepare.md)
  * [§ 页面该放置何处？](02_Part/01_Prepare.md#where)
  * [§ 加入基础库](02_Part/01_Prepare.md#add_support)
  * [§ onlinechat工具](02_Part/01_Prepare.md#usage_onlinechat)
  * [§ nodechat工具](02_Part/01_Prepare.md#usage_nodechat)
* [2.2 开始入手吧](02_Part/02_Get_Started.md)
  * [§ 导入基础库](02_Part/02_Get_Started.md#include_libs)
  * [§ 获取token](02_Part/02_Get_Started.md#token)
  * [§ 获取ticket](02_Part/02_Get_Started.md#ticket)
  * [§ nodechat使用](02_Part/02_Get_Started.md#nodechat_usage)
  * [§ 建立聊天通道](02_Part/02_Get_Started.md#connect_nodechat)

## 第三部分 接口篇-http

* [3.1 聊天基础接口](03_Part/01_Chat_Base.md)
  * [§ 查询聊天历史](03_Part/01_Chat_Base.md#chatMsg)
  * [§ 用户评价](03_Part/01_Chat_Base.md#rate)
* [3.2 客服分组](03_Part/02_Cs_Group.md)
  * [§ 查询分组列表](03_Part/02_Cs_Group.md#list)
  * [§ 查询分组及客服](03_Part/02_Cs_Group.md#list_and_cs)
* [3.3 多媒体](03_Part/03_Multimedia.md)
  * [§ 获取图片路径](03_Part/03_Multimedia.md#loadPicture)
  * [§ 上传图片](03_Part/03_Multimedia.md#uploadImage)
  * [§ 上传文件](03_Part/03_Multimedia.md#uploadFile)
  * [§ 下载文件](03_Part/03_Multimedia.md#downLoadFile)
* [3.4 工单管理](03_Part/04_Fault.md)
  * [§ 获取工单类型](03_Part/04_Fault.md#getBusinessType)
  * [§ 新增工单](03_Part/04_Fault.md#add)
  * [§ 查询工单](03_Part/04_Fault.md#list)

## 第四部分 接口篇-node

* [4.1 聊天基础操作](04_Part/01_Chat_Base.md)
  * [§ 建立聊天通道](04_Part/01_Chat_Base.md#connect)
  * [§ 进入聊天房间](04_Part/01_Chat_Base.md#join)
  * [§ 发送消息](04_Part/01_Chat_Base.md#chat)
  * [§ 接收消息](04_Part/01_Chat_Base.md#event_chat)
  * [§ 标记消息已读](04_Part/01_Chat_Base.md#mkread)
  * [§ 监听消息已读](04_Part/01_Chat_Base.md#event_mkread)
  * [§ 查看更多消息](04_Part/01_Chat_Base.md#viewchat)
  * [§ 离开聊天房间](04_Part/01_Chat_Base.md#leave)
* [4.2 智能客服](04_Part/02_Chat_AI.md)
  * [§ 展示默认问题](04_Part/02_Chat_AI.md#defFAQ)
  * [§ 获取问题详情](04_Part/02_Chat_AI.md#query)
  * [§ 展示搜索结果](04_Part/02_Chat_AI.md#aiFAQ)
* [4.3 客服基础操作](04_Part/03_Cs_Base.md)
  * [§ 获取所有用户](04_Part/03_Cs_Base.md#list_allUser)
  * [§ 获取自己用户](04_Part/03_Cs_Base.md#list_selfUser)
  * [§ 监听新用户请求](04_Part/03_Cs_Base.md#Event_Assign)
  * [§ 更新等待人数](04_Part/03_Cs_Base.md#setWaitCount)
  * [§ 移除某个用户](04_Part/03_Cs_Base.md#mgr_remove)
  * [§ 设置在线状态](04_Part/03_Cs_Base.md#mgr_setStatus)
  * [§ 获取所有客服状态](04_Part/03_Cs_Base.md#mgr_allStatus)
* [4.4 客服转接](04_Part/04_Cs_Transfer.md)
  * [§ 发起转接](04_Part/04_Cs_Transfer.md#mgr_transfer)
  * [§ 接收转接](04_Part/04_Cs_Transfer.md#assign_transfer)

## 第五部分 其他

* [常见问题及答复](05_Part/01_FAQ.md)
* [版本更新历史](05_Part/history.md)

