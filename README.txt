Custom camos
============

camo_slots.csv   Every camo and the texture in each of its 36 slots.
                 GitHub shows it as a searchable table: type a camo
                 name or "zm" in the filter box above the table.
index.html       Same list as a page: https://divity.github.io/kronos-camos/

Make a pack
-----------
1. Find the camo you want to replace. Example: Infestation (Zombies
   mastery) is sat_camo_comp_04_zm.
2. Make the folder:
     kronos\Assets\Camos\<your pack>\<camo name>\
3. Add PNGs named after the slot number, like 0.png or 7.png.
   Only slots listed in slots_used for that camo do anything.
4. Restart the game. poi_reg.log shows "camos/<camo>/<slot> applied".

Previews
--------
previews/<camo name>.webp is the game's own menu preview for that
camo, taken from its ui_<camo name> image. 2,390 of the 2,412 camos
have one.

Columns
-------
game, category, mode   From the camo name (sat = Black Ops 7,
                       cer = Black Ops 6, jup = MW3, camo_x = base).
slots_used             Slot numbers the camo fills.
unique_textures        Fewer than slot_count means slots share a texture.
slot_0 ... slot_35     The texture in that slot: its real name when known,
                       else image_<hash>, the name export tools give it.

What each slot does
-------------------
Slots come in five groups of seven plus slot 35. The texture format
the game uses for each group shows what it is:
  0-6     color (sRGB)
  7-13    normal + gloss, packed (linear RGBA)
  14-20   grayscale mask (one channel)
  21-27   second color layer (sRGB)
  28-34   data map (linear RGB)
  35      distortion map (names end in _distort or _wobble)
Most camos use slots 0, 1 and 7, and almost half also use 21.
