# SceneActorObject
------------------------------------------------------------------------------------------
## 描述

继承：`SceneModelObject`

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Movespeed</font>]()</div>|
|:---|
|生物的移动速度|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">MaxHealth</font>]()</div>|
|:---|
|生物的最大生命值|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Health</font>]()</div>|
|:---|
|生物的当前生命值|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">UseCameraAngle</font>]()</div>|
|:---|
|是否使用相机角度|

|<div style="width:1125px">[BehaviorState]() &emsp;[<font color="dd00dd">MoveState</font>]()</div>|
|:---|
|行为状态枚举，见枚举`BehaviorState`|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">UserId</font>]()</div>|
|:---|
|用户id|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">NoPath</font>]()</div>|
|:---|
|是否无导航路径|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">SetGravity</font>]()</div>|
|:---|
|重力|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">BehaviorState</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|行为状态枚举|
|**名称**   |**值**  |**描述**|
|ZERO   |0   |无|
|Jump|1   |跳|
|Jumping  |2   |跳跃|
|Stand  |3   |站立|
|Walk  |4   |步行|
|Fly  |5   |飞形|
|Died  |6   |死亡|


------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetMoveEndTime</font> ]() ([float]() endtime)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置生物移动的结束时间||||
|**参数名称**|**类别**|**默认**|**描述**|
|endtime|float||结束时间|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">MoveTo</font> ]() ([Vector3]() target)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移动到某个位置||||
|**参数名称**|**类别**|**默认**|**描述**|
|target|Vector3||位置坐标|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetMoveEndTime</font> ]() ([Vector3]() dir, [bool]() relativeToCamera)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置生物移动的结束时间||||
|**参数名称**|**类别**|**默认**|**描述**|
|dir|Vector3||方向|
|relativeToCamera|bool||是否关联摄像机|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">Jump</font> ]() ([bool]() jump)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置生物是否跳跃||||
|**参数名称**|**类别**|**默认**|**描述**|
|jump|bool||是否跳跃|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetJumpInfo</font> ]() ([float]() baseSpeed, [float]() continueSpeed)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置生物跳跃参数||||
|**参数名称**|**类别**|**默认**|**描述**|
|baseSpeed|float||基础速度|
|continueSpeed|float||继续速度|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">NavigateTo</font> ]() ([Vector3]() target)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|寻路到某个位置||||
|**参数名称**|**类别**|**默认**|**描述**|
|target|Vector3||位置坐标|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetOneJumpTick</font> ]() ([int]() tickcount)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置一个跳跃行为||||
|**参数名称**|**类别**|**默认**|**描述**|
|tickcount|int||行为次数|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetEnableContinueJump</font> ]() ([bool]() enable)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置是否能连续跳跃||||
|**参数名称**|**类别**|**默认**|**描述**|
|enable|bool||是否能连续跳跃|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">StopNavigate</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|停止寻路||

|<div style="width:500px">[BehaviorState]() &emsp;[<font color="dd00dd">GetCurMoveState</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取当前行为状态||
|**返回类型**|**概要**|
|BehaviorState|行为状态枚举，见枚举`MNSandbox::BehaviorState`|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">UseDefaultAnimation</font> ]() ([bool]() use)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移动过程中使用默认的动作||||
|**参数名称**|**类别**|**默认**|**描述**|
|use|bool||是否使用默认动作|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Walking</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物行走时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物行走时触发，事件参数为（`bool isWalking`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isWalking|bool||行走是否触发|


|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Standing</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物站立时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物站立时触发，事件参数为（`bool isStanding`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isStanding|bool||站立是否触发|

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Jumping</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物跳跃时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物跳跃时触发，事件参数为（`bool isJumping`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isJumping|bool||跳跃是否触发|

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Flying</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物飞行时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物飞行时触发，事件参数为（`bool isFlying`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isFlying|bool||飞行是否触发|

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Died</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物死亡时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物死亡时触发，事件参数为（`bool isDied`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isDied|bool||死亡是否触发|

|<div style="width:500px">[SBXSignal\<BehaviorState, BehaviorState\>]() &emsp;[<font color="dd00dd">MoveStateChange</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|生物行为改变时触发，从一个行为改为另外一个行为||||
|**返回类型**|||**概要**|
|SBXSignal|||生物行为改变时触发，事件参数为（`BehaviorState beforeState, BehaviorState afterState`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|beforeState|BehaviorState||改变前的行为|
|afterState|BehaviorState||改变后的行为|

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">AvigateFinished</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|寻路结束时触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物寻路结束时触发，事件参数为（`bool isAvigateFinished`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAvigateFinished|bool||寻路结束是否触发|


|<div style="width:500px">[SBXSignal]() &emsp;[<font color="dd00dd">MoveFinished</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移动MoveTo结束后触发||||
|**返回类型**|||**概要**|
|SBXSignal|||移动`MoveTo`结束后触发|

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">MoveFinished</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移动`MoveTo`结束后触发（返回值有可能为空）||||
|**返回类型**|||**概要**|
|SBXSignal|||生物移动结束时触发，事件参数为（`bool isMoveFinished`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isMoveFinished|bool||移动MoveTo结束后触发|


------------------------------------------------------------------------------------------
## 示例代码

```
--创建实例
local newActor = SandboxNode.new('SceneActorObject')
--设置名字
newActor.Name = "my_actor"
--设置模型
newActor.ModelId = string.format("sandboxAsset://entity/%s/body.omod","100010")
--设置位置
newActor.Position = Vector3.new(500,700,500)
--设置父节点
newActor:SetParent(Workspace)
--设置速度
newActor.Movespeed = 2 
--监听MoveFineshed事件
newActor.MoveFinished:connect(function(isMoveFinished)
        print("actor move:"..tostring(isMoveFinished))
end)

newActor.Walking:connect(function()
        print("actor walking..")
end)
```