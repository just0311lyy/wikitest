# SandboxChat
------------------------------------------------------------------------------------------
## 描述

继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsUserChatEnable</font> ]() ([int]() userId)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|是否允许聊天||||
|**参数名称**|**类别**|**默认**|**描述**|
|userId|int||玩家id|
|**返回类型**|||**概要**|
|bool|||回true，表示允许聊天|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SendChatText</font> ]() ([string]() text, [int]() type, [int]() targetuin, [int]() language)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|发送文本消息||||
|**参数名称**|**类别**|**默认**|**描述**|
|text|string||发送的文本内容|
|type|int||聊天类型|
|targetuin|int||目标玩家的uin|
|language|int||语言种类|

|<div style="width:500px">[string]() &emsp;[<font color="dd00dd">GetFilterString</font> ]() ([string]() text)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|过滤文本||||
|**参数名称**|**类别**|**默认**|**描述**|
|text|string||发送的文本内容|
|**返回类型**|||**概要**|
|string|||过滤后的文本|

------------------------------------------------------------------------------------------
## 示例代码
 
  