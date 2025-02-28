---
weight: 20
---

# CrossFire Actions

The following Actions apply to the CrossFire Control Surface scripts. These all require that CrossFire is selected as a Control Surface.

In addition to the Actions listed here, the standard [Control Surface Actions](/action-reference/control-surface-actions) can also be applied to the CrossFire Control Surface script.

---

### CROSSFIRE LOCK 

Lock to or unlock from the current Track.

### CROSSFIRE MODE `x`

`x` is the name of the Mode to select. 

```
CROSSFIRE STEP
CROSSFIRE NOTE
CROSSFIRE DRUM
CROSSFIRE PERFORM
CROSSFIRE CHAIN
CROSSFIRE MIXER
CROSSFIRE USER CHAIN
CROSSFIRE USER MIXER
```

### CROSSFIRE MSG `x`

Temporarily show a message in the controller's display. By default,
this will show the message in lower case. If you'd like capitalization to be preserved, use quotes.

```
CROSSFIRE MSG THE VERSE.
CROSSFIRE MSG "Preserve Caps"
```

### CROSSFIRE SCL

This Action is only accessible to [X-Clips](/manual/core-concepts/#x-clips) and [X-Scenes](manual/core-concepts/#x-scenes) and should not be combined with other Actions. This will capture the current Scale settings and store them in the X-Clip/X-Scene. Once settings have been stored, you can then add other Actions if you like or copy the stored settings and paste them into the Action List of other [X-Trigger types](/manual/core-concepts/#x-triggers).

### CROSSFIRE SCL OCT < or > 

Move to the previous/next Octave offset in Note Mode. 

```
CROSSFIRE SCL OCT <
CROSSFIRE SCL OCT >
```

### CROSSFIRE SCL ROOT `x`

Select the Root Note (only natural and sharp note names are
recognized) to use in Note Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
CROSSFIRE SCL ROOT C
CROSSFIRE SCL ROOT >
```

### CROSSFIRE SCL TYPE `x`

Select the Scale Type (the available types are listed below) to use in Note Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
CROSSFIRE SCL TYPE MAJOR
CROSSFIRE SCL TYPE >
```

!!! info "Available Scale Types"
    Dual Keyboard, Major, Minor, Dorian, Mixolydian, Lydian, Phrygian, Locrian, Whole Tone, Half-whole Dim., Whole-half dim., Minor Blues, Minor Pentatonic, Major Pentatonic, Harmonic Minor, Harmonic Major, Dorian #4, Phrygian Dominant, Melodic Minor, Lydian Augmented, Lydian Dominant, Super Locrian, 8-Tone Spanish, Bhairav, Hungarian Minor, Hirojoshi, In-Sen, Iwato, Kumoi, Pelog Selisir, Pelog Tembung, Messiaen 3, Messiaen 4, Messiaen 5, Messiaen 6, Messiaen 7, Chromatic
