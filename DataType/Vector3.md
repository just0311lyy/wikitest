# Vector3
------------------------------------------------------------------------------------------
## 描述

描述三维空间中的一个`[vector]`（矢量）
注意：构造之后只读，对于实例中的 x/y/z 进行修改是无意义的

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">x</font>]()</div>|
|:---|
|x坐标|


|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">y</font>]()</div>|
|:---|
|y坐标|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">z</font>]()</div>|
|:---|
|z坐标|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local v1 = Vector3.new(100,100,100)
local v2 = Vector3.new(50,50,50)

local v3 = v1 + v2
local v4 = v1 - v2
local v5 = v1*v2
local v6 = v1/v2
local v7 = -v1


print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y).." z:"..tostring(v1.z))
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y).." z:"..tostring(v2.z))
print("v3 x:"..tostring(v3.x).." y:"..tostring(v3.y).." z:"..tostring(v3.z))
print("v4 x:"..tostring(v4.x).." y:"..tostring(v4.y).." z:"..tostring(v4.z))
print("v5 x:"..tostring(v5.x).." y:"..tostring(v5.y).." z:"..tostring(v5.z))
print("v6 x:"..tostring(v6.x).." y:"..tostring(v6.y).." z:"..tostring(v6.z))
print("v7 x:"..tostring(v7.x).." y:"..tostring(v7.y).." z:"..tostring(v7.z))

--v1 x:100 y:100 z:100
--v2 x:50 y:50 z:100
--v3 x:150 y:150 z:150
--v4 x:50 y:50 z:50
--v5 x:5000 y:5000 z:5000
--v6 v6 x:2 y:2 z:2
--v7 x:-100 y:-100 z:-100
Vector3.Normalize(v1)
print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y).." z:"..tostring(v1.z))
--v1 x:0.57735025882721 y:0.57735025882721 z:0.57735025882721
v2:Normalize()
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y).." z:"..tostring(v2.z))
--v2 x:0.57735025882721 y:0.57735025882721 z:0.57735025882721
```