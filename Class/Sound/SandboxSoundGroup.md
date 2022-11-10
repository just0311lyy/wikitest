# SandboxSoundGroup
------------------------------------------------------------------------------------------
#### 描述

声音分组节点，统一控制声音的播放，停止，音量等（请直接将声音节点挂在SoundGroup节点下面，`SoundGroup->Node->Sound`的挂载方式将不会起到控制效果）<br>
继承：`SandboxNode`

------------------------------------------------------------------------------------------
#### 属性：

------------------------------------------------------------------------------------------
#### 函数：

|<div style="width:1125px">void PlaySound()</div>|
|:---|
|播放/继续播放组内声音|

|<div style="width:1125px">void StopSound()</div>|
|:---|
|停止播放组内声音|

|<div style="width:1125px">void ResumeSound()</div>|
|:---|
|重新播放组内声音（声音将从头开始播放）|

|<div style="width:1125px">void PauseSound()</div>|
|:---|
|暂停组内声音|

|<div style="width:500px">void ChangeVolume( float vaval )</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|按比例改变组内声音音量（0~1），如：传入0.5会将组内Sound节点音量减半||||
|参数名称|类别|默认|描述|
|vaval|float||置组内声音音量（0~1），0.5音量减半|

------------------------------------------------------------------------------------------
#### 事件：

------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local part = script.Parent --获取父节点
	local soundGroup = SandboxNode.new('SandboxSoundGroup', part) --创建Sound节点
	soundGroup:ChangeVolume(0.5) --按比例调节音量
	soundGroup:PlaySound() --播放
	soundGroup:StopSound() --停止
```