---
title: Seamless Travel
date: 2025-03-25
tags:
  - unreal
  - multiplayer
---
**Quick Tip:** Testing seamless level transitions in PIE became possible starting with Unreal Engine 5.1!
To get this working, you'll need to:

1. Configure your `GameMode` to use seamless travel
2. Add this to your `DefaultEngine.ini`
```cpp
[SystemSettings]  
net.AllowPIESeamlessTravel=1
```
3. Set up a transition level in your project settings
