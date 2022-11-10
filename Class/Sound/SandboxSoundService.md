# SandboxSoundService
------------------------------------------------------------------------------------------
#### 描述

此类是一个服务！它是顶级单例，可以使用`GetService`函数获取。为负责将 `Players`玩家在不同服务器和场景间进行传送的服务。<br>
继承：`ServiceNode` 

------------------------------------------------------------------------------------------
#### 属性：

|<div style="width:1125px">EnumListenerType ListenerType</div>|
|:---|
|当前监听类型。包括以下几种：<br>	EnumListenerType::Camrea         --以相机位置作为监听位置<br>	EnumListenerType::TransObject    --以玩家指定的TransObject位置作为监听位置<br>	只可在脚本获取，不可写。参考枚举EnumListenerType |

|<div style="width:1125px">SandboxNode ListenerObject</div>|
|:---|
|只可在脚本获取，不可写，当ListenerType为Camrea时返回nil，当ListenerType为TransObject时返回TransObject节点指针|

|<div style="width:1125px">float RolloffScale</div>|
|:---|
|3D声音衰减速度|

|<div style="width:1125px">float DistanceFactor</div>|
|:---|
|3D声音衰减距离|

|<div style="width:1125px">float DopplerScale</div>|
|:---|
|3D声音多普勒效应强度|

------------------------------------------------------------------------------------------
#### 枚举：

|<div style="width:200px">EnumListenerType</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|监听类型枚举|
|名称   |值  |描述|
|Camrea   |0   |以相机位置作为监听位置|
|TransObject|1   |以玩家指定的TransObject位置作为监听位置|

------------------------------------------------------------------------------------------
#### 函数：

|<div style="width:500px">void SetListener( ListenerType type, SandboxNode object )</div>|<div style="width:120px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置监听类型与监听者||||
|参数名称|类别|默认|描述|
|type|EnumListenerType||监听类型枚举，参见枚举EnumListenerType|
|object|SandboxNode||监听者|

|<div style="width:500px">void PlayerLocalSound( SandboxNode sound )</div>|<div style="width:120px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|在本地播放声音节点（2D，不会同步）||||
|参数名称|类别|默认|描述|
|sound|SandboxNode||监听者|

|<div style="width:500px">void SetSoundOpen(bool value)</div>|<div style="width:120px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|在本地开关声音（包括游戏本身的音乐和声音节点）||||
|参数名称|类别|默认|描述|
|value|bool||声音开关，为true，开启声音|

------------------------------------------------------------------------------------------
#### 事件：


------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local SoundService = game:GetService("SoundService")
	SoundService:SetSoundOpen(true) --打开声音
	local listenertype = SoundService.ListenerType --监听类型
	local listenerobject = SoundService.ListenerObject --监听对象
	SoundService.RolloffScale = 1 --衰减速度
	SoundService.DistanceFactor = 0 --衰减距离
	SoundService.DopplerScale = 0 --多普勒效应强度
	local soundnode = game.WorkSpace.Sound --获取Sound节点
	SoundService:PlayerLocalSound(soundnode) --本地播放
	local transnode = game.WorkSpace.TransNode --获取TransObject节点
	SoundService:SetListener(Enum.EnumListenerType.TransObject,transnode) --设置监听者
```
