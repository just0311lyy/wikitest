# Rect
------------------------------------------------------------------------------------------
## 描述

矩形数据类型，包含四个属性:
- Left
- Right
- Top
- Bottom

注意：构造之后只读

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Left</font>]()</div>|
|:---|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Right</font>]()</div>|
|:---|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Top</font>]()</div>|
|:---|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Bottom</font>]()</div>|
|:---|

------------------------------------------------------------------------------------------
## 代码示例

```lua
local rect = Rect.new(0,1,2,3)
print("Left:"..tostring(rect.Left).." Right:"..tostring(rect.Right).." Top:"..tostring(rect.Top).." Bottom:"..tostring(rect.Bottom))
--Left:0 Right:2 Top:1 Bottom:3
```