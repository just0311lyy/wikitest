# SandboxWorldService
------------------------------------------------------------------------------------------
## 描述

此类是一个服务！它是顶级单例，可以使用`GetService`函数获取。<br>
提供跟`chunk`、`world`交互的功能性接口。

继承：`ServiceNode`

------------------------------------------------------------------------------------------
## 属性：

------------------------------------------------------------------------------------------
## 函数：

|<div style="width:500px">[ReflexTuple]() &emsp;[<font color="dd00dd">GetRangeXZ</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取当前所在`chunk`的首尾 xz 的坐标||
|**返回类型**|**概要**|
|ReflexTuple|元组|

|<div style="width:500px">[ReflexTuple]() &emsp;[<font color="dd00dd">GetRangeXZ</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取当前所在`chunk`的首尾 xz 的坐标||
|**返回类型**|**概要**|
|ReflexTuple|元组|

|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">GetRayBlock</font> ]() ([Vector3]() vector3, [int]() face, [float]() distance)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取射线碰撞到的方块id||||
|**参数名称**|**类别**|**默认**|**描述**|
|vector3|Vector3||射线发射起始点，方块坐标|
|face|int||射线发射方向|
|distance|float||射线途径的距离长度|
|**返回类型**|||**概要**|
|int|||方块id|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsSolidBlock</font> ]() ([Vector3]() vector3)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|判断该位置是否是刚体方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|vector3|Vector3||射线发射起始点，方块坐标|
|**返回类型**|||**概要**|
|bool|||返回true代表此坐标方块为刚体方块|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsLiquidBlock</font> ]() ([Vector3]() vector3)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|判断该位置是否是流体方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|vector3|Vector3||射线发射起始点，方块坐标|
|**返回类型**|||**概要**|
|bool|||返回true代表此坐标方块为流体方块|

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsAirBlock</font> ]() ([Vector3]() vector3)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|判断该位置是否是空气方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|vector3|Vector3||射线发射起始点，方块坐标|
|**返回类型**|||**概要**|
|bool|||返回true代表此坐标方块为空气方块|

|<div style="width:500px">[int]() &emsp;[<font color="dd00dd">GetBlockData</font> ]() ([Vector3]() vector3)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取该位置方块的blockdata数据||||
|**参数名称**|**类别**|**默认**|**描述**|
|vector3|Vector3||射线发射起始点，方块坐标|
|**返回类型**|||**概要**|
|int|||blockdata数据|

|<div style="width:500px">[Vector2]() &emsp;[<font color="dd00dd">GetUIScale</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取UI布局的缩放大小||
|**返回类型**|**概要**|
|Vector2|UI布局的缩放大小|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetBlock</font> ]() ([Vector3]() pos,[int]() blockid,[int]() data,[int]() flags,[bool]() forceupdate)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|放置方块||||
|**参数名称**|**类别**|**默认**|**描述**|
|pos|Vector3||方块世界坐标|
|blockid|int||方块id|
|data|int||方块数据|
|flags|int|3|标识|
|forceupdate|bool|false|强制刷新该位置block|
|pos|Vector3||方块世界坐标|

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">RaycastClosest</font> ]() ([Vector3]() origin, [Vector3]() unitDir, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|射线段检测，返回最近的碰撞物||||
|**参数名称**|**类别**|**默认**|**描述**|
|origin|Vector3||射线段的起点，世界坐标|
|unitDir|Vector3||射线段的世界方向，单位向量|
|distance|float||射线段的最大长度|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|ReflexMap|||最近的碰撞物|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">RaycastAll</font> ]() ([Vector3]() origin, [Vector3]() unitDir, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|射线段检测,返回所有碰撞物,最多128个||||
|**参数名称**|**类别**|**默认**|**描述**|
|origin|Vector3||射线段的起点，世界坐标|
|unitDir|Vector3||射线段的世界方向，单位向量|
|distance|float||射线段的最大长度|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector<ReflexMap>|||所有碰撞物|

