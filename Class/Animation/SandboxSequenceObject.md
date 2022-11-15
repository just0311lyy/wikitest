# SandboxSequenceObject
------------------------------------------------------------------------------------------
## 描述

动画节点(可以外部引入动画也可以场景树上显示模型本身动画)
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">SequenceId</font>]()</div>|
|:---|
|序列ID|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">Time</font>]()</div>|
|:---|
|时间|

------------------------------------------------------------------------------------------
## 函数

------------------------------------------------------------------------------------------
## 事件

------------------------------------------------------------------------------------------
## 示例代码

```lua
--local animation
--创建SandboxSequenceObject
local sequenceNode = SandboxNode.new('SandboxSequenceObject')
sequenceNode:SetParent(game.WorkSpace)--animation
sequenceNode.SequenceId = 'id1'
sequenceNode.Time= 10
```