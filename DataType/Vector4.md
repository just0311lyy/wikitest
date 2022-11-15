# Vector4
------------------------------------------------------------------------------------------
## 描述

描述4维空间中的一个`[vector]`（矢量）
注意：构造之后只读，对于实例中的 x/y/z/w 进行修改是无意义的

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

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">w</font>]()</div>|
|:---|
|w坐标|


------------------------------------------------------------------------------------------
## 示例代码

```lua
local v1 = Vector4.new(100,100,100,1)
local v2 = Vector4.new(50,50,50,1)

local v3 = v1 + v2
local v4 = v1 - v2
local v5 = v1*v2
local v6 = v1/v2
local v7 = -v1


print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y).." z:"..tostring(v1.z).." w:"..tostring(v1.w))
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y).." z:"..tostring(v2.z).." w:"..tostring(v2.w))
print("v3 x:"..tostring(v3.x).." y:"..tostring(v3.y).." z:"..tostring(v3.z).." w:"..tostring(v3.w))
print("v4 x:"..tostring(v4.x).." y:"..tostring(v4.y).." z:"..tostring(v4.z).." w:"..tostring(v4.w))
print("v5 x:"..tostring(v5.x).." y:"..tostring(v5.y).." z:"..tostring(v5.z).." w:"..tostring(v5.w))
print("v6 x:"..tostring(v6.x).." y:"..tostring(v6.y).." z:"..tostring(v6.z).." w:"..tostring(v6.w))
print("v7 x:"..tostring(v7.x).." y:"..tostring(v7.y).." z:"..tostring(v7.z).." w:"..tostring(v7.w))

--v1 x:100 y:100 z:100 w:1
--v2 x:50 y:50 z:50 w:1
--v3 x:150 y:150 z:150 w:2
--v4 x:50 y:50 z:50 w:0
--v5 x:5000 y:5000 z:5000 w:1
--v6 x:2 y:2 z:2 w:1
--v7 x:-100 y:-100 z:-100 w:-1
Vector4.Normalize(v1)
print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y).." z:"..tostring(v1.z).." w:"..tostring(v1.w))
--v1 x:0.5773406624794 y:0.5773406624794 z:0.5773406624794 w:0.0057734064757824
v2:Normalize()
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y).." z:"..tostring(v2.z).." w:"..tostring(v2.w))
--v2 x:0.57731175422668 y:0.57731175422668 z:0.57731175422668 w:0.011546235531569
```