# SandboxDefaultEffect
------------------------------------------------------------------------------------------
## 描述

特效节点，可以用于播放一个特效
继承：`SceneTransObject`

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[EnumDefaultEffect]() &emsp;[<font color="dd00dd">EffectType</font>]()</div>|
|:---|
|特效效果类型,有烟雾、爆炸、光效、粒子、火焰、环境和提示。见枚举`SandboxDefaultEffect::EnumDefaultEffect`|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">EffectIndex</font>]()</div>|
|:---|
|特效效果序列|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Scale</font>]()</div>|
|:---|
|效果大小, 整体缩放比例|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Visible</font>]()</div>|
|:---|
|是否显示视觉效果|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">MaxTime</font>]()</div>|
|:---|
|效果最大存在时间|

|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">VisibleDistance</font>]()</div>|
|:---|
|效果最大可见距离|

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px">EnumDefaultEffect</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|特效效果类型,有烟雾、爆炸、光效、粒子、火焰、环境和提示|
|**名称**   |**值**  |**描述**|
|NONE   |0   |无|
|SMOKE|1   |烟雾|
|EXPOSION  |2   |爆炸|
|LIGHT  |3   |光效|
|PARTICLE  |4   |粒子|
|FIRE  |5   |火焰|
|ENVIRONMENT  |6   |环境|
|HINT  |7   |提示|

------------------------------------------------------------------------------------------
## 函数

------------------------------------------------------------------------------------------
## 示例代码

```lua
local workspace = game:GetService("workspace")
local Effect = SandboxNode.new('SandboxDefaultEffect', workspace)
local pos2 = Vector3.new(unpack({1000,1000,1000}))
--设置特效位置
Effect.Position = pos2
--设置特效为火焰类型
Effect.EffectType = Enum.EnumDefaultEffect.Fire
--设置特效序列
Effect.EffectIndex = 13
--设置特效时长
Effect.MaxTime = 10
--设置特效可见距离
Effect.VisibleDistance = 100
 ```