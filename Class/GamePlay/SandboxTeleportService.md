# SandboxTeleportService
------------------------------------------------------------------------------------------
## 描述

此类是一个服务！它是顶级单例，可以使用`GetService`函数获取。为负责将 `Players`玩家在不同服务器和场景间进行传送的服务。

继承：`ServiceNode` 

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">teleport</font> ]() ([SandboxNode]() playernode, [Vector3]() pos)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|地图内将玩家传送到指定位置||||
|**参数名称**|**类别**|**默认**|**描述**|
|playernode|SandboxNode||玩家|
|pos|Vector3||指定位置的世界坐标|


------------------------------------------------------------------------------------------
## 事件

|<div style="width:1125px">[SBXSignal]() &emsp;[<font color="dd00dd">TeleportSuccess</font>]()</div>|
|:---|
|玩家传送成功触发|

|<div style="width:1125px">[SBXSignal]() &emsp;[<font color="dd00dd">TeleportFail</font>]()</div>|
|:---|
|玩家传送失败触发|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local TeleportService= game:GetService('TeleportService')
TeleportService:teleport(player, Vector3.new(500, 700, 800))
```