---
title: How to get FHitResult.FaceIndex
date: 2025-04-02
tags:
  - unreal
  - hitresult
  - trace
---
**Quick Tip:** In order for `FHitResult.FaceIndex` to return a valid index, multiple settings have to be enabled:

1. The trace being performed needs to trace complex (`bTraceComplex=true`)
2. The trace being performed needs to return the face index (`bReturnFaceIndex=true`)
3. Any mesh from traced against must have its **collision complexity** set to either **Use Complex Collision as Simple** or **Use Both Simple and Complex**. If the mesh only has a simple collision setup, the engine won't have triangle data to return.