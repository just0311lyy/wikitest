# RemoteEvent
-----------------------------------------------------------------------------------------
## 描述
`RemoteEvent`（远程事件）的作用是在客户端和服务器端之间提供一个单向讯息传播途径，它允许`Script`（脚本）和`LocalScript`（本地脚本）之间互相调用其内部的代码。讯息可以由客户端传向服务器端，也可以由服务器端传向特定的客户端，还可以由服务器端传给所有客户端。

为了让服务器端和客户端都能使用远程事件，`RemoteEvent`对象必须处于一个能让服务器端和客户端双方都能看到的位置，`RemoteEvent`要求存储在`MainStorage`里面。

-----------------------------------------------------------------------------------------
## 属性

-----------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">fireServer</font> ]() ([ReflexTuple]() arguments)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|在服务器端用同样的参数触发`RemoteEvent.OnServerNotify`事件，前面外加一个玩家参数||||
|**参数名称**|**类别**|**默认**|**描述**|
|arguments|ReflexTuple|||


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">fireClient</font> ]() ([int]() client_uin, [ReflexTuple]() arguments)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|为指定的玩家触发`RemoteEvent.OnClientNotify`事件||||
|**参数名称**|**类别**|**默认**|**描述**|
|int|client_uin|||
|arguments|ReflexTuple|||


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">fireAllClients</font> ]() ([ReflexTuple]() arguments)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|在每个客户端触发`RemoteEvent.OnClientNotify`事件||||
|**参数名称**|**类别**|**默认**|**描述**|
|arguments|ReflexTuple|||

-----------------------------------------------------------------------------------------
## 事件


|<div style="width:500px">[SBXSignal\<int, ReflexTuple\>]() &emsp;[<font color="dd00dd">OnServerNotify</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|当`RemoteEvent.fireClient`或`RemoteEvent.fireAllClients`从`Script`调用时触发`LocalScript`内的监听函数||||
|**返回类型**|||**概要**|
|SBXSignal|||事件参数为（`int ReflexTuple`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
||int|||
||ReflexTuple|||


|<div style="width:500px">[SBXSignal\<ReflexTuple\>]() &emsp;[<font color="dd00dd">OnClientNotify</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|从一个`LocalScript`中调用 `RemoteEvent.fireServer`时触发`Script`中的监听函数||||
|**返回类型**|||**概要**|
|SBXSignal|||事件参数为（`ReflexTuple`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
||ReflexTuple|||


-----------------------------------------------------------------------------------------
## 示例代码

* **脚本中创建RemoteEvent(注意要求其父节点必须是MainStorage)**
```lua
--代码中动态创建RemoteEvent示例 
local mainStorageService = game:GetService("MainStorage")
local node1 = SandboxNode.new('RemoteEvent')
node1.Name = "test_remoteevent_name"
node1:SetParent(mainStorageService)
```

* **`RemoteEvent：`服务器至多个客户端**
	
	通过远程事件，服务器能够以两种形式将消息发送给客户端：
	1. 服务器向单独指定客户端发送消息
	2. 服务器同时向所有客户端发送消息。

	如果要想将消息发送给所有客户端，服务器需要对 RemoteEvent:fireAllClients 进行调用。需要注意的是，在此情况下无需将玩家作为参数进行传递（由于函数将为所有连接至服务器的客户端触发远程事件）。

  **如果需要监听此事件时，每个客户端都需要将函数连接至 OnClientNotify。**

	```lua
	--服务端的发送脚本
	local mainStorageService = game:GetService("MainStorage")
	--这里的testnoargs是一个RemoteEvent类型的实例,它的name = "testnoargs"
	--这里的testargs 是一个RemoteEvent类型的实例,它的name = "testargs "
	--都是预先在编辑地图时预先创建好的事件
	local testnoargs = mainStorageService:WaitForChild("testnoargs")
	local target_client_uin = 1000072589--for test
	testnoargs:fireClient( target_client_uin )

	local testargs   = mainStorageService:WaitForChild("testargs")
	testargs:fireAllClients(123,"abc")
	```

	```lua
	--客户端的监听脚本localScript
	local mainStorageService = game:GetService("MainStorage")

	--这里的testnoargs是一个RemoteEvent类型的实例,它的name = "testnoargs"
	--这里的testargs 是一个RemoteEvent类型的实例,它的name = "testargs "
	--都是预先在编辑地图时预先创建好的事件

	local testnoargs = mainStorageService:WaitForChild("testnoargs")

	testnoargs.OnClientNotify:connect(function()
	    print("client recv testnoargs event from server")
	end)

	local testargs = mainStorageService:WaitForChild("testargs")
	testargs.OnClientNotify:connect(function(arg1, arg2)
	    print("client recv testargs event from server:"..tostring(arg1)..tostring(arg2))
	end)
	```

* **`RemoteEvent：`客户端至服务器端**

	要想从客户端发送一条消息到服务器端，就需要在`LocalScript`中执行函数`RemoteEvent:fireServer`。<br>
	与此同时，服务器端要监听通知`OnServerNotify`。<br>
	当客户端调用`fireServer`函数时，所有订阅`OnServerNotify`通知的服务器端的监听函数都会执行，注意这个过程不会立刻开始：过程的进展速度取决于客户端和服务器端之间的网络连接状况。<br>
	当从一个客户端向服务器端发送一个 RemoteEvent 的时候，可以自由携带参数。

	```lua
	--服务端的监听脚本
	local mainStorageService = game:GetService("MainStorage")

	--这里的testnoargs是一个RemoteEvent类型的实例,它的name = "testnoargs"
	--这里的testargs 是一个RemoteEvent类型的实例,它的name = "testargs "
	--都是预先在编辑地图时预先创建好的事件

	local testnoargs = mainStorageService:WaitForChild("testnoargs")

	testnoargs.OnServerNotify:connect(function(uin)
	    print("server recv testnoargs event from client:"..tostring(uin))
	end)

	local testargs = mainStorageService:WaitForChild("testargs")
	testargs.OnServerNotify:connect(function(uin, arg1, arg2)
	    print("server recv testargs event from client:"..tostring(uin),  tostring(arg1),tostring(arg2))
	end)
	```

	```lua
	----客户端的localScript脚本  向服务器发送远程事件
	wait(1)
	local mainStorageService = game:GetService("MainStorage")
	local testnoargs = mainStorageService:WaitForChild("testnoargs")        
	print("testnoargs:fireServer()")
	testnoargs:fireServer()
	wait(1)
	local testargs = mainStorageService:WaitForChild("testargs")        
	testargs:fireServer(1325,"abc")
	print("testargs:fireServer() arg1: 1325 arg2: abc")
	```