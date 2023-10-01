## ORAS May with RS Colours
- Overworld sprites
- Original sprites by Poffin_Case
- Wailmer dive sprites by Pawkkie
- Reformatting, recolouring, and extensive sprite changes / reworks by Pawkkie

![acro_bike.png](acro_bike.png)
![decorating.png](decorating.png)
![field_move.png](field_move.png)
![fishing.png](fishing.png)
![mach_bike.png](mach_bike.png)
![running.png](running.png)
![surfing.png](surfing.png)
![underwater.png](underwater.png)
![walking.png](walking.png)
![watering.png](watering.png)

## Sprite Insertion Instructions
This May's running sprite is 32 pixels wide, so the walking sprite was also converted to be 32 pixels wide. By default May's run / walk sprites are only 16 pixels wide, so I wanted to include a section on how to make the conversion.

in `spritesheet_rules.mk`:
```diff
$(OBJEVENTGFXDIR)/people/may/walking.4bpp: %.4bpp: %.png
-	$(GFX) $< $@ -mwidth 2 -mheight 4
+	$(GFX) $< $@ -mwidth 4 -mheight 4

$(OBJEVENTGFXDIR)/people/may/running.4bpp: %.4bpp: %.png
-	$(GFX) $< $@ -mwidth 2 -mheight 4
+	$(GFX) $< $@ -mwidth 4 -mheight 4
```

in `src/data/object_events/object_event_graphics_info.h`:
```diff
const struct ObjectEventGraphicsInfo gObjectEventGraphicsInfo_MayNormal = {
    .paletteTag = OBJ_EVENT_PAL_TAG_MAY,
    .reflectionPaletteTag = OBJ_EVENT_PAL_TAG_BRIDGE_REFLECTION,
    .size = 512,
-    .width = 16,
+    .width = 32,
    .height = 32,
    .paletteSlot = PALSLOT_PLAYER,
    .shadowSize = SHADOW_SIZE_M,
    .inanimate = FALSE,
    .disableReflectionPaletteLoad = FALSE,
    .tracks = TRACKS_FOOT,
-    .oam = &gObjectEventBaseOam_16x32,
-    .subspriteTables = sOamTables_16x32,
+    .oam = &gObjectEventBaseOam_32x32,
+    .subspriteTables = sOamTables_32x32,
    .anims = sAnimTable_BrendanMayNormal,
    .images = sPicTable_MayNormal,
    .affineAnims = gDummySpriteAffineAnimTable,
```
```diff
const struct ObjectEventGraphicsInfo gObjectEventGraphicsInfo_RivalMayNormal = {
    .tileTag = TAG_NONE,
    .paletteTag = OBJ_EVENT_PAL_TAG_MAY,
    .reflectionPaletteTag = OBJ_EVENT_PAL_TAG_BRIDGE_REFLECTION,
-    .size = 256,
-    .width = 16,
+    .size = 512,
+    .width = 32,
    .height = 32,
    .paletteSlot = PALSLOT_NPC_SPECIAL,
    .shadowSize = SHADOW_SIZE_M,
    .inanimate = FALSE,
    .disableReflectionPaletteLoad = FALSE,
    .tracks = TRACKS_FOOT,
-    .oam = &gObjectEventBaseOam_16x32,
-    .subspriteTables = sOamTables_16x32,
+    .oam = &gObjectEventBaseOam_32x32,
+    .subspriteTables = sOamTables_32x32,
    .anims = sAnimTable_BrendanMayNormal,
    .images = sPicTable_MayNormal,
    .affineAnims = gDummySpriteAffineAnimTable,
```
```diff
const struct ObjectEventGraphicsInfo gObjectEventGraphicsInfo_LinkMay = {
    .tileTag = TAG_NONE,
    .paletteTag = OBJ_EVENT_PAL_TAG_MAY,
    .reflectionPaletteTag = OBJ_EVENT_PAL_TAG_BRIDGE_REFLECTION,
-    .size = 256,
-    .width = 16,
+    .size = 512,
+    .width = 32,
    .height = 32,
    .paletteSlot = PALSLOT_NPC_SPECIAL,
    .shadowSize = SHADOW_SIZE_M,
    .inanimate = FALSE,
    .disableReflectionPaletteLoad = FALSE,
    .tracks = TRACKS_FOOT,
-    .oam = &gObjectEventBaseOam_16x32,
-    .subspriteTables = sOamTables_16x32,
+    .oam = &gObjectEventBaseOam_32x32,
+    .subspriteTables = sOamTables_32x32,
    .anims = sAnimTable_BrendanMayNormal,
    .images = sPicTable_MayNormal,
    .affineAnims = gDummySpriteAffineAnimTable,
```
in `rc/data/object_events/object_event_pic_tables.h`:
```diff
static const struct SpriteFrameImage sPicTable_MayNormal[] = {
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 0),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 1),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 2),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 3),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 4),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 5),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 6),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 7),
-    overworld_frame(gObjectEventPic_MayNormal, 2, 4, 8),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 0),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 1),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 2),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 3),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 4),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 5),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 6),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 7),
-    overworld_frame(gObjectEventPic_MayRunning, 2, 4, 8),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 0),
+   overworld_frame(gObjectEventPic_MayNormal, 4, 4, 1),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 2),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 3),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 4),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 5),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 6),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 7),
+    overworld_frame(gObjectEventPic_MayNormal, 4, 4, 8),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 0),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 1),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 2),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 3),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 4),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 5),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 6),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 7),
+    overworld_frame(gObjectEventPic_MayRunning, 4, 4, 8),
};
```
