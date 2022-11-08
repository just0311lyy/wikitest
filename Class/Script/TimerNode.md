
# TimerNode
------------------------------------------------------------------------------------------
## 描述

TimerNode 定时器节点允许指定一个lua 回调方法在一定时间后执行。

------------------------------------------------------------------------------------------
## 属性

|\<LuaFunction\> Callback|
|:---|
|lua回调方法|

|double Delay|
|:---|
|首次延迟执行的事件|

|bool Loop|
|:---|
|是否循环执行|

|double Interval|
|:---|
|循环执行间隔|

------------------------------------------------------------------------------------------
## 枚举：

### TimerRunState
|TimerRunState|||
|:---|:---|:---|
|运行状态枚举|||
|名称|值|描述|
|IDLE|0|空闲|
|RUNNING|1|运行中|
|PAUSE|2|暂停|

<table>
	<tr>
		<td colspan="3">TimerRunState</td>
	</tr>
	<tr>
		<td colspan="3">运行状态枚举</td>
	</tr>
	<tr>
		<td>名称</td>
		<td>值</td>
		<td>描述</td>
	</tr>
	<tr>
		<td>IDLE</td>
		<td>0</td>
		<td>空闲</td>
	</tr>
	<tr>
		<td>RUNNING</td>
		<td>1</td>
		<td>运行中</td>
	</tr>
	<tr>
		<td>PAUSE</td>
		<td>2</td>
		<td>暂停</td>
	</tr>
</table>

------------------------------------------------------------------------------------------
## 函数

|void Start()|
|:---|
|开始执行。需要先设置参数|

|void Pause()|
|:---|
|暂停。需要在开始执行后调用|

|void Resume()|
|:---|
|恢复。需要在暂停后调用|

|void Stop()|
|:---|
|停止。需要在执行后调用|

|void StartEx( double delay, bool loop, double interval, AutoRef<LuaFunction> cb )||||
|:---|:---|:---|:---|
|开始执行。附带初始化的参数此服务器中可以容纳的最大玩家数量||||
|参数名称|类别|默认|描述|
|delay|double||延迟秒数|
|loop|bool||是否循环|
|interval|double||环间隔多少秒|
|cb|LuaFunction||回调方法|

|TimerRunState GetRunState()||
|:---|:---|
|获取运行状态||
|返回类型|概要|
|TimerRunState|运行状态。参见枚举TimerRunState|


## 事件

示例代码

```lua
local a = 0
local timer = SandboxNode.new("TimerNode") -- 创建定时器节点
timer.Delay = 1 -- 延迟多少秒开始
timer.Loop = true -- 是否循环
timer.Interval = 2 -- 循环间隔多少秒
timer.Callback = function() -- 回调方法
    a = a + 1
    print("timer : ", timer, " a=", a)
    if a == 4 then
        print("timer pause")
        timer:Pause() -- 暂停定时器，只有在定时器运行期间有效
        wait(4)
        print("timer resume")
        timer:Resume() -- 恢复定时器，只有在定时器运行暂停期间有效
    end
end
timer:Start()

-- 一次性传入参数，并且开始定时器
--timer:StartEx(3, true, 3, function() a = a + 1; print("timer ex : a=", a) end)
print("timer start")
```

