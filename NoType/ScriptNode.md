# ScriptNode
------------------------------------------------------------------------------------------
## 描述

继承：`SandboxNode`

------------------------------------------------------------------------------------------
## 属性


|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">luafile</font>]()</div>|
|:---|
|加载模式是`LoadMode::LUAFILE`时会执行设置的`luafile`的`string`内容|


|<div style="width:1125px">[string]() &emsp;[<font color="dd00dd">code</font>]()</div>|
|:---|
|加载模式是`LoadMode::LUACODE`时会执行设置`code`的字符串内容|

------------------------------------------------------------------------------------------
## 示例代码

```lua
--创建实例
local newScript = SandboxNode.new('ScriptNode')
--设置名字
newScript .Name = "my_script"
--设置脚本节点对应的文件
newScript.luafile = "res/jsonFiles/demo/SandboxNodeDemo.lua"
--设置脚本节点对应的string
newScript.code = "print('hello script')"
```