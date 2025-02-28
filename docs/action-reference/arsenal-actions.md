---
weight: 20
---

# Arsenal Actions

The following Actions apply to Arsenal-powered Control Surface scripts where `N` is the name of the script to operate on. These all require that at least one Arsenal-powered Control Surface script is selected as a Control Surface.

In addition to the Actions listed here, the standard [Control Surface Actions](/action-reference/control-surface-actions) can also be applied to Arsenal-powered Control Surface scripts.

---

### ARSENAL `N` E_MODE `x`

Select Encoder Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). [^1]

```
ARSENAL AP2_A E_MODE 4
ARSENAL NLCX_C E_MODE >
```

### ARSENAL `N` LOCK

Lock to or unlock from the current Track.

```
ARSENAL NK2_A LOCK
ARSENAL LP1_F LOCK
```

### ARSENAL `N` M_MODE `x`

Select Matrix Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). [^2]

```
ARSENAL AP4_A M_MODE 4
ARSENAL LPP_C M_MODE >
```

### ARSENAL `N` MSG `x`

Temporarily show a message in the controller's display. By default, this will show the message in lower case. If you'd like capitalization to be preserved, use quotes. [^4]

```
ARSENAL PS1_A MSG THE VERSE
ARSENAL NSL_A MSG "Preserve Caps"
```

### ARSENAL `N` SCL

This Action is only accessible to [X-Clips](/manual/core-concepts/#x-clips) and [X-Scenes](manual/core-concepts/#x-scenes) and should not be combined with other Actions. This will capture the current Scale settings and store them in the X-Clip/X-Scene. 

Once settings have been stored, you can then add other Actions if you like or copy the stored settings and paste them into the Action List of other [X-Trigger types](/manual/core-concepts/#x-triggers).

```
ARSENAL LP2_A SCL
ARSENAL AP2_F SCL
```

!!! note

    #### Available Scale Types

    Major, Minor, Dorian, Mixolydian, Lydian, Phrygian, Locrian, Diminished, Whole-half, Whole Tone,Minor Blues, Minor Pentatonic, Major Pentatonic, Harmonic Minor, Melodic Minor, Super Locrian,Bhairav, Hungarian Minor, Minor Gypsy, Hirojoshi, In-Sen, Iwato, Kumoi, Pelog

### ARSENAL `N` SCL HORZ

Toggle, turn on of turn off the Horizontal Scale setting. [^3]

```
ARSENAL APM_A SCL HORZ
ARSENAL LPP_B SCL HORZ ON
ARSENAL PS1_F SCL HORZ OFF
```
### ARSENAL `N` SCL INKEY

Toggle, turn on or turn off the In Key Scale setting. [^3]

```
ARSENAL AP4_A SCL INKEY
ARSENAL APM_B SCL INKEY ON
ARSENAL LPP_F SCL INKEY OFF
```

### ARSENAL `N` SCL OFFSET `x`

Select the Scale Offset to use. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). [^3]

```
ARSENAL AP4_A SCL OFFSET SEQUENT
ARSENAL LPP_F SCL OFFSET >
```

!!! note

    #### Available Scale Offsets

    Sequent, 2nds, 3rds, 4ths, 5ths, 6ths

### ARSENAL `N` SCL ROOT `x`

Select the Root Note (only natural and sharp note names are recognized) to use. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). [^3]

```
ARSENAL LP1_A SCL ROOT C
ARSENAL AP2_F SCL ROOT >
```

### ARSENAL `N` SCL SEQ

Toggle, turn on or turn off the Sequent Layout Scale setting. [^3]

```
ARSENAL AP2_A SCL SEQ
ARSENAL APM_C SCL SEQ ON
ARSENAL LP1_F SCL SEQ OFF
```

### ARSENAL `N` SCL TYPE `x`

Select the Scale Type (the available types are listed below) to use. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). [^3]

```
ARSENAL AP4_A SCL TYPE MAJOR
ARSENAL LPP_F SCL TYPE >
```


[^1]: Requires that the script has Encoder Modes.

[^2]: Requires that the script has Matrix Modes.

[^3]: Requires that the script has at least one Matrix Mode that utilizes Scale settings (such as the Note, Note Plus, Scale or Scale Sequence Mode).

[^4]: Requires that the script is used with a controller that has a display.
