# SceneUIBillboard
------------------------------------------------------------------------------------------
## 描述

出现在`3D`空间中的`GUI`对象的容器。可以设置是否总是朝向摄像机，并且可以根据距离的变化改变其大小、或是在屏幕上保持相同的大小
继承：`SceneTransObject` 

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">FixedSize</font>]()</div>|
|:---|
|是否固定大小|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Billboard</font>]()</div>|
|:---|
|是否设置为广告位|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">AlwaysOntop</font>]()</div>|
|:---|
|是否总在顶部（已注释，lua不可调用）|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">Size2d</font>]()</div>|
|:---|
|设置容器平面大小(`Rainbow::Vector2f`)|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Visible</font>]()</div>|
|:---|
|是否可见|

------------------------------------------------------------------------------------------
## 函数


------------------------------------------------------------------------------------------
## 示例代码

```lua
local workSpace = game.WorkSpace
local loc = workSpace.SpawnLocation1
--创建SceneUIBillboard
local node = SandboxNode.new('SceneUIBillboard', workSpace)
node.Position = loc.Position+Vector3.new(0,500,0)
node.FixedSize = false
node.Billboard = false
--Billboard上文本
local image1 = SandboxNode.new('SceneUIImage', node)
image1.Name = 'Image'
image1.Visible = true
image1.Icon = 'ui\\mobile\\texture0\\common\\board_activity_box_white.png'
image1.Size = Vector2.new(500, 200)
```