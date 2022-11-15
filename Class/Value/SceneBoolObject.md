# SceneBoolObject
------------------------------------------------------------------------------------------
## 描述
 
继承：`SandboxNode` 
------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Value</font>]()</div>|
|:---|
|用于存储布尔值。|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">ValueChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|当`boolvalue`改变时，通知值已更改||||
|**返回类型**|||**概要**|
|SBXSignal|||进入`boolvalue`改变时触发，事件参数为（`bool boolvalue`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|boolvalue|bool||当`boolvalue`改变时，通知值已更改|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local workspace = game:GetService("workspace")
local bool1 = SandboxNode.new('SceneBoolObject', workspace)
bool1.Value = false
```
