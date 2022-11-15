# SceneTweenObject
------------------------------------------------------------------------------------------
## 描述

渐变`tween`对象本身控制插值的播放（补间动画，就是可以给节点的属性做插值）
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">EasingDirection</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|补间动画变化的方向枚举|
|**名称**   |**值**  |**描述**|
|In   |0   |缓动风格是向前应用的|
|Out|1   |缓动风格是向后应用的。|
|In_Out  |2   |缓动风格在前半段向前应用，在后半段向后应用|


|<div style="width:200px">EasingStyle</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|补间动画变化的方法枚举|
|**名称**   |**值**  |**描述**|
|Linear   |0   |以恒定速度移动|
|Sine|1   |运动速度由正弦波决定|
|Back  |2   |调整移动回原位或移出原位|
|Quad  |3   |类似于`Quart`和`Quint`，但速度不同|
|Quart  |4   |类似于`Quad`和`Quint`，但速度不同|
|Quint  |5   |类似于`Quad`和`Quart`，但速度不同|
|Bounce  |6   |移动时，就像`tween`的开始或结束位置是有弹性的一样|
|Elastic  |7   |移动时就像`GUI`元素连接到橡皮筋一样|


|<div style="width:200px">TweenStatus</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|补间动画的状态|
|**名称**   |**值**  |**描述**|
|Begin   |0   |`Tween`开始|
|Delayed|1   |`Tween`延迟播放|
|Playing  |2   |`Tween`开始播放|
|Paused  |3   |`Tween`在完成前暂停了|
|Canceled  |4   |`Tween`在完成前就被取消了|
|Completed  |5   |`Tween`顺利完成了|

------------------------------------------------------------------------------------------
## 函数：

|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">Pause</font>]()</div>|
|:---|
|将暂停`tween`的播放|


|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">Play</font>]()</div>|
|:---|
|将开始`tween`的播放|


|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">Cancel</font>]()</div>|
|:---|
|将停止`tween`的播放并重置它的变量|


|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">Resume</font>]()</div>|
|:---|
|将继续`tween`播放|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<TweenStatus\>]() &emsp;[<font color="dd00dd">Completed</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`Tween`结束时触发，返回`Tween`执行的状态||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`TweenStatus status`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|status|TweenStatus||补间动画的状态枚举，参见枚举`SceneTweenObject::TweenStatus`|


------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建实例
local TweenService = game:GetService('TweenService')
--缓动数据
local TweenInfo = TweenInfo.new(3.0, Enum.EasingStyle.Linear, nil, 0, 1)
--创建一个button
local root = SandboxNode.new('SceneUIRoot', game.WorkSpace)
root.Name = 'uiroot'
local button= SandboxNode.new('SceneUIButton', game.WorkSpace.uiroot)
button.Icon = 'ui\\mobile\\texture0\\common\\board_activity_box_white.png'
button.Size = Vector2.new(100, 50)
button.Position = Vector2.new(200, 100)
local goal = {}
goal.Position = Vector2.new(300, 200)
--创建缓动
local tween = TweenService:Create(button, TweenInfo, goal)
--缓动播放
tween:Play()
--缓动停止
tween:Pause()
--缓动继续
tween:Resume()
--缓动取消
tween:Cancel()
```