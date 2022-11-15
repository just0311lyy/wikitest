# UserInputService
------------------------------------------------------------------------------------------
## 描述

是一个服务，用于绑定处理用户输入
继承：`ServiceNode` 
另请参阅：`ContextActionService` 

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">TouchEnabled</font>]()</div>|
|:---|
|当前的设备是否有可用的触摸屏|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">KeyboardEnabled</font>]()</div>|
|:---|
|当前的设备是否有可用的键盘|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">MouseEnabled</font>]()</div>|
|:---|
|当前的设备是否有可用的鼠标|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">AccelerometerEnabled</font>]()</div>|
|:---|
|设备是否带有加速度计|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">GamepadEnabled</font>]()</div>|
|:---|
|用户正在使用的设备是否有可用的游戏手柄|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">GyroscopeEnabled</font>]()</div>|
|:---|
|用户的设备是否有陀螺仪|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">OnScreenKeyboardVisible</font>]()</div>|
|:---|
|屏幕键盘当前是否在用户的屏幕上可见|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">VREnabled</font>]()</div>|
|:---|
|用户是否正在使用头戴虚拟现实设备|


|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">OnScreenKeyboardPosition</font>]()</div>|
|:---|
|决定屏幕键盘的位置|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">MouseIconEnabled</font>]()</div>|
|:---|
|决定`Mouse`的图标是否可见|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">ModalEnabled</font>]()</div>|
|:---|
|切换`Roblox`的移动控制是否在移动设备上隐藏|


|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">MouseDeltaSensitivity</font>]()</div>|
|:---|
|缩放用户的`Mouse`的`Delta`（位置改变）输出|


|<div style="width:1125px">[MouseBehaviorEnum]() &emsp;[<font color="dd00dd">MouseBehavior</font>]()</div>|
|:---|
|用户的鼠标可以自由移动或是被锁定。参见枚举`UserInputService::MouseBehaviorEnum`|


|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">InputBegan</font>]()</div>|
|:---|
|开始输入|


|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">InputChanged</font>]()</div>|
|:---|
|输入改变|


|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">InputEnded</font>]()</div>|
|:---|
|输入结束|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">MouseBehavior</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|鼠标行为枚举|
|**名称**   |**值**  |**描述**|
|Default   |0   |自由移动|
|LockCenter|1   |锁定在中间|
|LockCurrentPosition|2   |锁定当前位置|


------------------------------------------------------------------------------------------
## 函数：

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">PickObjects</font> ]() ([float]() mouseX, [float]() mouseY, [vector/<sandboxNode/>]() objects)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|从给定的`obj`列表中，根据传入的2D屏幕坐标，拾取指定对象||||
|**参数名称**|**类别**|**默认**|**描述**|
|mouseX|float||指定屏幕位置坐标 x|
|mouseY|float||指定屏幕位置坐标 y|
|objects|vector<SandboxNode>||SandboxNode数组：给定的列表|
|**返回类型**|||**概要**|
|SandboxNode|||拾取到的对象|


|<div style="width:500px">[Vector2]() &emsp;[<font color="dd00dd">GetMouseLocation</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取鼠标当前坐标||
|**返回类型**|**概要**|
|Vector2|鼠标坐标|


|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsKeyDown</font> ]() ([int]() key)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|按键是否按下||||
|**参数名称**|**类别**|**默认**|**描述**|
|key|int||按键值|
|**返回类型**|||**概要**|
|bool|||是否按下|


------------------------------------------------------------------------------------------
## 事件：

|<div style="width:500px">[SBXSignal\<InputObject inputObj, bool bGameProcessed\>]() &emsp;[<font color="dd00dd">InputBegan</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`InputBegan`事件会在用户开始使用人机交互设备时触发<br>（例如按下鼠标键）||||
|**返回类型**|||**概要**|
|SBXSignal|||按下鼠标键，触发`InputBegan`事件，参数为（`InputObject inputObj, bool bGameProcessed`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|inputObj|InputObject|||
|bGameProcessed|bool|||


|<div style="width:500px">[SBXSignal\<InputObject inputObj, bool bGameProcessed\>]() &emsp;[<font color="dd00dd">InputChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`InputChanged`事件会在用户已开始输入，并且中间状态发生改变时触发，<br>例如鼠标位置等||||
|**返回类型**|||**概要**|
|SBXSignal|||按下鼠标键，触发`InputChanged`事件，参数为（`InputObject inputObj, bool bGameProcessed`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|inputObj|InputObject|||
|bGameProcessed|bool|||


|<div style="width:500px">[SBXSignal\<InputObject inputObj, bool bGameProcessed\>]() &emsp;[<font color="dd00dd">InputEnded</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`InputEnded`事件会在用户结束某次输入时触发||||
|**返回类型**|||**概要**|
|SBXSignal|||用户结束某次输入时触发`InputEnded`事件，参数为（`InputObject inputObj, bool bGameProcessed`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|inputObj|InputObject|||
|bGameProcessed|bool|||


------------------------------------------------------------------------------------------
## 示例代码

```lua
local UserInputService = game:GetService("UserInputService")

local function inputBegagn( inputObj, bGameProcessd )
        print("InputBegan")
        print( inputObj.UserInputState )   -- 0 这里都是InputBeagn 
        if inputObj.UserInputType == Enum.UserInputType.Keyboard.Value then
            print( "keyPressed" )
            print( inputObj.KeyCode )
        end
        if inputObj.UserInputType == Enum.UserInputType.MouseButton1.Value then
            print( "left pressed" )
            print( inputObj.Position.x ) -- 鼠标左键按下时位置
        end
end

UserInputService.InputBegan:Connect(inputBegagn)
```