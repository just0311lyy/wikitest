# SceneModelObject
------------------------------------------------------------------------------------------
## 描述

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Visible</font>]()</div>|
|:---|
|设置节点的显示和隐藏|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">ModelId</font>]()</div>|
|:---|
|设置模型的模型ID|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">TextureId</font>]()</div>|
|:---|
|设置模型的贴图`TextureId`|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">Color</font>]()</div>|
|:---|
|设置模型的颜色 (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Gravity（已注释，不可用）</font>]()</div>|
|:---|
|模型重力（已注释，不可用）|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Friction</font>]()</div>|
|:---|
|模型摩擦力|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Restitution</font>]()</div>|
|:---|
|模型反弹力，比如物体撞击在地面上会根据此值来计算反弹高度|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Mass</font>]()</div>|
|:---|
|模型质量|

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Velocity</font>]()</div>|
|:---|
|模型移动速度 (`Rainbow::Vector3f`)|

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">AngleVelocity</font>]()</div>|
|:---|
|模型角速度|

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Size</font>]()</div>|
|:---|
|模型的Box大小|


|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Center</font>]()</div>|
|:---|
|模型的中心世界坐标|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">EnableGravity</font>]()</div>|
|:---|
|模型是支持重力|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Achored</font>]()</div>|
|:---|
|锚定状态，为`true`时此物体不受外部环境物理影响，但是会给外部提供物理输入。<br>例如：有外来物体撞击到此物体，此物体不会产生移动，但是会对外来物体产生碰撞反弹力。|


|<div style="width:1125px">[PhysicsType]() &emsp;[<font color="dd00dd">PhysXType</font>]()</div>|
|:---|
|参见枚举`PhysXLocoMotionComponent::PhysicsType`|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">EnablePhysics</font>]()</div>|
|:---|
|开启此物体的物理状态。为true时物体的物理属性可以使用|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">CanCollide</font>]()</div>|
|:---|
|是否可以碰撞。设为false时为trigger状态。|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">CanQuery</font>]()</div>|
|:---|
|是否可以查询。<br>特别注意：角色的碰撞是依靠物理查询的，所以此值如果为`false`，角色不会跟此物体产生任何碰撞。<br>响应包括`trigger`。|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">CanTouch</font>]()</div>|
|:---|
|是否触发碰撞回调函数：`Touched`和`TouchEnded`事件。|


|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">CollideGroupID</font>]()</div>|
|:---|
|碰撞组ID(`unsigned int`)，可以通过`PhysXService:SetCollideInfo`函数设置任意两个组之间是否会产生碰撞。|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">ModelLoaded</font>]()</div>|
|:---|
||


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">showDebug1</font>]()</div>|
|:---|
||


------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">PhysicsType</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|物理类型枚举|
|**名称**   |**值**  |**描述**|
|BOX|1   ||
|TRIANGLE_MESH  |2   ||

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">PlayAnimal</font> ]() ([string]() id, [float]() speed, [int]() loop)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|动作播放（兼容旧版，应该废弃）||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|string||动画id编号|
|speed|float||动画播放速度|
|loop|int||动画循环次数|
|**返回类型**|||**概要**|
|bool|||动画播放成功返回`true`|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">PlayAnimal2</font> ]() ([string]() id, [float]() speed, [int]() loop, [int]() priority = 1, [float]() weight = 1.0f)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|动作播放||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|string||动画id编号|
|speed|float||动画播放速度|
|loop|int||动画循环次数|
|priority|int|1|动画优先级|
|weight|float|1.0|动画权重|
|**返回类型**|||**概要**|
|bool|||动画播放成功返回`true`|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">StopAnimal</font> ]() ([string]() id)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|动作停止播放||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|string||动画id编号|
|**返回类型**|||**概要**|
|bool|||动画停止播放成功返回`true`|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">StopAnimal2</font> ]() ([string]() id)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|动作停止播放||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|string||动画id编号|
|reset|bool|||
|**返回类型**|||**概要**|
|bool|||动画停止播放成功返回`true`|


|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">StopAllAnimal</font> ]() ([bool]() reset)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|停止所有动画||||
|**参数名称**|**类别**|**默认**|**描述**|
|reset|bool|||
|**返回类型**|||**概要**|
|bool|||停止所有动画,返回true|


------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<SandboxNode, Vector3, Vector3\>]() &emsp;[<font color="dd00dd">Touched</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|模型被其他模型碰撞时，会触发一个Touched通知||||
|**返回类型**|||**概要**|
|SBXSignal|||被碰撞的模型节点对象，事件参数为（`SandboxNode node, Vector3 pos, Vector3 normal`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||被碰撞的模型节点对象|
|pos|Vector3||世界坐标|
|normal|Vector3||世界坐标|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">TouchEnded</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|模型被其他模型碰撞时，会触发一个Touched通知||||
|**返回类型**|||**概要**|
|SBXSignal|||被碰撞的模型节点对象，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||被碰撞的模型节点对象|

|<div style="width:500px">[SBXSignal\<int, int\>]() &emsp;[<font color="dd00dd">AnimEvent</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|模型动作事件||||
|**返回类型**|||**概要**|
|SBXSignal|||事件参数为（`int a, int b`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|a|int|||
|b|int|||

|<div style="width:500px">[SBXSignal\<ReflexTuple\>]() &emsp;[<font color="dd00dd">RemotePlayAnimal</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|||||
|**返回类型**|||**概要**|
|SBXSignal|||事件参数为（`ReflexTuple tuple`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|tuple|ReflexTuple|||

------------------------------------------------------------------------------------------
## 代码示例

```lua
--创建实例
local newModel= SandboxNode.new('SceneModelObject')
--设置名字
newModel.Name = "my_model"
--设置模型
newModel.ModelId = string.format("sandboxAsset://entity/%s/body.omod","100010")
--设置位置
newModel.Position = Vector3.new(500,700,500)
--设置父节点 将模型节点添加到Workspace中
newModel:SetParent(Workspace)

--播放动画
local player = game:GetService("Players").LocalPlayer.Character
player:PlayAnimal2("100114", 1.0, 0, 1, 1.0) --"100114 吃的动作"
player:StopAnimal("100114") --"100114 某个指定动作"
```