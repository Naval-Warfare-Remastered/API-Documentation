# Naval Warfare Remastered Global Enviroment API
Hello, Welcome to the Naval Warfare Remastered API Documentation. This has been written by plainenglish to help other NWR developers and contributors understand the 

## Accessing the API
The API is accessed by referencing the NWR entry in the \_G enviroment.
```lua
local NWR = _G.NWR;

--// Example:
local NWR = _G.NWR;
local Globals = NWR.Globals;
local Resources = NWR.Resources;
```

### Global API
The Global API contains the following;

#### Global
- `Constants` [Table of Constants]
- `Globals` [Table of Globals]
- `Pipeline` [Library for Server-Client Communication] // WORK IN PROGRESS //
- `Utilities` [Library for random utility functions]
- `Debug` [Library for logging events]
- `Resources` [Library for accessing the built in content provider]
- `ModuleLoader` [Library for loading ModuleScripts]

#### Server Specific
- `N/A`

#### Client Specific
- `N/A`

## Utilities
The Utilities library comes with the following functions:

#### Instance
Creates a New Instance.
```lua
<Instance> Utilities.Instance(Instance <ClassName>, [Optional] Parent <Instance>, [Optional] Name <string>, [Optional] Properties <Dictionary>)

-- Example:
Utilities.Instance("Part", workspace, "ExamplePart", {Size = Vector3.new(5, 5, 5)}); -- Creates a part in workspace.
```

#### ClearDirectory
Clears all objects inside a certain object. Ignores objects listed in `Globals.DO_NOT_CLEAR`
```lua
Utilities.ClearDirectory(Directory <Instance>)

-- Example:
Utilities.ClearDirectory(workspace); -- Clears the workspace.
```

#### QuickTween
Performs a one-time tween on an object and removes the tween after.
```lua
Utilities.QuickTween(Object <Instance>, Properties <Dictionary>, [Optional] TweenSettings <TweenInfo>, [Optional] DestroyOnComplete <bool>, [Optional] OnFinish <function>)

-- Example:
Utilities.QuickTween(workspace.Part, {Size = Vector3.new(1, 1, 1)}); -- Fades a parts size to 1x1x1.
```

## Resources
The Resources library comes with the following functions:

#### GetInstance
Clones an instance in the resource folder and returns it.
```lua
<Instance> Resouces.GetInstance(Type <string>, Name <string>)

-- Example:
Resouces.GetInstance("Image", "TestImage").Parent = workspace; -- Copies an image called TestImage and sends it to workspace.
```

#### GetInstanceDirect
Returns the direct instance without cloning. **BE CAREFUL, DO NOT MODIFY THE RETURNED INSTANCE, ONLY READ.**
```lua
<Instance> Resouces.GetInstanceDirect(Type <string>, Name <string>)

-- Example:
print(Resouces.GetInstance("Image", "TestImage").Texture) -- Prints the texture of "TestImage".
```

## ModuleLoader
The ModuleLoader library comes with the following functions:

#### DeployModule
Deploys a module file.
```lua
ModuleLoader.DeployModule(Module <ModuleScript>)	

-- Example:
ModuleLoader.DeployModule(script.Client); -- Deploys the client module.
```

#### GetModuleFunction
Returns the source function of a module.
```lua
ModuleLoader.GetModuleFunction(Module <ModuleScript>)

-- Example:
print(string.dump(ModuleLoader.GetModuleFunction(script.Client))); -- Dumps the client module.
```

## Debug
The Debug library comes with the following functions:

#### Log
Prints to the output.
```lua
Debug.Log(Text <string>, [Optional] SubText <string>)

-- Example:
Debug.Log("Hello world!");
```

#### Warn
Prints to the output in yellow.
```lua
Debug.Warn(Text <string>, [Optional] SubText <string>)

-- Example:
Debug.Warn("Hello world!");
```

#### Info
Prints to the output in blue.
```lua
Debug.Info(Text <string>, [Optional] SubText <string>)

-- Example:
Debug.Info("Hello world!");
```

#### Error
Prints to the output in red.
```lua
Debug.Error(Text <string>, [Optional] SubText <string>)

-- Example:
Debug.Error("Hello world!");
```

#### GetLogs
Returns an array of logs for the peer the function is called on.
```lua
<Array> Debug.GetLogs()

-- Example:
for i, v in pairs(Debug.GetLogs()) do
  print(v);
 end
```
