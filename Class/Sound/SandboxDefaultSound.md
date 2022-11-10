# SandboxDefaultSound
------------------------------------------------------------------------------------------
#### 描述

音效节点，可以用于原生库中的音效（在`Sound.csv`中配置的音效）<br>
继承：`SandboxSound`

------------------------------------------------------------------------------------------
#### 属性：

|<div style="width:1125px">EnumDefaultSound SoundType</div>|
|:---|
|默认声音类型枚举：脚步、行为、受击、待机、技能、环境、背景音乐、提示和其他。见枚举`EnumDefaultSound`|

|<div style="width:1125px">int EffectIndex</div>|
|:---|
|音效效果序列|

------------------------------------------------------------------------------------------
#### 枚举：

|<div style="width:200px">EnumDefaultSound</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|默认声音类型枚举：脚步、行为、受击、待机、技能、环境、背景音乐、提示和其他|
|名称   |值  |描述|
|NONE   |0   |无|
|FOOTSTEP|1   |脚步|
|BEHIVIOR  |2   |行为|
|BEHIT  |3   |受击|
|IDLE  |4   |待机|
|SKILL  |5   |技能|
|ENVIRONMENT  |6   |环境|
|BACKGROUND  |7   |背景音乐|
|HINT  |8   |提示|
|OTHER  |9   |其他|

------------------------------------------------------------------------------------------
#### 函数：

------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	 local workspace = game:GetService("workspace")
	 local Effect = SandboxNode.new('SandboxDefaultSound', part)
	 --设置音效为脚步
	 Effect.SoundType = Enum.EnumDefaultSound.FootStep
	 --设置音效序列
	 Effect.EffectIndex = 13
	 Effect:PlaySound() --播放音效
 ```