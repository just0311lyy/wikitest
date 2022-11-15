# SceneUIComponent
------------------------------------------------------------------------------------------
## 描述

`UI`约束和布局类别的基类，由`SceneUIBase`继承而来
继承：`SceneUIBase`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">Size</font>]()</div>|
|:---|
|UI节点像素和尺寸大小 (`Rainbow::Vector2f`)|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">Scale</font>]()</div>|
|:---|
|UI节点缩放倍数|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Rotation</font>]()</div>|
|:---|
|UI节点旋转度数|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">Position</font>]()</div>|
|:---|
|UI节点坐标|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">Pivot</font>]()</div>|
|:---|
|UI节点锚点（0~1），（0.5,0.5）为中点|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">IsKeepPosWhenPivotChange</font>]()</div>|
|:---|
|更新锚点时是否保持位置不变|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">IsNotifyEventStop</font>]()</div>|
|:---|
|是否将触摸事件传递给父节点（为true时不传递）|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">LineColor</font>]()</div>|
|:---|
|UI节点边线颜色设置 (Rainbow::ColorQuad)|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">FillColor</font>]()</div>|
|:---|
|UI节点填充颜色设置|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">LineSize</font>]()</div>|
|:---|
|UI节点边线像素和尺寸大小|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">ClickPass</font>]()</div>|
|:---|
|UI节点边线像素和尺寸大小|

|<div style="width:1125px">[EnumLayoutHRelation]() &emsp;[<font color="dd00dd">LayoutHRelation</font>]()</div>|
|:---|
|水平关联方式，包括左关联、中线关联和右关联。设置后，当父节点（若父节点为`UIRoot`则为屏幕）变化时，UI与关联位置的相对距离将保持不变。<br>参见枚举`EnumLayoutHRelation`|

|<div style="width:1125px">[EnumLayoutVRelation]() &emsp;[<font color="dd00dd">LayoutVRelation</font>]()</div>|
|:---|
|垂直关联方式，包括上关联、中线关联和下关联。设置后，当父节点（若父节点为`UIRoot`则为屏幕）变化时，UI与关联位置的相对距离将保持不变。<br>参见枚举`EnumLayoutVRelation`|

|<div style="width:1125px">[EnumLayoutSizeRelation]() &emsp;[<font color="dd00dd">LayoutSizeRelation</font>]()</div>|
|:---|
|宽高关联，包括无关联，宽关联，高关联和全关联，当父节点宽高改变时，UI宽高随之变化。<br>参见枚举`EnumLayoutSizeRelation`|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">EnumLayoutHRelation</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|水平关联枚举|
|**名称**   |**值**  |**描述**|
|Left   |0   |左关联，保持与父节点（屏幕）左侧的相对位置|
|Middle|1   |中线关联，保持与父节点（屏幕）中线的相对位置|
|Right  |2   |右关联，保持与父节点（屏幕）右侧的相对位置|

|<div style="width:200px">EnumLayoutVRelation</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|垂直关联枚举|
|**名称**   |**值**  |**描述**|
|Top   |0   |上关联，保持与父节点（屏幕）顶部的相对位置|
|Middle|1   |中线关联，保持与父节点（屏幕）中线的相对位置|
|Bottom  |2   |下关联，保持与父节点（屏幕）底部的相对位置|


|<div style="width:200px">EnumLayoutSizeRelation</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|尺寸布局关联枚举|
|**名称**   |**值**  |**描述**|
|None   |0   |无关联|
|Height|1   |高关联|
|Width  |2   |宽关联|
|Both  |3   |宽高关联|

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[Vector2f]() &emsp;[<font color="dd00dd">GetGlobalPos</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取UI的全局位置||
|**返回类型**|**概要**|
|Vector2f|ui的2D坐标（`Rainbow::Vector2f`）|

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">RollOver</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|拖住滑动或鼠标滚轮结束||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isOver|bool||是否正拖住鼠标或者鼠标滚轮结束|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|


|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">RollOut</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|拖住滑动或鼠标滚轮超出UI布局范围||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isOut|bool||是否拖住滑动或鼠标滚轮超出UI布局范围|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|

|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">TouchBegin</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|触摸事件开始||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isTouchBegin|bool||是否触摸事件开始|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|

|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">TouchMove</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|触摸移动||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isTouchMove|bool||是否触摸移动|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|

|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">TouchEnd</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|触摸事件结束||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isTouchEnd|bool||是否触摸事件结束|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|


|<div style="width:500px">[SBXSignal\<SandboxNode, bool, Vector2\>]() &emsp;[<font color="dd00dd">Click</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|点击事件||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`SandboxNode node, bool, Vector2`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||当前`ui`节点组件|
|isClick|bool||是否点击事件|
|vector2|Vector2||当前鼠标的二维坐标(`Rainbow::Vector2f`)|

------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建ui布局
local root = SandboxNode.new('SceneUIRoot', game.WorkSpace)
root.Name = 'uiroot'
--创建图片
local image1 = SandboxNode.new('SceneUIImage', game.WorkSpace.uiroot)
image1.Name = 'image'
image1.Visible = true
image1.Icon = 'ui\\mobile\\texture0\\common\\board_activity_box_white.png'
image1.Size = Vector2.new(500, 200)
image1.Pivot= Vector2.new(0, 0)
image1.LayoutHRelation = Enum.EnumLayoutHRelation.Left
image1.LayoutVRelation= Enum.EnumLayoutVRelation.Top
image1.LayoutSizeRelation= Enum.EnumLayoutSizeRelation.Both

image1.RollOver:connect(function(node,issuccess,mousepos) 
    print('you RollOver me')
    print('RollOver pos:'..mousepos.x..' '..mousepos.y)
end)
image1.RollOut:connect(function(node,issuccess,mousepos) 
    print('you RollOut me')
    print('RollOut pos:'..mousepos.x..' '..mousepos.y)
end)
image1.TouchBegin:connect(function(node,issuccess,mousepos) 
    print('you TouchBegin me')
    print('TouchBegin pos:'..mousepos.x..' '..mousepos.y)
end)
image1.TouchMove:connect(function(node,issuccess,mousepos) 
    print('you TouchMove me')
    print('TouchMove pos:'..mousepos.x..' '..mousepos.y)
end)
image1.TouchEnd:connect(function(node,issuccess,mousepos) 
    print('you TouchEnd me')
    print('TouchEnd pos:'..mousepos.x..' '..mousepos.y)
end)
image1.Click:connect(function(node,issuccess,mousepos) 
    print('you Clickme')
    print('Clickme pos:'..mousepos.x..' '..mousepos.y)
end)
```