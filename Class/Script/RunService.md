# RunService
-----------------------------------------------------------------------------------------
#### 描述

此类是一个服务！它是顶级单例，可以使用`GetService`函数获取。
包含了用于时间管理的方法和事件，以及管理游戏或脚本所处于的内容。
继承：`ServiceNode `

------------------------------------------------------------------------------------------
#### 属性：

------------------------------------------------------------------------------------------
#### 枚举：

|<div style="width:200px">RenderPriority</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|渲染优先级枚举|
|名称   |值  |描述|
|First   |0   |优先运行|
|Input|100   |此项应当第 2 位运行|
|Camera  |200   |在 Input（输入）后运行|
|Character  |300   |在 Camera（镜头）后运行|
|Last  |400   |后在 Character 后运行|


------------------------------------------------------------------------------------------
#### 函数：

|<div style="width:500px">bool IsClient()</div>|<div style="width:598px"></div>|
|:---|:---|
|返回当前的环境是否运行在客户端上||
|返回类型|概要|
|bool|true, 运行在客户端上; false, 运行在服务端上|

|<div style="width:500px">bool IsServer()</div>|<div style="width:598px"></div>|
|:---|:---|
|返回当前的环境是否运行在服务器上||
|返回类型|概要|
|bool|true, 运行在服务器上; false, 运行在客户端上|

|<div style="width:500px">bool IsRemote()</div>|<div style="width:598px"></div>|
|:---|:---|
|返回当前的环境是否远程||
|返回类型|概要|
|bool|返回true，表示当前的环境是远程|

|<div style="width:500px">bool IsEdit()</div>|<div style="width:598px"></div>|
|:---|:---|
|返回当前运行环境是否为 Edit（编辑）模式||
|返回类型|概要|
|bool|true, 运行在Edit模式; false, 未运行在Edit模式|

|<div style="width:500px">bool IsRunMode()</div>|<div style="width:598px"></div>|
|:---|:---|
|返回当前运行环境是否为Running模式||
|返回类型|概要|
|bool|true, 当前运行在Running模式; false, 当前运行在编辑模式或者Pause模式|

|<div style="width:1125px">void Pause()</div>|
|:---|
|如果游戏在运行则暂停游戏的模拟，暂停物理运算和脚本|

|<div style="width:500px">void BindToRenderStep( string szKey, int priority, LuaFunction func )</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|绑定RenderStep事件的Lua函数||||
|参数名称|类别|默认|描述|
|szKey|string||Lua函数唯一标识|
|priority|int||函数调用的优先级（参考枚举`RenderPriority`）|
|func|LuaFunction||`Lua`函数的C++映射`LuaFunction`|

|<div style="width:500px">void UnbindFromRenderStep( string szKey )</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|解除绑定RenderStep事件的Lua函数||||
|参数名称|类别|默认|描述|
|szKey|string||Lua函数唯一标识|

|<div style="width:500px">double CurrentMilliSecondTimeStamp()</div>|<div style="width:598px"></div>|
|:---|:---|
|获取当前时间戳，精确到毫秒||
|返回类型|概要|
|double|毫秒时间戳 |

------------------------------------------------------------------------------------------
#### 事件：

|<div style="width:500px">SBXSignal<double> HeartBeat()</div>|<div style="width:598px"></div>|
|:---|:---|
|在物理模拟完成后每帧触发||
|返回类型|概要|
|double|毫秒时间戳 |

|<div style="width:500px">SBXSignal<double> PostSimulation()</div>|<div style="width:598px"></div>|
|:---|:---|
|在帧被模拟之后触发||
|返回类型|概要|
|double|毫秒时间戳 |

|<div style="width:500px">SBXSignal<double> PreRender()</div>|<div style="width:598px"></div>|
|:---|:---|
|在帧被渲染之前触发||
|返回类型|概要|
|double|毫秒时间戳 |

|<div style="width:500px">SBXSignal<double> PreSimulation()</div>|<div style="width:598px"></div>|
|:---|:---|
|在帧被模拟之前触发||
|返回类型|概要|
|double|毫秒时间戳 |

|<div style="width:500px">SBXSignal<double> RenderStepped()</div>|<div style="width:598px"></div>|
|:---|:---|
|在帧被渲染之前每帧触发||
|返回类型|概要|
|double|毫秒时间戳 |

|<div style="width:500px">SBXSignal Stepped()</div>|<div style="width:598px"></div>|
|:---|:---|
|每次Tick触发Stepped事件||
|返回类型|概要|
|double|毫秒时间戳 |


------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local RunService = game:GetService("RunService")
	local ret = RunService:isClient()
```