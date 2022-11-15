# SandboxNetService
------------------------------------------------------------------------------------------
## 描述

此类是一个服务！它是网络服务节点，可以使用 GetService 函数获取。负责网络服务。
继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 函数：（http[s] 基于CURL）

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">cancelAsync</font> ]() ([LuaNetIns]() id)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|终止http异步请求||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|LuaNetIns||`lua`异步请求`id`|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">waitAsync</font> ]() ([LuaNetIns]() id)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`block`当前`http`异步请求，直至返回数据或者失败<br>（仅限lua调用，C++调用无意义）||||
|**参数名称**|**类别**|**默认**|**描述**|
|id|LuaNetIns||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpGet</font> ]() ([string]() url)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步请求||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpDownload</font> ]() ([string]() url, [string]() filePath)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步下载||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|filePath|string||下载文件路径|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpUpload</font> ]() ([string]() url, [string]() filePath)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步下载||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|filePath|string||上传的文件路径|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpGetWithCB</font> ]() ([string]() url, [LuaNetCallBack]() callBack)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步请求，带有`callback`||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|callBack|LuaNetCallBack||回调函数|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpDownloadWithCB</font> ]() ([string]() url, [string]() filePath, [LuaNetCallBack]() callBack)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步下载，带有`callback`||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|filePath|string||下载文件路径|
|callBack|LuaNetCallBack||回调函数|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">asyncHttpUploadWithCB</font> ]() ([string]() url, [string]() filePath, [LuaNetCallBack]() callBack)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`http`异步上传，带有`callback`||||
|**参数名称**|**类别**|**默认**|**描述**|
|url|string||请求的`url`|
|filePath|string||上传文件路径|
|callBack|LuaNetCallBack||回调函数|
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


------------------------------------------------------------------------------------------
## 函数 (TCP/UDP/ICMP 功能，基于RakNet)


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">startSocket</font> ]() ([bool]() isHost, [int]() maxConnect, [int]() port4, [int]() port6)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|开始一个`socket client/service`||||
|**参数名称**|**类别**|**默认**|**描述**|
|isHost|bool|||
|maxConnect|int|||
|port4|int|||
|port6|int|||
|**返回类型**|||**概要**|
|LuaNetIns|||`lua`异步请求`id`|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">closeSocket</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|关闭一个`socket`||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|


