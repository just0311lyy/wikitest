# SceneUIImage
------------------------------------------------------------------------------------------
## 描述

2d界面图片节点
继承：`SceneUIComponent`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Icon</font>]()</div>|
|:---|
|图片资源路径|

|<div style="width:1125px">[EnumFillMethod]() &emsp;[<font color="dd00dd">FillMethod</font>]()</div>|
|:---|
|填充模式，有以下几种：<br>  无，<br>  不会应用填充属性；<br>  水平填充模式；<br>  垂直填充模式；<br>  以图片上方中点为起点，360度填充模式。<br>  参见枚举EnumFillMethod|


|<div style="width:1125px">[EnumFillOrigin]() &emsp;[<font color="dd00dd">FillOrigin</font>]()</div>|
|:---|
|填充原点（仅在Horizontal与Vertical填充模式下适用）：<br>  从上方开始填充（水平模式下为左边）；<br>  从下方开始填充（水平模式下为右边）。<br>  参见枚举EnumFillOrigin|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">FillClockwise</font>]()</div>|
|:---|
|顺时针填充（仅在Radial360模式下适用），为true时以上方中点为起点，根据FillAmount比例顺时针渲染，否则为逆时针|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">FillAmount</font>]()</div>|
|:---|
|填充比例（0~1），填充显示的部分占原来大小的比例|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">IsAutoSize</font>]()</div>|
|:---|
|自动大小。为true时，将节点大小调整为图片原本大小|


|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Alpha</font>]()</div>|
|:---|
|透明度（0~1） 为1时不透明|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">EnumFillMethod</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|填充模式|
|**名称**   |**值**  |**描述**|
|NONE   |0   |无，不会应用填充属性|
|Horizontal|1   |水平填充模式|
|Vertical  |2   |垂直填充模式|
|Radial360  |3   |以图片上方中点为起点，360度填充模式。|

|<div style="width:200px">EnumFillOrigin</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|填充原点（仅在Horizontal与Vertical填充模式下适用）|
|**名称**   |**值**  |**描述**|
|Top   |0   |从上方开始填充（水平模式下为左边）|
|Bottom|1   |从下方开始填充（水平模式下为右边）|

------------------------------------------------------------------------------------------
## 函数


------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建ui布局
local root = SandboxNode.new('SceneUIRoot', game.WorkSpace)
root.Name = 'uiroot'
--创建图片
local image1 = SandboxNode.new('SceneUIImage', game.WorkSpace.uiroot)
image1.Name = 'Image'
image1.Visible = true
image1.Icon = 'ui\\mobile\\texture0\\common\\board_activity_box_white.png'
image1.Size = Vector2.new(500, 200)
image1.Position = Vector2.new(0, 0)
image1.FillColor = ColorValue.new(0, 0, 0, 0)
image1.FillMethod = Enum.EnumFillMethod.Horizontal
image1.FillOrigin = Enum.EnumFillOrigin.Top
image1.FillAmount = 0.5
image1.Alpha= 1
image1.IsAutoSize= true
```