# ScenePlayerObject
------------------------------------------------------------------------------------------
## 描述：

继承：`SandboxNode` 

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">Character</font>]()</div>|
|:---|
|行为|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Neutral</font>]()</div>|
|:---|
|是否中立|

|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">Team</font>]()</div>|
|:---|
|隶属Team|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">TeamColor</font>]()</div>|
|:---|
|隶属Team的颜色值|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">UserId</font>]()</div>|
|:---|
|用户UserId|

|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">Backpack</font>]()</div>|
|:---|
|背包|

|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">ActorObject</font>]()</div>|
|:---|
|生物对象|

|<div style="width:1125px">[CameraMode]() &emsp;[<font color="dd00dd">CameraMode</font>]()</div>|
|:---|
|相机模式（第一人称或第三人称视角）|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">CameraMaxZoomDistance</font>]()</div>|
|:---|
|玩家镜头的最大拉远距离|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">CameraMinZoomDistance</font>]()</div>|
|:---|
|玩家镜头的最大拉近距离|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">nameDisplayDistance</font>]()</div>|
|:---|
|设置其他 Humanoid 名称对当前玩家的可见距离。设置为 0 时将隐藏所有名称|

------------------------------------------------------------------------------------------
## 函数：

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">WaitForChild</font> ]() ([string]() child)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|通过名获取沙盒子节点||||
|**参数名称**|**类别**|**默认**|**描述**|
|child|string||节点name名|
|**返回类型**|||**概要**|
|SandboxNode|||沙盒子节点|

|<div style="width:500px">[Vector3]() &emsp;[<font color="dd00dd">EyePos</font> ]() ([Vector3]() pos, [Vector3]() dir, [float]() dist)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|校准碰撞视线位置（仅脚本可用）||||
|**参数名称**|**类别**|**默认**|**描述**|
|pos|Vector3||世界坐标|
|dir|Vector3||朝向|
|dist|Vector3||射线途径的距离长度|
|**返回类型**|||**概要**|
|Vector3|||世界坐标|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">EquipTool</font> ]() ([SandboxNode]() tool)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|给`player`装备上指定的`tool`||||
|**参数名称**|**类别**|**默认**|**描述**|
|tool|SandboxNode||即将装备的Tool|

|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">UnequipTools</font>]()</div>|
|:---|
|解除`player`的装备|

------------------------------------------------------------------------------------------
## 事件：

|<div style="width:500px">[SBXSignal\<float\>]() &emsp;[<font color="dd00dd">Idle</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|通常在游戏引擎将玩家定类为闲置状态的两分钟后进行触发。`Time`（时间）为此时点后所经历的秒数||
|**返回类型**|**概要**|
|float|限制状态触发时间|

