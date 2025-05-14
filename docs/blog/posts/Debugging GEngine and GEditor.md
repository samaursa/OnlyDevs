---
title: Debugging GEngine and GEditor
date: 2025-05-13
tags:
  - unreal
  - debug
  - visual-studio
---
Debugging global variables is different than debugging regular variables in Visual Studio on Windows.
![](attachments/Pasted%20image%2020250513212813.png)

Every static variable is defined in its own `dll` module. Visual Studio requires the variable to be qualified by the module:
```cpp
{,,UnrealEditor-Engine}::GEngine
{,,UnrealEditor-Core}::GFrameNumber
{,,UnrealEditor-UnrealEd}::GEditor
```