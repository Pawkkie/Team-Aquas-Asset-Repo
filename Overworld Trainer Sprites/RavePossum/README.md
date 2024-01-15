## Poffin Case's FRLG Overworlds Converted for pokeemerald

This is the full set of [Poffin Case's FRLG overworlds](https://github.com/Pawkkie/Team-Aquas-Asset-Repo/tree/main/Overworld%20Trainer%20Sprites/Poffin_Case) with the following changes:
- All sprites use vanilla palettes
- All sprites are named like the original file and in the right location (every single vanilla overworld NPC sprite is included, besides unused sprites)
- Some sprites have been altered or recolored to more closely match the original sprites

What that means is that these sprites are *drag and drop-ready* so all you need to do to implement them is replace all of the original files in `graphics/object_events/pics/people/`. Then, just make two tiny code changes so the fly animations line up properly.

## Code Changes

### field_effect.c

SpriteCB_FlyBirdLeaveBall()
```diff
...
        sprite->affineAnims = sAffineAnims_FlyBird;
        InitSpriteAffineAnim(sprite);
        StartSpriteAffineAnim(sprite, 0);
-       sprite->x = 0x76;
+       sprite->x = 0x80;
        sprite->y = -0x30;
        sprite->data[0]++;
        sprite->data[1] = 0x40;
...
```

SpriteCB_FlyBirdReturnToBall()
```diff
...
        sprite->data[1] += sprite->data[2] >> 8;
        sprite->data[3] += sprite->data[2] >> 8;
        sprite->data[1] &= 0xff;
-       sprite->x2 = Cos(sprite->data[1], 0x20);
+       sprite->x2 = Cos(sprite->data[1], 0x40);
        sprite->y2 = Sin(sprite->data[1], 0x78);
        if (sprite->data[2] > 0x100)
...
```

If you find any glaring mistakes in these, please let me on Discord @ravepossum :)