# AreaNode
------------------------------------------------------------------------------------------
## 描述

继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Beg</font>]()</div>|
|:---|
|起始位置世界坐标|

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">End</font>]()</div>|
|:---|
|结束位置世界坐标|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">EffectWidth</font>]()</div>|
|:---|
|效果宽度|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Show</font>]()</div>|
|:---|
|是否显示|

|<div style="width:1125px">[SHOWMODE]() &emsp;[<font color="dd00dd">ShowMode</font>]()</div>|
|:---|
|显示模式的枚举(`SceneEffectFrame::SHOWMODE`):<br>X = 1,<br>Y = 2,<br>Z = 4,<br>XY = 1+2,<br>XZ = 1+4,<br>YZ = 2+4,<br>XYZ = 1+2+4|


|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">Color</font>]()</div>|
|:---|
|设置区域颜色|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyEnterNode</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|节点进入该区域||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||进入该区域的`SandboxNode`节点|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyLeaveNode</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|节点离开该区域||||
|**返回类型**|||**概要**|
|SBXSignal|||离开节点时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||离开该区域的`SandboxNode`节点|

------------------------------------------------------------------------------------------
## 示例代码：

```lua
local part = script.Parent --获取父节点
local area = SandboxNode.new('AreaNode', part) --创建AreaNode节点

--创建Actor实例
local actorNode = SandboxNode.new('SceneActorObject')
actorNode.Name = "my_actor"

--actorNode进入区域
area.NotifyEnterNode:connect(function(actorNode) 
    print("actorNode进入区域")
end)
```