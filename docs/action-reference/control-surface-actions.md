---
weight: 18
---

# Control Surface Actions

The following Actions apply to Control Surface scripts that are selected in Live's Control Surface section (in Preferences on the Link/MIDI tab) where `N` is the name or number of the script to operate on.

When specifying a script by number, the numbering is based on the number of Control Surface scripts that are selected. For example, if only two scripts are selected, the second script will be 2 even if the script is selected in Control Surface slot #6.

When specifying a script by name, if the name appears to have spaces in it (such as PXT Live), the spaces should be replaced by underscores (such as PXT_Live). If multiple scripts with the same name are in use, it is recommended that you specify the number of the script instead of its name.

Except where noted, these Actions will work with most of the Control Surface scripts built into Live (as well as User Remote Scripts and most user-created Framework scripts). However, they will not work with some of the legacy scripts such as the Mackie scripts and the Tranzport script.

---

### CS `N` `x`/ `ACTION NAME`

Apply a Track-based Action to Channel Strip number `x`. [^1]

```
CS 1 1/MUTE, CS "APC40" 4/DEV RND
CS 3 8/CLIP SEMI >
```

### CS `N` `x`-`y`/ `ACTION NAME`

Apply a [Track-based Action](/manual/general-action-information/#track-based-actions) to a range of Channel Strips. You can use a [range specification](/manual/general-action-information/#applying-actions-to-specific-objects-and-ranges), but should strictly use Channel Strip numbers or ALL when specifying the range. [^1]

```
CS 1 1-4/FOLD, CS "Push" 4, 8/DEV
CS 3 ALL/CLIP START >
```

### CS `N` BANK < or >

Move the script's Track Bank selection Backward/Forward by increment of 1 Track and (if the script doesn't indicate the Track it's controlling) select the first Track in the new Bank selection. [^1]

```
CS 1 BANK <
CS "MPD32" BANK >
```

### CS `N` BANK <`x` or >`x`

Same as above except `x` is the increment to use. [^1]

```
CS 1 BANK <2
CS "MPD32" BANK >8
```

### CS `N` BANK LAST or FIRST

Move the script's Track Bank selection to the first or last Bank.

```
CS 1 BANK FIRST
CS "MPD32" BANK LAST
```

### CS `N` COLORS `x` `y` `z`

Change the color of the Clip Launch LEDs where `x` is the color to use for playing Clips, `y` is the color to use for recording Clips and `z` is the color to use for stopped Clips. The available colors are: `AMBER`, `GREEN` and `RED`. [^4]

**This is a temporary change that will be reverted upon loading a Set.**

```
CS 1 COLORS RED AMBER GREEN
CS "APC20" COLORS GREEN RED AMBER
```

### CS `N` DEV BANK `x`

`x` is the number of the Bank of Device parameters to select. [^2]

```
CS 1 DEV BANK 2
CS "APC40" DEV BANK 5
```

### CS `N` DEV BANK < or >

Move to the previous/next Bank of Device parameters. 

```
CS 1 DV BANK >
CS "Push" DEV BANK <
```

### CS `N` DEV LOCK

Toggle the script's lock on Devices. [^2]

```
CS 1 DEV LOCK
```

### CS `N` FULLVELO

Toggle, turn on or turn off Full Velocity for the script. When on, notes sent from the controller will have full velocity (127).

```
CS 4 FULLVELO
CS 1 FULLVELO ON
CS "Launchpad_Pro" FULLVELO OFF
```

### CS `N` RING T`x` S`y`

`x` is the name or number of the first Track outlined by the ring. `y` is the name or number of the first Scene outlined by the ring. Only one of these has to be specified so that you can change the Scene offset without changing the Track offset and vice versa. [^3]

### CS `N` RING < or > / S< or >

Move the ring Backward/Forward by increment of 1 Track and/or 1 Scene. Only one of these has to be specified so that you can increment Tracks without incrementing Scenes and vice versa. [^3]

```
CS 1 RING T1 S20
CS "APC40" RING S"My Scene"
CS 4 RING T5
CS "Push" RING T"My Track" S100
```

### CS N RING T<`x` or >`x` / S<`x` or >`x`

Same as above except `x` is the increment to use. [^3]

```
CS "APC40" RING T>4 S<8
CS 1 RING T<2, CS 1 RING T>10
```

### CS `N` RING LAST

Move the ring back to the position it was at prior to triggering one of the Ring Actions described above.

```
CS "APC40" RING LAST
CS 1 RING LAST
```

### CS `N` RINGLINK `T` `S`

Cause the script's ring to be linked to the selected Track and/or Scene.
Only one of these has to be specified so that you can link to Tracks without linking to Scenes and vice versa. You can also specify `CENTER`, which will cause the ring to be centered around the selected
Track and/or Scene. [^3]

```
CS "APC40" RINGLINK T S
CS 1 RINGLINK T CENTER
CS "Push" RINGLINK S
```

### CS `N` RINGLINK OFF

Turn the script's ring linking off. [^3]

```
CS "APC40" RINGLINK OFF
```

### CS `N` RPT

Toggle Note Repeat on/off. [^5]

```
CS 1 RPT
```

### CS `N` RPT `x`

`x` is the Note Repeat rate to set. [^5]

```
CS 1 RPT OFF
CS "MPD32" RPT 1/4
CS 4 RPT 1/32T
```



[^1]: Requires that the script has Channel Strip controls (like Volume, Pan, Mute, etc).

[^2]: Requires that the script has Device controls.

[^3]: Requires that the script has a grid selector (aka red ring). Also, in order for a Track to be outlined by the ring, the Track needs be visible. In other words, it isn't possible to move the ring to a Track that is inside of a Group Track that is closed.

[^4]: Only applies to the builtin APC20, APC40, APC mini and Launchpad scripts.

[^5]: Requires that the controller can send notes to MIDI Tracks and that its Track switch be turned on. When RPT is on, notes sent from the controller will produce a consistent stream of rhythmic notes at the specified rate. Additionally, the available Note Repeat rates are as follows: 

    OFF, 1/4D, 1/4, 1/4T, 1/8D, 1/8, 1/8T, 1/16D, 1/16, 1/16T, 1/32D, 1/32, 1/32T, 1/64D, 1/64, 1/64T (where 'D' stands for dotted and 'T' stands for triplet). 

    Swing can also be applied by using the [SWING](/action-reference/global-actions#swing-x) Actions covered in [Global Actions](/action-reference/global-actions).