# SandboxClickDetectorObject
------------------------------------------------------------------------------------------
## 描述

运行脚本接收3D对象上的指针输入，可以检测基本的鼠标事件：进入、离开、左键单击和右键单击。
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性

------------------------------------------------------------------------------------------
## 函数

------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">MouseClick</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标左键单击||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标左键单击时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标左键单击是否触发|


|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">RightMouseClick</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标右键单击||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标右键单击时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标右键单击是否触发|

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">MouseHoverEnter</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标停在节点上||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标停在节点上时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标停在节点上是否触发|

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">MouseHoverLeave</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标在节点上离开||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标在节点上离开时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标在节点上离开是否触发|


|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">MouseDown</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标按下触发||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标按下触发时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标按下触发是否触发|


|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">MouseUp</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|鼠标弹起触发||||
|**返回类型**|||**概要**|
|SBXSignal|||鼠标弹起触发时触发，事件参数为（`int isAction`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|isAction|int||鼠标弹起触发是否触发|


------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建模型
local model = SandboxNode.new('SceneModelObject', game.WorkSpace)
model.ModelId = string.format("sandboxAsset://entity/%s/body.omod","100041")
model.Position = Vector3.new(500, 700, 150)
--绑定点击点
local clickDetector = sandboxNode.new('SandboxClickDetectorObject', model)
--监听MouseClick事件
clickDetector.MouseClick:connect(function() 
    print("You clicked me!")
end)
```