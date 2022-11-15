# CloudService
------------------------------------------------------------------------------------------
## 描述

此类是一个服务！它是`Cloud`节点，可以使用`GetService`函数获取。负责`Cloud`服务。
继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">setValue</font> ]() ([lua_State*]() L, [string]() key, [string]() name, [string]() value)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|同步设置KV值||||
|**参数名称**|**类别**|**默认**|**描述**|
|L|lua_State|||
|key|string|||
|name|string|||
|value|string|||
|**返回类型**|||**概要**|
|int||||


|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">getValue</font> ]() ([lua_State*]() L, [string]() key, [string]() name)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|同步请求kv值||||
|**参数名称**|**类别**|**默认**|**描述**|
|L|lua_State|||
|key|string|||
|name|string|||
|**返回类型**|||**概要**|
|int||||

|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">setValueAsync</font> ]() ([lua_State*]() L, [string]() key, [string]() name, [string]() value, [LuaFunction]() func)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|异步设置KV值||||
|**参数名称**|**类别**|**默认**|**描述**|
|L|lua_State|||
|key|string|||
|name|string|||
|value|string|||
|func|LuaFunction|||
|**返回类型**|||**概要**|
|int||||


|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">getValueAsync</font> ]() ([lua_State*]() L, [string]() key, [string]() name, [LuaFunction]() func)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|异步获取KV值||||
|**参数名称**|**类别**|**默认**|**描述**|
|L|lua_State|||
|key|string|||
|name|string|||
|func|LuaFunction|||
|**返回类型**|||**概要**|
|int||||


------------------------------------------------------------------------------------------
## 代码示例

```lua
local utils = {}
function utils.run(func)
    local status,err,ret = xpcall(func,debug.traceback)
    if not status then
        print("err = " .. tostring(err))
        print("ret = " .. tostring(ret))
    end
end

function utils.print(...)
    local args = {...}
    args[#args + 1] = '\n'
    local tab = {}
    for i, v in ipairs(args) do
        tab[i] = tostring(v)
    end
    print(table.concat(tab,' '))
end

utils.run(function() 
    local service = game:GetService("CloudService")

    local status,value = service:setValue("test_1","global","20000")
    utils.print("1111",status,value)

    status,value = service:getValue("test_1","global")
    utils.print("22222",status,value)

    service:setValueAsync("test_1","global","30000",function(status, value) 
        utils.print("33333",status,value)
    end)

    service:getValueAsync("test_1","global",function(status, value) 
        utils.print("44444",status,value)
    end)


    local idx = 0
    while idx <= 40 do
        wait(1)
        utils.print("55555",idx)
        idx = idx + 1
    end
end)

print("finish")


--[[
线程 0x50cc 已退出，返回值为 0 (0x0)。
线程 0x5070 已退出，返回值为 0 (0x0)。
my log "[path:game.WorkSpace.ScriptObject] 1111 true 20000 \n"
线程 0x5d78 已退出，返回值为 0 (0x0)。
线程 0x57f8 已退出，返回值为 0 (0x0)。
my log "[path:game.WorkSpace.ScriptObject] 22222 true 20000 \n"
线程 0x11f0 已退出，返回值为 0 (0x0)。
线程 0x519c 已退出，返回值为 0 (0x0)。
my log "[path:game.WorkSpace.ScriptObject] 33333 true 30000 \n"
[WRN] OutputWASAPI::mixerThread                : Starvation detected in WASAPI output buffer!
线程 0x3d08 已退出，返回值为 0 (0x0)。
线程 0xadc 已退出，返回值为 0 (0x0)。
my log "[path:game.WorkSpace.ScriptObject] 44444 true 30000 \n"

my log "[path:game.WorkSpace.ScriptObject] 55555 0 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 1 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 2 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 3 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 4 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 5 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 6 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 7 \n"
my log "[path:game.WorkSpace.ScriptObject] 55555 8 \n"
]]

```