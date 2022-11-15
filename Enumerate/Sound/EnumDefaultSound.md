# EnumDefaultSound

枚举所属类：`SandboxDefaultSound`

------------------------------------------------------------------------------------------
## 描述:

默认声音类型枚举：
- 脚步
- 行为
- 受击
- 待机
- 技能
- 环境
- 背景音乐
- 提示
- 其他


------------------------------------------------------------------------------------------
## 枚举

|<div style="width:200px"></div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---   |:---|:---|
|**名称**   |**值**  |**描述**|
|NONE   |0   |无|
|FOOTSTEP|1   |脚步|
|BEHIVIOR  |2   |行为|
|BEHIT  |3   |受击|
|IDLE  |4   |待机|
|SKILL  |5   |技能|
|ENVIRONMENT  |6   |环境|
|BACKGROUND  |7   |背景音乐|
|HINT  |8   |提示|
|OTHER  |9   |其他|


------------------------------------------------------------------------------------------
## 代码示例

```lua
SandboxDefaultSound::EnumDefaultSound
local workspace = game:GetService("workspace")
local Effect = SandboxNode.new('SandboxDefaultSound', workspace)
--默认音效枚举结合音效序列一起使用
Effect.EffectType = Enum.EnumDefaultSound.FOOTSTEP --设置音效为脚步
Effect.EffectIndex = 13 --设置音效序列
Effect:PlaySound() --播放音效
```