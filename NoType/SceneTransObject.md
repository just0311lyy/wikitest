------------------------------------------------------------------------------------------
## SceneTransObject
------------------------------------------------------------------------------------------
## 描述

位移，旋转等操作的基类节点
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性：


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Position</font>]()</div>|
|:---|
|全局坐标(`Rainbow::Vector3f`)|


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Euler</font>]()</div>|
|:---|
|全局欧拉角(`Rainbow::Vector3f`)|


|<div style="width:1125px">[Quaternion]() &emsp;[<font color="dd00dd">Rotation</font>]()</div>|
|:---|
|全局旋转(`Rainbow::Quaternionf`)|


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">LocalPosition</font>]()</div>|
|:---|
|局部坐标(`Rainbow::Vector3f`)|


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">LocalEuler</font>]()</div>|
|:---|
|局部欧拉角(`Rainbow::Vector3f`)|


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">LocalScale</font>]()</div>|
|:---|
|局部大小(`Rainbow::Vector3f`)|


|<div style="width:1125px">[Quaternion]() &emsp;[<font color="dd00dd">LocalRotation</font>]()</div>|
|:---|
|局部旋转(`Rainbow::Quaternionf`)|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">CubeBorderEnable</font>]()</div>|
|:---|
|立方体边框是否被禁止|


|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">CubeBorderColor</font>]()</div>|
|:---|
|立方体边框颜色(`Rainbow::ColorQuad`)|

------------------------------------------------------------------------------------------
## 函数：


------------------------------------------------------------------------------------------
## 示例代码

```lua
local trans = SandboxNode.new('SceneTransObject')
local workSpace = game.WorkSpace
trans:SetParent(workSpace)
--设置全局位置
trans.Position = Vector3.new(100, 100, 100)
--设置局部大小
trans.LocalScale = Vector3.new(20, 1, 1)
```