# InputObject 
------------------------------------------------------------------------------------------
## 描述

在用户输入事件触发时，描述具体的输入信息的对象，例如鼠标位置，按键信息等

------------------------------------------------------------------------------------------
## 属性

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Delta</font>]()</div>|
|:---|
|暂无信息|

|<div style="width:1125px">[Vector3]() &emsp;[<font color="dd00dd">Position</font>]()</div>|
|:---|
|鼠标相关的事件中，描述鼠标的位置|


|<div style="width:1125px">[Int]() &emsp;[<font color="dd00dd">KeyCode</font>]()</div>|
|:---|
|按键事件触发时，对应的按键码，等于`Enum.KeyCode`中的某个值|

|<div style="width:1125px">[Int]() &emsp;[<font color="dd00dd">UserInputState</font>]()</div>|
|:---|
|描述输入状态（开始，结束等）等于枚举`UserInputState`中的某个值|

|<div style="width:1125px">[Int]() &emsp;[<font color="dd00dd">UserInputType</font>]()</div>|
|:---|
|描述输入的类型 等于枚举`UserInputType`中的某个值|

------------------------------------------------------------------------------------------
## 函数

|<div style="width:500px">[bool]() &emsp;[<font color="dd00dd">IsModifierKeyDown</font> ]() ([int]() vkey)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|按键是否按下||||
|**参数名称**|**类别**|**默认**|**描述**|
|vkey|int||按键值|
|**返回类型**|||**概要**|
|bool|||是否按下|