|<div style="width:500px">[vector/<string/>]() &emsp;[<font color="dd00dd">getSocketAddress</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取当前`socket`的地址||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|**返回类型**|||**概要**|
|vector<string>|||当前`socket`的地址|


|<div style="width:500px">[vector/<string/>]() &emsp;[<font color="dd00dd">getIpAddress</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取当前`socket`的`ip`地址||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|**返回类型**|||**概要**|
|vector<string>|||当前`socket`的`ip`地址|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">setSocketEvent</font> ]() ([LuaNetIns]() ins, [LuaNetCallBack]() callBack)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置`socket`的`lua`回调||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|callBack|LuaNetCallBack||回调函数|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">writeMsgToSocket</font> ]() ([LuaNetIns]() ins, [string]() content, [string]() clientID)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|向`socket`写入内容||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|content|string||传输内容|
|clientID|string||客户端id|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">writeBinMsgToSocket</font> ]() ([LuaNetIns]() ins, [UInt8Vec]() content, [string]() clientID)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|向`socket`写入二进制数据包||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|content|UInt8Vec||二进制数据包`Binary::UInt8Vec`|
|clientID|string||客户端id|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">connectSocket</font> ]() ([LuaNetIns]() ins, [string]() ip, [short]() port)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`Socket client`链接`server`||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|ip|string||ip地址|
|port|unsigned short||端口号|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">ping</font> ]() ([LuaNetIns]() ins, [string]() ip, [short]() port)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`Socket client``ping`命令||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|ip|string||ip地址|
|port|unsigned short||端口号|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">disconnectSocket</font> ]() ([LuaNetIns]() ins, [string]() clientID)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|`Socket`断开连接||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`socket`请求`id`|
|clientID|string||客户端id|


------------------------------------------------------------------------------------------
## 函数 (WebSocket系列功能 基于WebSocket)

|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">startWebSocketClient</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|开启一个`webSocket client`||||
|**返回类型**|||**概要**|
|LuaNetIns|||`WebSocket`请求`id`|


|<div style="width:500px">[LuaNetIns]() &emsp;[<font color="dd00dd">startWebSocketServer</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|开启一个`webSocket server`||||
|**返回类型**|||**概要**|
|LuaNetIns|||`WebSocket`请求`id`|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">closeWebSocket</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|关闭一个`webSocket client/server`||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">setWebSocketEvent</font> ]() ([LuaNetIns]() ins, [LuaNetCallBack]() callBack)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置一个`webSocket lua`回调||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|
|callBack|LuaNetCallBack||`lua`回调函数|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">writeMsgToWebSocket</font> ]() ([LuaNetIns]() ins, [string]() content, [int]() clientID)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|向一个`webSocket`写入数据||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|
|content|string||传输内容|
|clientID|int||客户端id|

       
|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">writeBinMsgToWebSocket</font> ]() ([LuaNetIns]() ins, [UInt8Vec]() content, [int]() clientID)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|向一个`webSocket`写入二进制数据||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|
|content|UInt8Vec||二进制数据`Binary::UInt8Vec`|
|clientID|int||客户端id|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">setupWebSocketServer</font> ]() ([LuaNetIns]() ins, [short]() port)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置`websocket sever`监听端口，并开启工作线程（内部）||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|
|port|short||端口号|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">setWebSocketServerTimeout</font> ]() ([LuaNetIns]() ins, [int]() time)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置`webSocket server`超时事件||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`WebSocket`请求`id`|
|time|int||时间|


|<div style="width:500px">[vector/<int/>]() &emsp;[<font color="dd00dd">getWebSocketServerClients</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取一个`webSocket server`持有的`client`回话实例数组||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`webSocket`请求`id`|
|**返回类型**|||**概要**|
|vector<int>|||`client`回话实例数组|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">addWebSocketClientProtocol</font> ]() ([LuaNetIns]() ins, [string]() name)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|添加一个webSocket client支持的协议||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`webSocket`请求`id`|
|name|string||协议名|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">connectWebSocketClient</font> ]() ([LuaNetIns]() ins, [string]() url)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置一个`webSocket client`链接`sever`<br>(`websocket`支持`URL`中带`port`,所以不需要传递`port`)||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`webSocket`请求`id`|
|url|string||url名|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">disconnectWebSocketClient</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置断开一个`webSocket client`实例||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`webSocket`请求`id`|


|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">getWebSocketClientState</font> ]() ([LuaNetIns]() ins)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取当前一个`webSocket client`的状态（是否打开，是否可读写）||||
|**参数名称**|**类别**|**默认**|**描述**|
|ins|LuaNetIns||`webSocket`请求`id`|
|**返回类型**|||**概要**|
|int|||`client`状态值|

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

local function testBinaryMsg()
    local binaryMsg = UInt8Vec.new(0xff)
    for i = 1, 0xff do
        binaryMsg[i - 1] = i % 10 
    end
    return binaryMsg
end

local service = game:GetService("NetService")

-- test http cancel
local function testCancelAsync()
    local retIns = service:AsyncHttpGet2("https://www.baidu.com/",function(state,content) 
        utils.print("testCancel",state,#content)
    end)
    service:CancelAsync(retIns)
end
utils.run(testCancelAsync)

-- test http block
local function testWaitAsync()
    local retIns = service:AsyncHttpGet2("https://www.qq.com/",function(state,content) 
        utils.print("testWait1",state,#content)
    end)
    local state,content = service:WaitAsync(retIns)
    utils.print("testWait2",state,#content)
end
utils.run(testWaitAsync)

-- test http get not cb
local function testAsyncHttp()
    local retIns = service:AsyncHttpGet("https://www.baidu.com/")
    local state,content = service:WaitAsync(retIns)
    utils.print("testAsyncHttpNotCB",state,#content)
end
utils.run(testAsyncHttp)

local function testAsyncDownload()
    local retIns = service:AsyncHttpDownload("https://dgss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=1538486630,180396690&fm=30&app=106&f=JPEG?w=312&h=208&s=162C64A162A792FA5A3D1808030050C2","test_temp222.png")
    local state,content = service:WaitAsync(retIns)
    utils.print("testAsyncHttpNotCB",state,#content)
end
utils.run(testAsyncDownload)

local function testAsyncUpload()
    -- cd E:\nodejs && node .\index.js
    local retIns = service:AsyncHttpUpload("http://127.0.0.1:8889/upload","test_temp222.png")
    local state,content = service:WaitAsync(retIns)
    utils.print("testAsyncHttpNotCB",state,#content)
end
utils.run(testAsyncUpload)

--test http get not cb
local function commonFunc(state,content)
    utils.print("CommonFunc",state,#content)
end
local function testAsyncHttp()
    local retIns = service:AsyncHttpGet2("https://www.baidu.com/",commonFunc)
end
utils.run(testAsyncHttp)

local function testAsyncDownload()
    local retIns = service:AsyncHttpDownload2("https://dgss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=1538486630,180396690&fm=30&app=106&f=JPEG?w=312&h=208&s=162C64A162A792FA5A3D1808030050C2","test_temp222.png",commonFunc)
end
utils.run(testAsyncDownload)

local function testAsyncUpload()
    -- cd E:\nodejs && node .\index.js
    local retIns = service:AsyncHttpUpload2("http://127.0.0.1:8889/upload","test_temp222.png",commonFunc)
end
utils.run(testAsyncUpload)

local function testStartSocketServer()
    local ins = service:StartSocket(true,10,8889,0)
    local address = service:GetSocketAddress(ins)
    for i,v in ipairs(address) do
        utils.print('address ', i, v)
    end
    local ipAddress = service:GetIpAddress(ins)
    for i,v in ipairs(ipAddress) do
        utils.print('ipAddress ', i, v)
    end
    -- service:CloseSocket(ins)
    local function handleMsg(msgType,fromClient,msg)
        if msgType == 2 then
            --reply to client peer
            utils.print("rec from",fromClient,#msg)
            service:WriteMsgToPeer(ins,"msg rec ack",fromClient)
            wait(1)
            service:DisconnectFromPeer(ins,fromClient)
            wait(10)
            service:CloseSocket(ins)
        elseif msgType == 0 then
            utils.print("client",fromClient,"connected")
            service:WriteMsgToPeer(ins,"Welcome",fromClient)
        elseif msgType == 1 then
            utils.print("client",fromClient, "disconnected")
        end
    end
    service:SetSocketEvent(ins,handleMsg)
end
utils.run(testStartSocketServer)

local function testStartSocketClient()
    local ins = service:StartSocket(false,1,8888,0)
    local address = service:GetSocketAddress(ins)
    local function handleMsg(msgType,msg)
        if msgType == 0 then
            utils.print("connect failure")
        elseif msgType == 1 then
            utils.print("connect success")
            service:WriteMsgToPeer(ins,"send hand shake msg to server","")
        elseif msgType == 2 then
            utils.print("client rec success")
        elseif msgType == 3 then
            utils.print("recv ping cost time", msg)
        end
    end
    service:SetSocketEvent(ins,handleMsg)
    service:PingToPeer(ins,"127.0.0.1",8889)
    wait(2)
    service:ConnectToPeer(ins,"127.0.0.1",8889)
    wait(2)
end
utils.run(testStartSocketClient)

local function testStartWebSocketServer()
    local ins = service:StartWebSocketServer()
    service:SetWebSocketServerTimeout(ins,5000)
    local isFirstRecMsg = false
    local function handleMsg(msgType,fromClient,msg)
        if msgType == 2 then
            --reply to client
            utils.print("rec from",fromClient,#msg)
            if not isFirstRecMsg then
                -- isFirstRecMsg = true
                -- service:WriteMsgToWebSocket(ins,"first msg rec",fromClient)
                -- wait(10)
                -- service:CloseWebSocket(ins)
            end
        elseif msgType == 3 then
            utils.print("client",fromClient,"disconnected")
        elseif msgType == 1 then
            utils.print("client",fromClient, "connected")
            service:WriteMsgToWebSocket(ins,"Welcome",fromClient)
        end
    end
    service:SetWebSocketEvent(ins,handleMsg)
    service:SetupWebSocketServer(ins,8888)
end
utils.run(testStartWebSocketServer)

local function testStartWebSocketClient()
    local ins = service:StartWebSocketClient()
    local isFirstRecMsg = false
    local function handleMsg(msgType,msg)
        if msgType == 0 then
            utils.print("connected")
            -- service:WriteMsgToWebSocket(ins,"I am connected!!!",0)
            -- local binaryMsg = UInt8Vec.new()
            local msg = testBinaryMsg()
            service:WriteBinMsgToWebSocket(ins,msg,0)
        elseif msgType == 1 then
            utils.print("disconnected")
        elseif msgType == 2 then
            utils.print("client rec msg",#msg)
            if not isFirstRecMsg then
                isFirstRecMsg = true
                wait(1)
                service:DisconnectWebSocketClient(ins)
                wait(2)
                service:CloseWebSocket(ins)
            end
        elseif msgType == 3 then
            utils.print("onError",msg)
        elseif msgType == 4 then
            -- utils.print("onStateChange")
        end
    end
    service:SetWebSocketEvent(ins,handleMsg)
    service:AddWebSocketClientProtocol(ins,"default-protocol")
    service:ConnectWebSocketClient(ins,"ws://127.0.0.1:8888")
end
utils.run(testStartWebSocketClient)

local function testBinary()
    local binaryMsg = UInt8Vec.new(0xff)
    for i = 1, 0xff do
        binaryMsg[i - 1] = i % 10 
    end
    utils.print(binaryMsg.Length)
    utils.print(binaryMsg[0],binaryMsg[1],binaryMsg[9])
    local str = binaryMsg:ToStr(true)
    utils.print(binaryMsg.Length,#str)
end
utils.run(testBinary)
```