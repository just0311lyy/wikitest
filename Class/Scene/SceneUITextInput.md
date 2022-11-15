# SceneUITextInput
------------------------------------------------------------------------------------------
## 描述

输入框组件
继承：`SceneUIComponent`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[ColorValue]() &emsp;[<font color="dd00dd">TitleColor</font>]()</div>|
|:---|
|字体颜色 (`Rainbow::ColorQuad`)|

|<div style="width:1125px">[TextVAlignment]() &emsp;[<font color="dd00dd">TextVAlignment</font>]()</div>|
|:---|
|上下对齐，有向上、中间和向下对齐。参见枚举`cocos2d::TextVAlignment`|

|<div style="width:1125px">[TextHAlignment]() &emsp;[<font color="dd00dd">TextHAlignment</font>]()</div>|
|:---|
|左右对齐，有向左、中间和向右对齐。参见枚举`cocos2d::TextHAlignment`|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">MaxLength</font>]()</div>|
|:---|
|限制输入文本长度|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">FontSize</font>]()</div>|
|:---|
|字体大小|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Title</font>]()</div>|
|:---|
|输入文本内容|

|<div style="width:1125px">[InputMode]() &emsp;[<font color="dd00dd">InputMode</font>]()</div>|
|:---|
|输入模式，有单行输入和多行输入，参见枚举`cocos2d::ui::EditBox::InputMode`|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">InputMode</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|行为状态枚举|
|**名称**   |**值**  |**描述**|
|Multiline   |0   |无|
|Singleline|1   |跳|

------------------------------------------------------------------------------------------
## 函数

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<bool\>]() &emsp;[<font color="dd00dd">Return</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|输入完成触发||||
|**返回类型**|||**概要**|
|SBXSignal|||进入节点时触发，事件参数为（`bool isReturn`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isReturn|bool||返回true，输入完成|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local workspace = game:GetService("workspace")
local root= SandboxNode.new('SceneUIRoot', workspace)
local petNameText = SandboxNode.new('SceneUITextInput', root)
--设置节点名字
petNameText.Name = "PetNameText"
--设置节点大小
petNameText.Size = Vector2.new(120, 50)
--设置节点位置
petNameText.Position = Vector2.new(400, 250)
--设置是否可见
petNameText.Visible = true
--设置输入框背景颜色
petNameText.FillColor = ColorValue.new(97, 151, 230, 255)
--设置文本上下对齐
petNameText.TextVAlignment = Enum.TextVAlignment.Center
--设置文本左右对齐
petNameText.TextHAlignment = Enum.TextHAlignment.Center
--设置输入内容
petNameText.Title = "宠物狼"
--设置输入文本最长长度
petNameText.MaxLength = 20
--设置输入文本字体大小
petNameText.FontSize = 25
--设置输入模式为单行
petNameText.InputMode = Enum.InputMode.Singleline
```