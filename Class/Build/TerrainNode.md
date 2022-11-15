# TerrainNode
------------------------------------------------------------------------------------------
## 描述

`Terrain`（地形）允许更改或者获取某个位置的方块以及方块实例；
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsAirBlock</font> ]() ([int]() x, [int]() y, [int]() z)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|位置在（x,y,z）的方块是否是空气方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|x|int||坐标x轴|
|y|int||坐标y轴|
|z|int||坐标z轴|
|**返回类型**|||**概要**|
|bool|||返回`true`表示该位置是空气方块|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">SetBlockAll</font> ]() ([int]() x, [int]() y, [int]() z, [int]() blockid, [int]() blockdata)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置位置（x,y,z）为XXX方块，并且设置该位置的`blockdata`||||
|**参数名称**|**类别**|**默认**|**描述**|
|x|int||坐标x轴|
|y|int||坐标y轴|
|z|int||坐标z轴|
|blockid|int||方块id|
|blockdata|int||方块data|
|**返回类型**|||**概要**|
|bool|||返回`true`表示设置成功|

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetBlockMaterial</font> ]() ([int]() x, [int]() y, [int]() z)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取位置（x,y,z）的方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|x|int||坐标x轴|
|y|int||坐标y轴|
|z|int||坐标z轴|
|**返回类型**|||**概要**|
|SandboxNode|||该坐标位置的方块|

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetBlockNode</font> ]() ([int]() x, [int]() y, [int]() z)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取位置（x,y,z）的方块实例||||
|**参数名称**|**类别**|**默认**|**描述**|
|x|int||坐标x轴|
|y|int||坐标y轴|
|z|int||坐标z轴|
|**返回类型**|||**概要**|
|SandboxNode|||返回该坐标位置的方块实例|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local TerrainNode = game.WorkSpace.Terrain
local posx, posy, posz = 0,0,1
local grassid = 100
local blockdata = 0
--在0,0,1位置放置一个草块
TerrainNode:SetBlockAll(posx, posy, posz, grassid, blockdata)
--查询0,0,1位置的方块是不是空气方块，ret:false
local ret = TerrainNode:IsAirBlock(posx, posy, posz)
--获取0,0,1位置的方块
local blockMtl = TerrainNode:GetBlockMaterial(posx, posy, posz)
--pos(0,0,1)is:grass
print("pos(0,0,1)is:"..tostring(blockMtl.Block_Name))
--设置0,0,1位置为楼梯方块
TerrainNode:SetBlockAll(posx, posy, posz, 376, 0)
--获取该位置的方块实例
local blockMtlInstance = TerrainNode:GetBlockNode(posx, posy, posz)
--更改楼梯朝向
blockMtlInstance.BlockData = 2
```