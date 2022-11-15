# SandboxFriendsService
------------------------------------------------------------------------------------------
## 描述

是一个服务，可以获取好友数量，根据索引获取好友的信息
继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">GetSize</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取好友数量||
|**返回类型**|**概要**|
|int|获取好友数量|

|<div style="width:500px">[ReflexTuple]() &emsp;[<font color="dd00dd">GetFriendsInfoByIndex</font> ]() ([int]() index)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|根据好友的序列号拿到好友信息||||
|**参数名称**|**类别**|**默认**|**描述**|
|index|int||好友数的序列号|
|**返回类型**|||**概要**|
|ReflexTuple|||好友信息 [uin(好友的uin), nickName(好友昵称), onLine(好友是否在线)]|


------------------------------------------------------------------------------------------
## 示例代码

```lua
------ 判断某人是否是好友 ----------
local function checkFriends(playerUin) 
    local friendsService = game:GetService("FriendsService")
    local friendsNum = friendsService:GetSize() --获取好友数（总序列号）
    for i = 0,friendsNum-1,1 do --初值,终值，步数
        local uin,nickName,onLine = friendsService:GetFriendsInfoByIndex(i) --遍历好友
        local isFriend = false
        if playerUin == uin then --比对该uin和拉去的好友列表
            isFriend = true
        end
        if isFriend then
            print("%s: is friend",nickName)
        else
            print("%s: is not friend",nickName)
        end
    end
end
local playerUin = 1111  --已知某人的uin信息
checkFriends(playerUin)
```