|<div style="width:500px">[SandboxNode]() &emsp;[<font color="dd00dd">GetBlockNode</font> ]() ([Vector3]() pos)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|获取方块节点||||
|**参数名称**|**类别**|**默认**|**描述**|
|pos|Vector3||方块世界坐标|
|**返回类型**|||**概要**|
|SandboxNode|||方块节点|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">DropBlockAsItem</font> ]() ([Vector3]() pos, [int]() droptype, [float]() chance, [int]() useToolId)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|方块掉落道具||||
|**参数名称**|**类别**|**默认**|**描述**|
|pos|Vector3||方块世界坐标|
|droptype|int||掉落类型|
|chance|float|1.0f||
|useToolId|int||工具id|

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">SweepBox</font> ]() ([Vector3]() center, [Vector3]() shape, [Vector3]() direction, [Vector3]() angle, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描框||||
|**参数名称**|**类别**|**默认**|**描述**|
|center|Vector3||中心点的世界坐标|
|shape|Vector3||长、宽、高的一半大小|
|direction|Vector3||朝向|
|angle|Vector3||朝向角度|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|ReflexMap|||{isHit  ,normal ,position , distance ,obj}|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">SweepBoxAll</font> ]() ([Vector3]() center, [Vector3]() shape, [Vector3]() direction, [Vector3]() angle, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描框全部||||
|**参数名称**|**类别**|**默认**|**描述**|
|center|Vector3||中心点的世界坐标|
|shape|Vector3||长、宽、高的一半大小|
|direction|Vector3||朝向|
|angle|Vector3||朝向角度|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">SweepCapsule</font> ]() ([float]() radius, [Vector3]() p0, [Vector3]() p1, [Vector3]() dir, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描胶囊||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|p0|Vector3||胶囊体上面的球体的中心点|
|p1|Vector3||胶囊体下面的球体的中心点|
|dir|Vector3||朝向|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|ReflexMap|||{isHit  ,normal ,position , distance ,obj}|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">SweepCapsuleAll</font> ]() ([float]() radius, [Vector3]() p0, [Vector3]() p1, [Vector3]() dir, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描胶囊全部||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|p0|Vector3||胶囊体上面的球体的中心点|
|p1|Vector3||胶囊体下面的球体的中心点|
|dir|Vector3||朝向|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[ReflexMap]() &emsp;[<font color="dd00dd">SweepSphere</font> ]() ([float]() radius, [Vector3]() center, [Vector3]() direction, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描球体||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|center|Vector3||中心点的世界坐标|
|direction|Vector3||朝向|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|ReflexMap|||{isHit  ,normal ,position , distance ,obj}|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">SweepCapsuleAll</font> ]() ([float]() radius, [Vector3]() center, [Vector3]() direction, [float]() distance, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|扫描球全部||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|center|Vector3||中心点的世界坐标|
|direction|Vector3||朝向|
|distance|float||检测距离|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">OverlapBox</font> ]() ([Vector3]() shape, [Vector3]() pos, [Vector3]() angle, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|重叠框||||
|**参数名称**|**类别**|**默认**|**描述**|
|shape|Vector3||长、宽、高的一半大小|
|pos|Vector3||中心点的世界坐标|
|angle|Vector3||朝向角度|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">OverlapCapsule</font> ]() ([float]() radius, [Vector3]() p0, [Vector3]() p1, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|重叠胶囊||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|p0|Vector3||胶囊体的上面球心的中心点|
|p1|Vector3||胶囊体的下面球心的中心点|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[vector\<ReflexMap\>]() &emsp;[<font color="dd00dd">OverlapSphere</font> ]() ([float]() radius, [Vector3]() pos, [bool]() isIgnoreTrigger, [vector\<int\>]() filterGroup)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|重叠球体||||
|**参数名称**|**类别**|**默认**|**描述**|
|radius|float||半径|
|pos|Vector3||世界坐标|
|isIgnoreTrigger|bool||是否忽略trigger类型|
|filterGroup|vector\<int\>||过滤组，{1，2，3} 含有的数字组会被查询|
|**返回类型**|||**概要**|
|vector\<ReflexMap\>|||{isHit  ,normal ,position , distance ,obj}数组|

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">SetMainFrameShow</font> ]() ([bool]() isShow)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|锁定时间||||
|**参数名称**|**类别**|**默认**|**描述**|
|isShow|bool||为true，表示显示游戏内置UI|

|<div style="width:500px">[Vector2]() &emsp;[<font color="dd00dd">GetUISize</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|获取UI布局的尺寸||
|**返回类型**|**概要**|
|Vector2|布局的尺寸|


------------------------------------------------------------------------------------------
## 示例代码：
```lua
local worldService = game:GetService('WorldService')
local ret = worldService:IsAirBlock(Vector3.new(500, 700, 800))
print("the pos block is airBlock = ", ret)
```