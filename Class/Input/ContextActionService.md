# ContextActionService
------------------------------------------------------------------------------------------
## 描述

是一个服务，用于将用户输入动态绑定到上下文中，支持优先级绑定，优先级高的回调函数先调用
继承：`ServiceNode` 
另请参阅：`UserInputService` 

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">Action</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|输入行为枚举|
|**名称**   |**值**  |**描述**|
|KEYBOARD   |0   |键盘输入|
|MOUSE|1   |鼠标输入|
|GAMEPAD  |2   |游戏手柄输入|
|CAMERA_INPUT  |3   |相机输入|

|<div style="width:200px">ContextActionResult</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|控制着多个绑定动作的行为，可以用它给出的选项来设置某绑定动作对输入事件进行阻止还是放行，意思就是其他东西（包括其他绑定动作）可以对其进行处理。|
|**名称**   |**值**  |**描述**|
|Sink   |0   |如果`ContextActionService:BindAction`的`functionToBind`返回了`Enum.ContextActionResult.Sink`，那么输入事件就会停止于该函数，而其他位于其下的绑定动作则不会停止。这是默认的行为，前提是 functionToBind 没有返回任何值或者没有产生任何结果|
|Pass|1   |如果ContextActionService:BindAction的 functionToBind 返回了 Enum.ContextActionResult.Pass，那么就认为输入事件没有被 functionToBind 处理过，就会继续将输入事件传送到与相同的输入类型绑定的动作上。|


|<div style="width:200px">ContextActionPriority</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|用来给上下文动作设置优先级，优先级决定了上下文动作的顺序|
|**名称**   |**值**  |**描述**|
|Low   |0   |低优先级|
|Medium|1   |中等优先级|
|Default  |2   |默认优先级|
|High  |3   |高优先级|

|<div style="width:200px">ContextActionType</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|`action`输入类型枚举:用户输入;键盘输入|
|**名称**   |**值**  |**描述**|
|UserInputType   |0   |用户输入，对应`Enum.UserInputType`|
|KeyBoard|1   |键盘输入，对应`Enum.KeyCode`|

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">BindAction</font> ]() ([string]() actionName, [LuaFunction]() func, [int]() nActionType, [int]() nSubType)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|绑定一个回调函数到指定输入上||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，代表本次绑定|
|func|LuaFunction||lua回调函数（三个参数1. `actionName`类型：`string`描述：最初传递给`BindAction` 的相同字符串;2.`state`类型：`int`描述：当前事件的输入状态，等于`UserInputState`中的值;3.`inputObj 类型：`InputObject`描述：携带输入信息的对象）|
|nActionType|int||`ContextActionType`中的输入类型，参见枚举`ContextActionType`|
|nSubType|int||`UserInputType`或`Enum.KeyCode`的类型的类型|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">BindActionAtPriority</font> ]() ([string]() actionName, [LuaFunction]() func, [int]() priority, [int]() nActionType, [int]() nSubType)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|绑定一个回调函数到指定输入上，并指定优先级||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，代表本次绑定|
|func|LuaFunction||lua回调函数（三个参数1. `actionName`类型：`string`描述：最初传递给`BindAction` 的相同字符串;2.`state`类型：`int`描述：当前事件的输入状态，等于`UserInputState`中的值;3.`inputObj 类型：`InputObject`描述：携带输入信息的对象）|
|priority|int||指定的优先级，数字越大优先级越高|
|nActionType|int||`ContextActionType`中的输入类型，参见枚举`ContextActionType`|
|nSubType|int||`UserInputType`或`Enum.KeyCode`的类型的类型|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">UnbindAction</font> ]() ([string]() actionName)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|取消指定的用户绑定||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应`BindAction`中使用的绑定名称|

|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">UnbindAllActions</font>]()</div>|
|:---|
|移除所有的函数绑定|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">BindActivate</font> ]() ([int]() userInputTypeForActivate, [int]() keyCodeForActivate)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|绑定激活||||
|**参数名称**|**类别**|**默认**|**描述**|
|userInputTypeForActivate|int||绑定激活用户输入类型|
|keyCodeForActivate|int||绑定激活键盘输入类型|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">UnbindActivate</font> ]() ([int]() userInputTypeForActivate, [int]() keyCodeForActivate)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|绑定激活||||
|**参数名称**|**类别**|**默认**|**描述**|
|userInputTypeForActivate|int||绑定激活用户输入类型|
|keyCodeForActivate|int||绑定激活键盘输入类型|

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">GetAllBoundActionInfo</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|（c++方法还未实现）||
|**返回类型**|**概要**|
|ReflexMap||

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">GetBoundActionInfo</font> ]() ([string]() actionName)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|**返回类型**|||**概要**|
|ReflexMap||||


|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetButton</font> ]() ([string]() actionName)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|通过绑定名称获取该按钮节点（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|**返回类型**|||**概要**|
|SandboxNode|||获取绑定的按钮节点|


|<div style="width:500px">[string]() &emsp;[<font color="dd00dd">GetCurrentLocalToolIcon</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|（c++方法还未实现）||
|**返回类型**|**概要**|
|string||

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetDescription</font> ]() ([string]() actionName, [string]() description)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|description|string|||

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetImage</font> ]() ([string]() actionName, [string]() image)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|image|string|||

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetPosition</font> ]() ([string]() actionName, [unordered_map\<string, int\>]() position)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|position|unordered_map<string, int>|||

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetTitle</font> ]() ([string]() actionName, [string]() title)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|（c++方法还未实现）||||
|**参数名称**|**类别**|**默认**|**描述**|
|actionName|string||自定义的名称，对应 BindAction 中使用的绑定名称|
|title|string|||


------------------------------------------------------------------------------------------
## 示例代码

```lua
local ContextActionService = game:GetService("ContextActionService")
local curActionName = "moveForwardAction"
local function handleMoveForward(actionName, inputState, inputObj)
    print(actionName)     -- 打印 moveForwardAction
    if inputState == Enum.UserInputState.InputBegin.Value then
        self.ForwardBackValue = 1
    else
        self.ForwardBackValue = 0
    end
    self.LocalCharacter:Move(Vector3.New(self.LeftRightValue,0,self.ForwardBackValue),true)
end
ContextActionService:BindAction(
    curActionName, 
    handleMoveForward, 
    Enum.ContextActionType.KeyBoard.Value, 
    Enum.KeyCode.W.Value )
```