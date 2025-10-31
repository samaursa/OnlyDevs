---
title: DrawDebugString Per-Actor Limit
date: 2025-10-31
tags:
  - unreal
  - debug
---
**Quick Tip:** DrawDebugString has a maximum number of strings that can be displayed per actor. By default, this limit is **128 strings**.

If you're hitting this limit and your debug text is getting cut off, you can adjust it using the console command:

```
r.DebugSafeZone.MaxDebugTextStringsPerActor
```

Set it to your desired limit, or use `0` for unlimited strings (though be warned—this will tank your FPS very quickly if you're displaying a large number of strings).