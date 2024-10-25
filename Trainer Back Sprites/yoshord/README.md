## Lance (Lets Go Kanto Outfit)
- Trainer Back Sprite
- yoshord

This has an extra frame compared to the standard back sprite array.
Intended to be used with the following `AnimCmd` array.
Or you can remove either frame 1 or frame 2 and use the Red/Leaf `AnimCmd`s

```
static const union AnimCmd sAnimCmd_Lance_Back[] =
{
    ANIMCMD_FRAME(1, 8),
    ANIMCMD_FRAME(2, 12),
    ANIMCMD_FRAME(3, 6),
    ANIMCMD_FRAME(4, 6),
    ANIMCMD_FRAME(5, 24),
    ANIMCMD_FRAME(0, 50),
    ANIMCMD_END,
};
```

![](lance_\(lets_go\).png)
