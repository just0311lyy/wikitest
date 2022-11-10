# ModuleScriptNode
------------------------------------------------------------------------------------------
#### 描述：

`ModuleScriptNode`它只会运行一次，并且必定返回相同的一个值。然后在 `ModuleScriptNode`作为唯一参数的情况下，通过调用`require`返回此值。对于每个`Lua`环境，`ModuleScriptNode`运行且仅运行一次，并且在后续调用`require`时返回该相同的值。<br>
继承：`ScriptNode` 

------------------------------------------------------------------------------------------
#### 示例代码：

```lua
	local ModuleA = SandboxNode.new("ModuleScriptNode")
	ModuleA.StringCode = "local a = 5 return a+1"

	local value1 = require(ModuleA)
	print("value1:"..value1)
	--value1:6
```