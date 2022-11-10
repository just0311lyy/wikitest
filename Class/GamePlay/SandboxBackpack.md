# SandboxBackpack

------------------------------------------------------------------------------------------
## 描述：

存放`ScenePlayerObject`物品栏的容器对象。玩家`Backpack`中的所有`SandboxTool`都会显示在他们屏幕下方的物品栏中。从物品栏中选择`SandboxTool`会装备`SandboxTool`，将其从`Backpack`中转移到玩家角色上。

继承：`SandboxNode` 

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">CoreUiEnabled</font>]()</div>|
|:---|
|是否显示默认的快捷栏`UI`，默认值为`false`|

------------------------------------------------------------------------------------------
## 函数：

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetTool</font> ]() ([int]() index)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取某个键位对应的tool，index从1开始||||
|**参数名称**|**类别**|**默认**|**描述**|
|index|int||按键1~8|
|**返回类型**|||**概要**|
|SandboxNode|||道具节点|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetTool</font> ]() ([int]() index, [SandboxNode]() tool)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置`tool`到具体的快捷键位置||||
|**参数名称**|**类别**|**默认**|**描述**|
|index|int||按键1~8|
|tool|SandboxNode||道具`tool`|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">RemoveTool</font> ]() ([int]() index)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移除tool||||
|**参数名称**|**类别**|**默认**|**描述**|
|index|int||按键1~8|

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">GetCurEquipedTool</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取当前装备的`tool`||
|**返回类型**|**概要**|
|SandboxNode|当前装备的`tool`|

