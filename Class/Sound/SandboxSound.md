# SandboxSound
------------------------------------------------------------------------------------------
#### 描述

一个发出声音的对象<br>
继承：`SandboxNode`

------------------------------------------------------------------------------------------
#### 属性：

|<div style="width:1125px">string SoundPath</div>|
|:---|
|声音资源路径|

|<div style="width:1125px">Button Play</div>|
|:---|
|试听(EDITORUI::Button)|

|<div style="width:1125px">float Volume</div>|
|:---|
|声音音量大小|

|<div style="width:1125px">bool IsLoop</div>|
|:---|
|设置该声音是否重复播放|

|<div style="width:1125px">bool IsPlaying</div>|
|:---|
|仅在脚本可获取，用于标识声音是否完成播放（暂停但未完成播放也为true）|

|<div style="width:1125px">bool IsPaused</div>|
|:---|
|仅在脚本可获取，用于标识声音是否处于暂停状态|

|<div style="width:1125px">bool PlayOnRemove</div>|
|:---|
|设置为true时，会在移除节点后播放一次声音|

|<div style="width:1125px">bool NeedRelease</div>|
|:---|
|设置为true时，标记为会被释放|

|<div style="width:1125px">SandboxNode TransObject</div>|
|:---|
|设置为某个`SceneTransObject`节点后，`Sound`将在该节点的位置播放（3D声音），若`TransObject`与`FixPos`均未设置，则为全局播放（2D声音）|

|<div style="width:1125px">Vector3 FixPos</div>|
|:---|
|设置后，若没有指定`TransObject`，则在指定位置(`Rainbow::Vector3f`)播放3D声音|

|<div style="width:1125px">bool IsFixPosPlay</div>|
|:---|
|只可读，为true时代表正在`FixPos`属性所指位置播放3D声音|

|<div style="width:1125px">EnumRollOffMode RollOffMode</div>|
|:---|
|声音衰减模式，包括逆衰减（默认），线性衰减，线性平方衰减，锥型逆衰减模式。见枚举`EnumRollOffMode`|

|<div style="width:1125px">float RollOffMaxDistance</div>|
|:---|
|声音衰减最大距离|

|<div style="width:1125px">float RollOffMinDistance</div>|
|:---|
|声音衰减最小距离|

------------------------------------------------------------------------------------------
#### 枚举：

|<div style="width:200px">EnumRollOffMode</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|声音衰减模式|
|名称   |值  |描述|
|Inverse   |0   |该声音将遵循逆衰减模型，其中`mindistance`=全音量，`maxdistance`=声音停止衰减，衰减根据全局衰减系数固定|
|Linear|1   |该声音将遵循线性衰减模型，其中`mindistance`=全音量，`maxdistance`=静音|
|LinearSquare  |2   |该声音将遵循线性平方衰减模型，其中`mindistance`=全音量，`maxdistance`=静音。|
|InverseTapered  |3   |在距离接近`mindistance`时，该声音将遵循逆衰减模型，在距离接近`maxdistance`的情况下，该声音会遵循线性平方衰减模型。|

------------------------------------------------------------------------------------------
#### 函数：

|<div style="width:1125px">void PlaySound()</div>|
|:---|
|播放/继续播放声音（调用后IsPlaying为true，IsPaused为false）|

|<div style="width:1125px">void StopSound()</div>|
|:---|
|停止播放声音（调用后IsPlaying为false）|

|<div style="width:1125px">void ResumeSound()</div>|
|:---|
|重新播放声音（声音将从头开始播放）|

|<div style="width:1125px">void PauseSound()</div>|
|:---|
|暂停声音（调用后IsPaused为true）|

------------------------------------------------------------------------------------------
#### 事件：

|<div style="width:500px">SBXSignal PlayFinish( SandboxNode )</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|SandboxSound实例播放结束时触发该事件||||
|参数名称|类别|默认|描述|
|sandboxnode|SandboxNode||播放动画的节点|

------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local part = script.Parent --获取父节点
	local sound1 = SandboxNode.new('SandboxSound', part) --创建Sound节点
	sound1.SoundPath ="sandboxSysId://sounds/npc/chest.ogg" --设置资源路径
	sound1.TransObject = script.Parent --绑定TransObject（播放3D声音）
	sound1.IsLoop = true --设置循环播放
	sound1.PlayOnRemove = true --设置移除时播放
	sound1.RollOffMode = Enum.EnumRollOffMode.Linear --设置声音衰减模式
	sound1.RollOffMinDistance = 300
	sound1.RollOffMaxDistance = 700
	sound1:PlaySound() --播放函数

	--播放结束事件
	sound1.PlayFinish:connect(function(node) 
	    node:Destroy()
	    print("sound is Destroy")
	end)
```