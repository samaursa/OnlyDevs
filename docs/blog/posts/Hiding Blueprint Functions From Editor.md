---
title: Hiding Blueprint Functions From Editor
date: 2025-03-25
tags:
  - unreal
  - editor
  - blueprint
---
**Quick Tip:** Sometimes the Unreal Engine exposes functions in Blueprint that you'd rather keep hidden from designers or other team members. Using a simple INI configuration, you can selectively hide specific blueprint functions from appearing in the editor interface, keeping your blueprint context menus cleaner and more focused on the functions that matter for your project.

This example shows how to hide the `ClientPlayCameraShake` function from the PlayerController class, but you can apply this technique to any function you need to keep out of sight but still accessible via code.

```cpp
[BlueprintEditor.Menu]
+BlueprintHiddenFields="/Script/Engine.Actor:K2_AttachRootComponentTo"
+BlueprintHiddenFields="/Script/Engine.Actor:K2_AttachRootComponentToActor"
+BlueprintHiddenFields="/Script/Engine.Actor:DetachRootComponentFromParent"
+BlueprintHiddenFields="/Script/Engine.SceneComponent:K2_AttachTo"
+BlueprintHiddenFields="/Script/Engine.SceneComponent:DetachFromParent"
```