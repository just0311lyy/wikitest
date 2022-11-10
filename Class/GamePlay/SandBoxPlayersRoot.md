# SandBoxPlayersRoot
------------------------------------------------------------------------------------------
## 描述

是一个服务，包含当前已连接到服务器的客户端的所有`player`对象。

继承：`ServiceNode` 

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">LocalPlayer</font>]()</div>|
|:---|
|客户端当前的`LocalPlayer`对象|


|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">MaxPlayers</font>]()</div>|
|:---|
|此服务器中可以容纳的最大玩家数量|

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetPlayerByUserId</font> ]() ([int]() userId)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|返回给的`serId`的`player`对象||||
|**参数名称**|**类别**|**默认**|**描述**|
|userId|int||给定的id|
|**返回类型**|||**概要**|
|SandboxNode|||`userid`对应的`player`对象|

|<div style="width:500px">[vector\<SandboxNode\>]() &emsp;[<font color="dd00dd">GetPlayers</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|返回所有目前连接的`player`对象的数组||
|**返回类型**|**概要**|
|vector\<SandboxNode\>|所有目前连接的`player`对象的数组|

------------------------------------------------------------------------------------------
## 事件：

|<div style="width:1125px">[SBXSignal]() &emsp;[<font color="dd00dd">PlayerConnecting</font>]()</div>|
|:---|
|玩家正在连接游戏时触发|

|<div style="width:1125px">[SBXSignal]() &emsp;[<font color="dd00dd">PlyerDisconnecting</font>]()</div>|
|:---|
|当玩家正从游戏中断开连接时触发。|

|<div style="width:1125px">[SBXSignal]() &emsp;[<font color="dd00dd">PlayerRejoining</font>]()</div>|
|:---|
|在玩家断开连接后重新加入游戏会话时触发。|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">PlayerAdded</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|当玩家进入游戏时触发。||
|**返回类型**|**概要**|
|SandboxNode|一个加入游戏的`player`实例|


|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">PlayerRemoving</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|玩家将要离开游戏时触发。||
|**返回类型**|**概要**|
|SandboxNode|一个离开游戏的`player`实例|


------------------------------------------------------------------------------------------
## 示例代码

```lua
local players = game:GetService("Players")
local playerlist = players:GetPlayers()
for i, v in ipairs( playerlist ) do
    print( v.ClassType )
end
```