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

Columns
-------
game, category, mode   From the camo name (sat = Black Ops 7,
                       cer = Black Ops 6, jup = MW3, camo_x = base).
slots_used             Slot numbers the camo fills.
unique_textures        Fewer than slot_count means slots share a texture.
slot_0 ... slot_35     Texture ID in that slot. Same ID = same texture.

What each slot does is not mapped yet. Slots come in five groups of
seven (0-6, 7-13, 14-20, 21-27, 28-34) plus slot 35.
