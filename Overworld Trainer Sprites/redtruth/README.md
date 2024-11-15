# RSE style overworld sprites

Please credit redtruth (mako)

## Gate Guard
![Gate Guard](./gate_guard.png)

Uses the NPC_1 palette, and the following pic table:

```c
static const struct SpriteFrameImage sPicTable_GateGuard[] = {
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 0),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 1),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 2),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 0),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 0),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 1),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 1),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 2),
    overworld_frame(gObjectEventPic_GateGuard, 2, 4, 2),
};
```

