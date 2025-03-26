---
title: Using ExecCmds to Set Console Variables at Launch
date: 2025-03-25
tags:
  - unreal
  - cvar
  - launch
  - command
---
**Quick Tip:** Use `-ExecCmds` in your launch parameters to set multiple console variables (`CVars`) during startup.

- Add console commands to your launch parameters with this syntax:	
```cpp
	-ExecCmds="cvar1 value1, cvar2 value2, cvar3 value3"
``` 
- Commands execute immediately after `GameInstance` initialization
- Useful for testing specific configurations without changing code
- Multiple commands can be chained with commas as separators