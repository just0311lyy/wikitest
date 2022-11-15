# SceneStringObject
------------------------------------------------------------------------------------------
## 描述

继承：`SandboxNode` 
------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Value</font>]()</div>|
|:---|
|用于存储字符串|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<string\>]() &emsp;[<font color="dd00dd">ValueChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|当`stringvalue`改变时，通知值已更改||||
|**返回类型**|||**概要**|
|SBXSignal|||进入`stringvalue`改变时触发，事件参数为（`string stringvalue`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|stringvalue|string||当`stringvalue`改变时，通知值已更改|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local workspace = game:GetService("workspace")
local str = SandboxNode.new('SceneStringObject', workspace)
str.Value = "aaaa"
```