# EnumDefaultEffect

枚举所属类：`SandboxDefaultEffect` 

------------------------------------------------------------------------------------------
## 描述

特效效果类型,有烟雾、爆炸、光效、粒子、火焰、环境和提示

------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px"></div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
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
## 代码示例

```lua
SandboxDefaultSound::EnumDefaultEffect
local workspace = game:GetService("workspace")
local Effect = SandboxNode.new('SandboxDefaultEffect', workspace)
--设置特效位置
Effect.Position = Vector3.new(unpack({1000，1000，1000}))
--设置特效为火焰类型
Effect.EffectType = Enum.EnumDefaultEffect.Fire
--设置特效序列
Effect.EffectIndex = 13
--设置特效时长
Effect.MaxTime = 10
--设置特效可见距离
Effect.VisibleDistance = 100
```