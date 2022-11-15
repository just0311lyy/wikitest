# Quaternion
------------------------------------------------------------------------------------------
## 描述

四元数

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[Quaternion]() &emsp;[<font color="dd00dd">LookAt</font> ]() ([Vector3]() va, [Vector3]() vb)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|||||
|**参数名称**|**类别**|**默认**|**描述**|
|va|Vector3|||
|vb|Vector3|||
|**返回类型**|||**概要**|
|Quaternion|||四元数|


|<div style="width:500px">[Quaternion]() &emsp;[<font color="dd00dd">FromEuler</font> ]() ([float]() p1, [float]() p2, [float]() p3)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|返回一个四元数，通过传入三个角度p1,p2,p3||||
|**参数名称**|**类别**|**默认**|**描述**|
|p1|float||角度|
|p2|float||角度|
|p3|float||角度|
|**返回类型**|||**概要**|
|Quaternion|||四元数|


|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">RotateAxisAngle</font> ]() ([Vector3]() dir, [float]() angle)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|通过传入的朝向和角度来旋转||||
|**参数名称**|**类别**|**默认**|**描述**|
|dir|Vector3||朝向|
|angle|float||角度|

Vector3  RotateToDir(Vector3 dir)
返回一个Vector3, 传入一个dir做旋转

|<div style="width:500px">[Vector3]() &emsp;[<font color="dd00dd">RotateToDir</font> ]() ([Vector3]() dir)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|返回一个`Vector3`, 传入一个`dir`做旋转||||
|**参数名称**|**类别**|**默认**|**描述**|
|dir|Vector3||朝向|
|**返回类型**|||**概要**|
|Vector3||||


|<div style="width:500px">[Quaternion]() &emsp;[<font color="dd00dd">Lerp</font> ]() ([Quaternion]() va, [Quaternion]() vb)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|返回一个四元数，传入va和vb，线性运算||||
|**参数名称**|**类别**|**默认**|**描述**|
|va|Quaternion||四元数|
|vb|Quaternion||四元数|
|**返回类型**|||**概要**|
|Quaternion|||四元数|

------------------------------------------------------------------------------------------
## 示例代码

```lua
local q1 = Quaternion.new(0,0,2,1)
local q2 = Quaternion.new(0,0,5,1)
local alpha = 0.8
local q3 = q1:Lerp(q2, alpha)

print("q3:"..tostring(q3))
--q3:userdata: 41E1E338
local angle = 20
local dir = Vector3.new(0,0,1)
q1:RotateAxisAngle(dir, angle)

local lookDirV3 = q1:LookDir()
print("lookDirV3 x:"..tostring(lookDirV3.x).." y:"..tostring(lookDirV3.y).." z:"..tostring(lookDirV3.z))
--lookDirV3 x:0 y:0 z:1

local v3 = q1:RotateToDir(dir)
print("v3 x:"..tostring(v3.x).." y:"..tostring(v3.y).." z:"..tostring(v3.z))
--v3 x:0 y:0 z:1

local va = Vector3.new(0,0,1)
local vb = Vector3.new(0,0,2)
local q4 = Quaternion.LookAt(va, vb)
print("q4:"..tostring(q4))
--q4:userdata: 41E25D98
local q5 = Quaternion.FromEuler(1.0,2.0,3.0)
print("q5:"..tostring(q5))
--q5:userdata: 41E26688
local q6 = Quaternion.FromAxisAngle(Vector3.new(0,0,1), angle);
print("q6:"..tostring(q6))
--q6:userdata: 41E2D068
```