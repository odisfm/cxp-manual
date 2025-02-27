---
weight: 22
---

# Push Actions

The following Actions apply to the Push and Push2 Control Surface scripts. These all require that either Push or Push2 is selected as a Control Surface. By default, these Actions will apply to the last (or only)Push or Push2 Control Surface script selected in Live's Preferences. When working with more than one Push and/or Push2 Control Surface script, you can target them by specifying their number. For example:

`PUSH 1 MODE SESSION`

`PUSH 4 MSG "I am the 4th Push script"`

In addition to the Actions listed here, the standard [Control Surface Actions](/action-reference/control-surface-actions) can also be applied to the Push and Push2 Control Surface scripts. However, with Push2, the RING-related Actions may produce undesirable results due to Push2's inclusion of Chain mixer settings alongside normal Track mixer settings.

!!! warning "Push 2 with Ableton 12+"
    As of Live 12, Push 2 no longer uses the traditional remote script system. When Push 2 is using this new 'mode', the actions on this page won't work.

    You can force Push 2 to use the legacy remote script mode and regain access to these actions. To do this, install the following Options.txt command:

    `-Push2UseLegacyScript`
    
    For instructions to create an Options.txt file, follow [this guide on the Ableton website](https://help.ableton.com/hc/en-us/articles/6003224107292).

___

### PUSH MODE `x`

`x` is the Push Mode to select. For the most part, these work in the same way they would work when pressing buttons on Push. So, for example, if you're in Device Mode, you can't select Stop Mode as it's not available when Device Mode is selected.

```
PUSH MODE SESSION
PUSH MODE NOTE
PUSH MODE STOP
PUSH MODE SOLO
PUSH MODE MUTE
PUSH MODE CLIP
PUSH MODE DEVICE
PUSH MODE 64PADS
PUSH MODE SCL
PUSH MODE USER
PUSH MODE LIVE
```

#### Only Push 1
```
PUSH MODE VOLUME
PUSH MODE PAN
PUSH MODE TRACK
```

#### Only Push 2
````
PUSH MODE MIX
````

### PUSH MSG `x`

Temporarily show a message in Push's display. By default, this will show the message in lower case. If you'd like capitalization to be preserved, use quotes.

```
PUSH MSG TRIGGER THE VERSE IN 4 BARS
PUSH MSG "Preserve Caps"
```

### PUSH PBMOD

Force the Touch Strip to enter its Pitch Bend/Mod Wheel Mode.
This is particularly useful in Note Mode when controlling a Drum
Rack.

### PUSH SCL

This Action is only accessible to [X-Clips](/manual/core-concepts/#x-clips) and [X-Scenes](manual/core-concepts/#x-scenes) and should not be combined with other Actions. This will capture the current Scale settings and store them in the X-Clip/X-Scene. Once settings have been stored, you can then add other Actions if you like or copy the stored settings and paste them into the Action List of other [X-Trigger types](/manual/core-concepts/#x-triggers).


### PUSH SCL FIXED

Toggle, turn on or turn off the Fixed Scale setting.

```
PUSH SCL FIXED
PUSH SCL FIXED ON
PUSH SCL FIXED OFF
```

### PUSH SCL INKEY

Toggle, turn on or turn off the In Key setting.

```
PUSH SCL INKEY
PUSH SCL INKEY ON
PUSH SCL INKEY OFF
```

### PUSH SCL OCT < or > 

Move to the previous/next Octave offset in Note Mode. 

```
PUSH SCL OCT <
PUSH SCL OCT >
```

### PUSH SCL ROOT `x`

Select the Root Note (only natural and sharp note names are
recognized) to use. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
PUSH SCL ROOT C
PUSH SCL ROOT >
```

### PUSH SCL TYPE `x`

Select the Scale Type (the available types are listed below) to use. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
PUSH SCL TYPE MAJOR,
PUSH SCL TYPE >
```

!!! info

    #### Available scale types

    Major, Minor, Dorian, Mixolydian, Lydian, Phrygian, Locrian, Whole Tone, Half-whole Dim., Whole-half dim., Minor Blues, Minor Pentatonic, Major Pentatonic, Harmonic Minor, Harmonic Major, Dorian #4, Phrygian Dominant, Melodic Minor, Lydian Augmented, Lydian Dominant, Super Locrian, 8-ToneSpanish, Bhairav, Hungarian Minor, Hirojoshi, In-Sen, Iwato, Kumoi, Pelog Selisir, Pelog Tembung, Messiaen 3, Messiaen 4, Messiaen 5, Messiaen 6