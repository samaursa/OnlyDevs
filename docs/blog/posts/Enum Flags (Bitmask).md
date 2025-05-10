---
title: Enum Flags (Bitmask)
date: 2025-05-09
tags:
  - unreal
  - enum
---
```cpp
UENUM(BlueprintType, meta = (Bitflags, UseEnumValuesAsMaskValuesInEditor = "true"))
enum class EPs_FireModes : uint8
{
    None   = 0,
    Single = 1 << 0,
    Burst  = 1 << 1,
    Auto   = 1 << 2
};
```

> [!warning] UseEnumValuesAsMaskValuesInEditor is necessary
> Moreover, `None = 0` as the first enum is also required. Note that without `UseEnumValuesAsMaskValuesInEditor` the enum flags will **NOT** behave correctyl