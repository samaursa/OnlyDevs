---
title: Hiding Blueprint Functions From Editor
date: 2025-03-25
tags:
  - unreal
  - editor
  - blueprint
---
Modify the INI file to feature the functions to hide

```cpp
[BlueprintEditor.Menu]
+BlueprintHiddenFields="/Script/Engine.Actor:K2_AttachRootComponentTo"
+BlueprintHiddenFields="/Script/Engine.Actor:K2_AttachRootComponentToActor"
+BlueprintHiddenFields="/Script/Engine.Actor:DetachRootComponentFromParent"
+BlueprintHiddenFields="/Script/Engine.SceneComponent:K2_AttachTo"
+BlueprintHiddenFields="/Script/Engine.SceneComponent:DetachFromParent"
```