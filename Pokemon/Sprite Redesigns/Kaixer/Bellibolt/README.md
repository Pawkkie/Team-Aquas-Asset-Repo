## Sprite Insertion Instructions

![Bellibolt.png](Bellibolt.png)

![BelliboltAnim.gif](BelliboltAnim.gif)

in `front_pic_anims.h`:

```diff
-PLACEHOLDER_ANIM_SINGLE_FRAME(Bellibolt);
+static const union AnimCmd sAnim_Bellibolt_1[] =
+{
+    ANIMCMD_FRAME(1, 20),
+    ANIMCMD_FRAME(0, 10),
+    ANIMCMD_END,
+};
```

Then change `//.frontAnimId = ANIM_V_SQUISH_AND_BOUNCE,`, to any animation you want. I'm using `.frontAnimId = ANIM_FLASH_YELLOW,` and for the back anim do the same but change it to `.backAnimId = BACK_ANIM_SHAKE_FLASH_YELLOW,`

Lastly, change:

```diff
-const u32 gMonFrontPic_Bellibolt[] = INCBIN_U32("graphics/pokemon/gen_9/bellibolt/front.4bpp.lz");
+const u32 gMonFrontPic_Bellibolt[] = INCBIN_U32("graphics/pokemon/gen_9/bellibolt/front_anim.4bpp.lz"); 
```
