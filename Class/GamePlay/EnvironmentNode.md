# EnvironmentNode
------------------------------------------------------------------------------------------
## 描述

环境节点，可以设置天气，星球、重力和时间
继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性：

|<div style="width:1125px">[EnumWeather]() &emsp;[<font color="dd00dd">Weather</font>]()</div>|
|:---|
|设置天气类型的枚举，有晴天、雨天、打雷和自定义。参见枚举`EnvironmentNode::EnumWeather`|

|<div style="width:1125px">[float]() &emsp;[<font color="dd00dd">Gravity</font>]()</div>|
|:---|
|环境重力设置|

|<div style="width:1125px">[Int]() &emsp;[<font color="dd00dd">TimeHour</font>]()</div>|
|:---|
|时间设置|

|<div style="width:1125px">[bool]() &emsp;[<font color="dd00dd">LockTimeHour</font>]()</div>|
|:---|
|是否锁定时间|

|<div style="width:1125px">[EnumSkyPlanet]() &emsp;[<font color="dd00dd">SkyPlanet</font>]()</div>|
|:---|
|设置星球类型的枚举，有地球、萌眼星、烈焰星、火山和自定义。参见枚举`EnvironmentNode::EnumSkyPlanet`|

|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">SkyPlanetRes</font>]()</div>|
|:---|
|设置天空|

------------------------------------------------------------------------------------------
## 枚举：

|<div style="width:200px">**EnumWeather**</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---|:---|:---|
|天气枚举|
|**名称**   |**值**  |**描述**|
|Sunny   |0   |晴天|
|Rain|1   |雨天|
|Thunder  |2   |打雷天|

|<div style="width:200px">**EnumSkyPlanet**</div>|<div style="width:100px"></div>|<div style="width:100px"></div>|
|:---|:---|:---|
|天空包围盒枚举|
|**名称**   |**值**  |**描述**|
|Earth   |0   |地球，默认|
|Twinkle|1   |萌眼星|
|Flame  |2   |烈焰星|
|Volcano  |3   |火山|
|Custom  |4   |自定义|


------------------------------------------------------------------------------------------
## 函数：

|<div style="width:500px">[void]() &emsp;[<font color="dd00dd">LockTime</font> ]() ([int]() timehour)</div>|<div style="width:100px"></div>|<div style="width:45px"></div>|<div style="width:400px"></div>|
|:---|:---|:---|:---|
|锁定时间||||
|**参数名称**|**类别**|**默认**|**描述**|
|timehour|int||时间几点|

------------------------------------------------------------------------------------------
## 事件：

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">WeatherChanged</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|天气改变时触发||
|**返回类型**|**概要**|
|int|天气枚举`EnumWeather`对应的`int`值|


|<div style="width:500px">[SBXSignal\<float\>]() &emsp;[<font color="dd00dd">GravityChanged</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|重力改变时触发||
|**返回类型**|**概要**|
|float|重力值|

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">SkyPlanetChanged</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|天空盒改变时触发||
|**返回类型**|**概要**|
|int|天空包围盒枚举`EnumSkyPlanet`对应的`int`值|

|<div style="width:500px">[SBXSignal\<int\>]() &emsp;[<font color="dd00dd">TimeChanged</font> ]() ()</div>|<div style="width:698px"></div>|
|:---|:---|
|时间改变时触发||
|**返回类型**|**概要**|
|int|24小时制中的某一小时值|

------------------------------------------------------------------------------------------
## 示例代码：

```lua
 local workspace = game:GetService("workspace")
 local environment = workspace.Environment
 --设置天气为下雨
 environment.Weather = Enum.EnumWeather.Rain
 --设置天空为火山
 environment.SkyPlanet = Enum.EnumSkyPlanet.Volcano
 --设置时间为22
 environment.TimeHour = 22
 ```
