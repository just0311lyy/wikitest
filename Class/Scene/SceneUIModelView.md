# SceneUIModelView
------------------------------------------------------------------------------------------
## 描述

在`UI`中展示`3D`模型，将模型节点（如`ModelObject`）放置到子节点即可（注：模型节点是在`ModelView`的场景中展示，节点自身的位置，转角等属性也会生效）
继承：`SceneUIComponent`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[Bool]() &emsp;[<font color="dd00dd">CanCameraMove</font>]()</div>|
|:---|
|是否启用视角拖拽（拖拽UI时相机围绕模型旋转）|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">CameraDist</font>]()</div>|
|:---|
|相机与原点距离|

------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建ui布局
local root = SandboxNode.new('SceneUIRoot', game.WorkSpace)
root.Name = 'uiroot'

--创建UI
local ModelView = SandboxNode.new('SceneUIModelView', game.WorkSpace.uiroot)
ModelView.Size = Vector2.new(500, 500)
ModelView.Position = Vector2.new(500, 500)
ModelView.CanCameraMove = true
ModelView.CameraDist = 700

local newModel= SandboxNode.new('SceneModelObject')
newModel.Name = "my_model"
newModel.ModelId = "sandboxSysId://entity/100011/body.omod"
newModel.Position = Vector3.new(0,0,0)
--设置父节点 将模型节点添加到ModelView中
newModel:SetParent(ModelView)
```