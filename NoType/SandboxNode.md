# SandboxNode
------------------------------------------------------------------------------------------
## 描述

沙盒节点，沙盒结构场景树基础节点。

------------------------------------------------------------------------------------------
## 属性


|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">ClassType</font>]()</div>|
|:---|
|节点的ClassType名称。（不可写）|


|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">Name</font>]()</div>|
|:---|
|节点名字|


|<div style="width:1125px">[SandboxNode]() &emsp;[<font color="dd00dd">Parent</font>]()</div>|
|:---|
|父节点 （同AutoRef<SandboxNode> parent，小写仅脚本可调用）|


|<div style="width:1125px">[vector/<SandboxNode/>]() &emsp;[<font color="dd00dd">Children</font>]()</div>|
|:---|
|全部子节点。（仅脚本可调用）|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Enabled</font>]()</div>|
|:---|
|节点是否被禁用。被禁用后节点内逻辑，事件，通知等不生效。|


|<div style="width:1125px">[AttributeContainer]() &emsp;[<font color="dd00dd">Attibutes</font>]()</div>|
|:---|
|获取属性容器。（仅脚本可调用）|


|<div style="width:1125px">[int]() &emsp;[<font color="dd00dd">flag</font>]()</div>|
|:---|
|同步标识符（仅同步可用）`unsigned int`|


|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">Syncable</font>]()</div>|
|:---|
|是否可同步|

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">Clone</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|节点克隆，克隆反射属性，自定义属性，以及包含的子对象；||
|**返回类型**|**概要**|
|SandboxNode|克隆的节点|

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">FindFirstChild</font> ]() ([string]() name)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|通过节点名找到节点对象；||||
|**参数名称**|**类别**|**默认**|**描述**|
|name|string||节点名|
|**返回类型**|||**概要**|
|SandboxNode|||节点对象|


|<div style="width:1125px">[void]() &emsp;[<font color="dd00dd">Destroy</font>]()</div>|
|:---|
|销毁节点|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetParent</font> ]() ([SandboxNode]() parent)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|锁定时间||||
|**参数名称**|**类别**|**默认**|**描述**|
|parent|SandboxNode||父节点|


|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">GetNodeid</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取节点id||
|**返回类型**|**概要**|
|int|节点id,`SandboxNodeID`|


|<div style="width:500px">[ReflexVariant]() &emsp;[<font color="dd00dd">GetAttribute</font> ]() ([string]() attr)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取`key`为`attr`的反射属性||||
|**参数名称**|**类别**|**默认**|**描述**|
|attr|string||属性`key`字符串|
|**返回类型**|||**概要**|
|ReflexVariant|||反射属性|


|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">SetAttribute</font> ]() ([string]() attr, [ReflexVariant]() value)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|设置反射的属性值||||
|**参数名称**|**类别**|**默认**|**描述**|
|attr|string||属性`key`字符串|
|value|ReflexVariant||反射属性|
|**返回类型**|||**概要**|
|bool|||返回`true`，`key`为`attr`，对应`value`为`ReflexVariant`的反射属性值设置成功|


|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">AddAttribute</font> ]() ([string]() attr, [TYPE]() type)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|添加反射属性||||
|**参数名称**|**类别**|**默认**|**描述**|
|attr|string||属性`key`字符串|
|type|TYPE||属性`key`对应的属性值类型,参见枚举`Attribute::TYPE`|
|**返回类型**|||**概要**|
|bool|||返回`true`，新增一条值类型为`type`的反射属性成功|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">DeleteAttribute</font> ]() ([string]() attr)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|删除一条反射属性||||
|**参数名称**|**类别**|**默认**|**描述**|
|attr|string||反射属性key字符串|


|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsA</font> ]() ([string]() value)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|判断节点的`ClassType`是不是属于`value`代表的`ClassType`||||
|**参数名称**|**类别**|**默认**|**描述**|
|value|string||`ClassType`字符串|
|**返回类型**|||**概要**|
|bool|||返回`true`，表示节点`ClassType`属于`value`代表的`ClassType`|


------------------------------------------------------------------------------------------
## 事件

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyAncestryChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|祖先节点变化，父级或任一祖先节点变化||||
|**返回类型**|||**概要**|
|SBXSignal|||祖先节点变化时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||发生祖先节点变化的节点|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyParentChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|父节点变化，父级节点变化||||
|**返回类型**|||**概要**|
|SBXSignal|||父节点变化时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||变化后的父级节点|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyChildAdded</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|新增子节点触发该事件||||
|**返回类型**|||**概要**|
|SBXSignal|||新增子节点时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||新增加的字节点|


|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyChildRemoved</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|移除子节点触发该事件||||
|**返回类型**|||**概要**|
|SBXSignal|||移除子节点时触发，事件参数为（`SandboxNode node`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|node|SandboxNode||移除的子节点|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyAttributeChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|属性发生变化后触发该事件||||
|**返回类型**|||**概要**|
|SBXSignal|||属性发生变化时触发，事件参数为（`string attr`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|attrName|string||发生变化的属性名称|

|<div style="width:500px">[SBXSignal\<SandboxNode\>]() &emsp;[<font color="dd00dd">NotifyCustomAttrChanged</font> ]() ()</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|自定义属性发生变化||||
|**返回类型**|||**概要**|
|SBXSignal|||自定义属性发生变化时触发，事件参数为（`string cusAttrName`）|
|**SBXSignal参数名称**|**类别**|**默认**|**描述**|
|cusAttrName|string||发生变化的自定义属性名称|


------------------------------------------------------------------------------------------
## 示例代码

```lua
--SandboxNode node 有一个自定义属性 bool类型 名字是test_k
local v = node:GetAttribute("test_k")
```