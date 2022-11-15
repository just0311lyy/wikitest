# SandboxTweenService
------------------------------------------------------------------------------------------
## 描述

此类是一个服务！它是顶级单例，可以使用`GetService`函数获取。用来对实例的属性进行插值，可以用来为多种节点对象创建动画。
继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">Create</font> ]() ([SandboxNode]() node, [TweenInfo]() info, [ReflexMap]() map)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|创建渐变系统||||
|**参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||执行`tween`节点对象|
|info|TweenInfo||对`tween`进行插值的信息|
|map|ReflexMap||进行tween的属性和其目标值的表|
|**返回类型**|||**概要**|
|SandboxNode|||渐变节点|


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