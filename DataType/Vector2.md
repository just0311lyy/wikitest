# Vector2
------------------------------------------------------------------------------------------
## 描述

描述二维空间中的一个 `[vector]`（矢量）
注意：构造之后只读，对于实例中的 x/y 进行修改是无意义的（查看示例）

------------------------------------------------------------------------------------------
## 属性


|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">x</font>]()</div>|
|:---|
|x坐标|


|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">y</font>]()</div>|
|:---|
|y坐标|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local v1 = Vector2.new(100,100)
local v2 = Vector2.new(50,50)

local v3 = v1 + v2
local v4 = v1 - v2
local v5 = v1*v2
local v6 = v1/v2
local v7 = -v1

print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y))
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y))
print("v3 x:"..tostring(v3.x).." y:"..tostring(v3.y))
print("v4 x:"..tostring(v4.x).." y:"..tostring(v4.y))
print("v5 x:"..tostring(v5.x).." y:"..tostring(v5.y))
print("v6 x:"..tostring(v6.x).." y:"..tostring(v6.y))
print("v7 x:"..tostring(v7.x).." y:"..tostring(v7.y))

--v1 x:100 y:100
--v2 x:50 y:50
--v3 x:150 y:150
--v4 x:50 y:50
--v5 x:5000 y:5000
--v6 x:2 y:2
--v7 x:-100 y:-100
Vector2.Normalize(v1)
print("v1 x:"..tostring(v1.x).." y:"..tostring(v1.y))
--v1 x:0.70710682868958 y:0.70710682868958
v2:Normalize()
print("v2 x:"..tostring(v2.x).." y:"..tostring(v2.y))
--v2 x:0.70710682868958 y:0.70710682868958

-- 构造之后只读
Vector2.new(102,100).x = 300
```