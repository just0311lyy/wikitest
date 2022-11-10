# SpawnLocation
------------------------------------------------------------------------------------------
#### 描述

可确定`Player`（玩家）死亡时在何处重生

继承：`ScenePrimitiveObject` 

------------------------------------------------------------------------------------------
#### 属性：

|<div style="width:1125px">[bool]() &emsp;&emsp;[<font color="dd00dd">Neutral</font>]()</div>|
|:---|
|是否隶属与特定队伍，设置为true之后，任意队伍中的任意Player可以在此位置重生|


|<div style="width:1125px">[bool]() &emsp;&emsp;[<font color="dd00dd">AllowTeamChangeOnTouch</font>]()</div>|
|:---|
|是否允许Player通过Touch触摸该Location来加入对应TeamColor的Team队伍|

|<div style="width:1125px">[ColorValue]() &emsp;&emsp;[<font color="dd00dd">TeamColor</font>]()</div>|
|:---|
|队伍颜色(Rainbow::ColorQuad)，跟TeamColor可对应|

------------------------------------------------------------------------------------------
#### 函数：

------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local Teams = game:GetService('Teams')
	--创建开始队伍
	local team1 = SandboxNode.new('SandboxTeam', Teams)
	team1.AutoAssignable = true
	team1.TeamColor = Vector3.new(255, 0, 0)

	--创建重生点
	local team1Spawn = SandboxNode.new('SpawnLocation', game.WorkSpace)
	team1Spawn.Neutral = false
	team1Spawn.AllowTeamChangeOnTouch = true
	team1Spawn.TeamColor = team1.TeamColor
```