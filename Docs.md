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
- `Pipeline` [Library for Server-Client Communication]
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

### Instance
Creates a New Instance.
```lua
Utilities.Instance(Instance <ClassName>, [Optional] Parent <Instance>, [Optional] Name <string>, [Optional] Properties <Dictionary>)

-- Example:
Utilities.Instance("Part", workspace, "ExamplePart", {Size = Vector3.new(5, 5, 5)}); -- Creates a part in workspace.
```

### ClearDirectory
Clears all objects inside a certain object. Ignores objects listed in `Globals.DO_NOT_CLEAR`
```lua
Utilities.ClearDirectory(Directory <Instance>)

-- Example:
Utilities.ClearDirectory(workspace); -- Clears the workspace.
```

### QuickTween
Performs a one-time tween on an object and removes the tween after.
```lua
Utilities.QuickTween(Object <Instance>, Properties <Dictionary>, [Optional] TweenSettings <TweenInfo>, [Optional] DestroyOnComplete <bool>, [Optional] OnFinish <function>)

-- Example:
Utilities.QuickTween(workspace.Part, {Size = Vector3.new(1, 1, 1)}); -- Fades a parts size to 1x1x1.
```
