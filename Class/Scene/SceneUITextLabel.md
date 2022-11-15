# SceneUITextLabel
------------------------------------------------------------------------------------------
## 描述

一个`text`文本组件
继承：`SceneUIComponent` 

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">TitleColor</font>]()</div>|
|:---|
|字体颜色  (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[TextVAlignment]() &emsp;[<font color="dd00dd">TextVAlignment</font>]()</div>|
|:---|
|上下对齐，有向上、中间和向下对齐。参见枚举`cocos2d::TextVAlignment`|

|<div style="width:1125px">[TextHAlignment]() &emsp;[<font color="dd00dd">TextHAlignment</font>]()</div>|
|:---|
|左右对齐，有向左、中间和向右对齐。参见枚举`cocos2d::TextHAlignment`|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">FontSize</font>]()</div>|
|:---|
|字体大小|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Title</font>]()</div>|
|:---|
|文本内容|

|<div style="width:1125px">[AutoSizeType]() &emsp;[<font color="dd00dd">IsAutoSize</font>]()</div>|
|:---|
|自动调整节点大小为字体大小。参见枚举`fairygui::AutoSizeType`|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">OutlineEnable</font>]()</div>|
|:---|
|开启描边|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">OutlineColor</font>]()</div>|
|:---|
|描边颜色 (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">OutlineSize</font>]()</div>|
|:---|
|描边宽度|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">ShadowEnable</font>]()</div>|
|:---|
|开启阴影|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">ShadowColor</font>]()</div>|
|:---|
|阴影颜色|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">ShadowOffect</font>]()</div>|
|:---|
|阴影偏移  (`Rainbow::Vector2f`)|

------------------------------------------------------------------------------------------
## 枚举：

|<div style="width:200px">TextVAlignment</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|文字水平对齐|
|**名称**   |**值**  |**描述**|
|Top   |0   |文字居上|
|Center|1   |文字居中|
|Bottom  |2   |文字居下|


|<div style="width:200px">TextHAlignment</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|文字垂直对齐|
|**名称**   |**值**  |**描述**|
|Right   |0   |文字居右|
|Center|1   |文字居中|
|Left  |2   |文字居左|

|<div style="width:200px">AutoSizeType</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|根据字体大小调节节点大小枚举|
|**名称**   |**值**  |**描述**|
|NONE   |0   |不调整|
|BOTH|1   |宽高|
|HEIGHT  |2   |高|
|SHRINK  |3   |宽|


------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[Vector2]() &emsp;[<font color="dd00dd">GetTextSize</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取字体大小||
|**返回类型**|**概要**|
|Vector2|返回`text`尺寸|

------------------------------------------------------------------------------------------
## 示例代码：

```lua
local workspace = game:GetService("Workspace")
local root = SandboxNode.new('SceneUIRoot', workspace)
local name = SandboxNode.new('SceneUITextLabel', root)
name.Title = "商店"
--设置背景框
name.LineColor = ColorValue.new(0, 0, 0, 0)
--设置背景颜色
name.FillColor = ColorValue.new(0, 0, 0, 0)
--设置字体颜色
name.TitleColor = ColorValue.new(255, 0, 0, 255)
--设置位置
name.Position = Vector2.new(75,50)
--设置字体大小
name.FontSize = 18
--设置上下居中对齐
name.TextVAlignment = Enum.TextVAlignment.Center
--设置左右向左对齐
name.TextHAlignment = Enum.TextHAlignment.Left

--设置自动调整大小
name.IsAutoSize= true

--设置开启描边
name.OutlineEnable= true
--设置开启阴影
name.ShadowEnable= true
--获取字体大小
local size = name:GetTextSize()
```