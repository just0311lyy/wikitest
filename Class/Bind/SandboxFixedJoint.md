# andboxFixedJoint
------------------------------------------------------------------------------------------
## 描述

固定连接点
继承：`SandboxJoint` 

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数



------------------------------------------------------------------------------------------
## 示例代码

```lua
local workspace = game:GetService("workspace")
--创建一个物理模型
local model1 = SandboxNode.new('SceneModelObject', workspace)
local model2 = SandboxNode.new('SceneModelObject', workspace)
--在两个模型下面分别添加一个附着点
local att0 = SandboxNode.new('SandboxAttachmentObject', model1)
local att1 = SandboxNode.new('SandboxAttachmentObject', model2)
--在其中一个模型下面添加一个连接点
local HingeJoint = SandboxNode.new('SandboxFixedJoint', model1)
--给连接点绑定两个模型的附着点
HingeJoint.attachment0 = att0
HingeJoint.attachment1 = att1
```