
# TimerNode
------------------------------------------------------------------------------------------
## 描述

TimerNode 定时器节点允许指定一个lua 回调方法在一定时间后执行。


------------------------------------------------------------------------------------------
## 属性

|<div style="width:925px">[LuaFunction](/DataType/Luafunction.md) &emsp;[<font color="dd00dd">Callback</font><br /> ]()</div>|
|:-----------------------|
|lua回调方法             |

|<div style="width:925px">[double]() &emsp;[<font color="dd00dd">Delay</font><br /> ]()</div>|
|:-----------------------|
|首次延迟执行的事件           |

|<div style="width:925px">[bool]() &emsp;[<font color="dd00dd">Loop</font><br /> ]()</div>|
|:-----------------------|
|是否循环执行           |

|<div style="width:925px">[double]() &emsp;[<font color="dd00dd">Interval</font><br /> ]()</div>|
|:-----------------------|
|循环执行间隔           |

|<div style="width:925px">[TimerRunState]() &emsp;[<font color="dd00dd">TimerRunState</font><br /> ]()</div>|
|:-----------------------|
|当前循环状态，包括：空闲，运行，暂停。           |




------------------------------------------------------------------------------------------
## 函数


|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">Start</font>]()()</div>|
|:-----------------------|
|暂停。需要在开始执行后调用           |

|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">Pause</font> ]()()</div>|
|:-----------------------|
|暂停。需要在开始执行后调用           |

|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">Resume</font> ]()()</div>|
|:-----------------------|
|恢复。需要在暂停后调用           |

|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">Stop</font>]()()</div>|
|:-----------------------|
|停止。需要在执行后调用          |

|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">StartEx</font> ]() ([double]() delay, [bool]() loop, [double]() interval, [AutoRef<LuaFunction>]() cb)  </div>|
|:-----------------------|
|开始执行。附带初始化的参数此服务器中可以容纳的最大玩家数量          |

|<div style="width:925px">[void]() &emsp;[<font color="dd00dd">GetRunState</font> ]() ()  </div>|
|:-----------------------|
|开始执行。附带初始化的参数此服务器中可以容纳的最大玩家数量          |





## 事件
------------------------------------------------------------------------------------------
## 示例代码

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

