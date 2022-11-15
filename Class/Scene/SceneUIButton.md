# SceneUIButton
------------------------------------------------------------------------------------------
## 描述

继承：`SceneUIComponent`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Icon</font>]()</div>|
|:---|
|按钮资源路径|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Title</font>]()</div>|
|:---|
|按钮标题|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">TitleSize</font>]()</div>|
|:---|
|按钮标题文本字体大小|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">DownEffectValue</font>]()</div>|
|:---|
|按钮按下效果变化值|

|<div style="width:1125px">[DownEffect]() &emsp;[<font color="dd00dd">DownEffect</font>]()</div>|
|:---|
|按钮按下效果，有缩放，颜色变化。参见枚举`DownEffect` (`SceneUIButton::ButtonDownEffect`)|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Alpha</font>]()</div>|
|:---|
|透明度（0~1） 为1时不透明|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">OutlineEnable</font>]()</div>|
|:---|
|开启字体描边|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">OutlineColor</font>]()</div>|
|:---|
|字体描边颜色  (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">OutlineSize</font>]()</div>|
|:---|
|字体描边宽度|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">ShadowEnable</font>]()</div>|
|:---|
|开启字体阴影|

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">ShadowColor</font>]()</div>|
|:---|
|字体阴影颜色  (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[Vector2]() &emsp;[<font color="dd00dd">ShadowOffect</font>]()</div>|
|:---|
|字体阴影偏移 (`Rainbow::Vector2f`)|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">IsAutoSize</font>]()</div>|
|:---|
|自动大小。为`true`时，将节点大小调整为图片原本大小|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">DownEffect</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|按钮按下效果，有缩放，颜色变化|
|**名称**   |**值**  |**描述**|
|NoEffect   |0   |无效果|
|ColorEffect|1   |颜色变化效果|
|ScaledEffect  |2   |缩放效果|

------------------------------------------------------------------------------------------
## 函数


------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建ui布局
local root = SandboxNode.new('SceneUIRoot', game.WorkSpace)
root.Name = 'uiroot'
--创建按钮
local button= SandboxNode.new('SceneUIButton', game.WorkSpace.uiroot)
button.Icon = 'ui\\mobile\\texture0\\common\\board_activity_box_white.png'
button.Title = "Button"
button.TitleSize = 36
button.DownEffect = Enum.DownEffect.ScaledEffect
button.Size = Vector2.new(100, 50)
button.Position = Vector2.new(200, 100)
button.Alpha= 1
--设置开启描边
button.OutlineEnable= true
--设置开启阴影
button.ShadowEnable= true
```