---
title: Clip Actions
weight: 12
search:
  boost: 2
---

# Clip Actions

The following Actions are [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to control properties and functions of
Clips. By default, these Actions will apply to the playing Clip or (if no Clip is playing) the selected Clip
Slot on the Track. You can apply these Actions to other Clips or to ranges of Clips [as described here](/manual/general-action-information/#applying-actions-to-specific-objects-and-ranges).

!!! Note "See Also"
    - [Clip Loop Actions](clip-loop-actions)
    - [Clip Cue Action](clip-cue-action)
    - [Clip Envelope Actions](clip-envelope-actions)
    - [Clip Envelope Capture Action](clip-envelope-capture-action)
    - [Clip Note Actions](clip-note-actions.md)
---

### CLIP CENT `x`

Adjust Audio Clip Detune value. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP CENT -12
CLIP CENT >
```

### CLIP CHOP

Duplicate the Clip 8 times and set evenly distributed Start/Loop Start positions (starting from the Clip's current Start/Loop Start) across the duplicates. As with any duplication of a Clip, this will overwrite Clips that exist in the Clip Slots beneath the Clip that will be duplicated.

### CLIP CHOP `x`

Same as [CLIP CHOP](#clip-chop), but `x` is the number of times to duplicate. 

``` 
CHOP 4
CHOP 16
```

### CLIP COLOR `x`

`x` is the index of the Color (in the range of 1 - 70) to set the Clip to. 

```
CLIP COLOR 5
CLIP COLOR 43
```

### CLIP COLOR < or >

Select the previous/next Color for the Clip. 

```
CLIP COLOR <
CLIP COLOR >
```

### CLIP COLOR ASCOL

Set the Color of the Clip to be the same as the column (Track) it's on.

### CLIP COLOR ASROW

Set the Color of the Clip to be the same as the row (Scene) it's on.

### CLIP CROP

Crop the MIDI Clip.

### CLIP DEL 

Delete the Clip. 

### CLIP DUPE

Duplicate the Clip. 

### CLIP END `x`

`x` is the Clip End to set in Bars.Beats.Sixteenths (for Clips that are
Warped) or absolute beat time.

```
CLIP END 1.4.1
CLIP END 16
```

### CLIP END < or >

Decrement/increment the Clip's End by 1 Beat. 

```
CLIP END <
CLIP END >
```

### CLIP END <`x` or >`x` 

Decrement/increment the Clip's End by `x` Beats (specify `B` for Bars). 

```
CLIP END <2B
CLIP END >1
```

### CLIP EXTEND  

Double the Loop Length of the MIDI Clip and duplicate its content. If Loop is on, this will zoom out to show the entire Loop.

### CLIP GAIN `x`

Adjust Audio Clip Gain value (in the range of 0 - 127). This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP GAIN 64
CLIP GAIN >
```

### CLIP GRID `x`

`x` is the fixed grid setting to apply to the Clip. 

```
CLIP GRID OFF
CLIP GRID 1/32
```

### CLIP LEGATO

Toggle, turn on or turn off Clip Legato.

```
CLIP LEGATO
CLIP LEGATO ON
CLIP LEGATO OFF
```

### CLIP LMODE `x`

Set the Clip's Launch Mode.

````
CLIP LMODE GATE
CLIP LMODE TOGGLE
````

### CLIP LQ `x`

Adjust Clip Launch Quantization. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP LQ 1 BAR
CLIP LQ GLOBAL
```

### CLIP MUTE

Toggle, turn on or turn off Clip Mute.

```
CLIP MUTE
CLIP MUTE ON
CLIP MUTE OFF
```

### CLIP NAME `x`

`x` is the new name for the Clip.

```
CLIP NAME "Drums"
```

### CLIP NAMEA `x`

Similar to [CLIP NAME](#clip-name-x), but adds `x` after the current name. 

```
CLIP NAMEA "Alt"
```

### CLIP NAMEP `x`

Similar to [CLIP NAME](#clip-name-x), but adds `x` before the current name. 

```
CLIP NAMEP "Sub"
```

### CLIP NAMED `i` `x` 

Same as [CLIP NAME](#clip-name-x), but `i` is the new [Identifier](/manual/core-concepts#identifiers) of the Clip. A timestamp will be added to the Identifier in order to make the Identifier unique for use in [Snap Actions](/action-reference/snap-actions). Action Lists containing this Action**must** contain an Identifier at the beginning of the Action List.

```
CLIP NAMED [My Snap] "ALL/SNAP"
```

### CLIP NAMES `x`

Same as [CLIP NAME](#clip-name-x) except an [Identifier](/manual/core-concepts#identifiers) for the Clip will be generated based on the name of the Track and Scene the Clip resides on to make the Identifier unique for use in [Snap Actions](/action-reference/snap-actions).

```
CLIP NAMES "ALL/SNAP"
```

### CLIP QNTZ `x`

`x` is the value to Quantize the Clip's Notes or Warp markers to. The names of the available Quantization values are the same as those mentioned for the [RQ](/action-reference/global-actions/#rq) Action.

```
CLIP QNTZ 1/4
CLIP QNTZ 1/32
```

### CLIP QNTZ `x` `y`

Same as [CLIP QNTZ X](#clip-qntz-x), but `y` is the Strength of quantization (in the range of 0 - 100) to apply.

```
CLIP QNTZ 1/16 50
CLIP QNTZ 1/8 25
```

### CLIP QNTZ `x` `y` `z`

Same as [CLIP QNTZ X Y](#clip-qntz-x-y), but `z` is the amount of Swing (in the range of 0 - 100) to apply.

```
CLIP QNTZ 1/16 100 50
CLIP QNTZ 1/16 50 25
```

### CLIP QNTZ `n` `x`

> or `CLIP QNTZ n x y` 
> 
> or `CLIP QNTZ n x y z`

Same as the [CLIP QNTZ](#clip-qntz-x) Actions listed above, but `n` is the Pitch name or Pitch range to Quantize. See [Clip Note Actions](/action-reference/clip-actions/clip-note-actions) for more info on how to specify Pitches to operate upon.


```
CLIP QNTZ (C3) 1/8,
CLIP QNTZ (D#4-C5) 1/32 50,
CLIP QNTZ (E1) 1/16 50 25
```

### CLIP RAM

Toggle, turn on or turn off the Audio Clip's RAM mode switch.

```
CLIP RAM
CLIP RAM ON
CLIP RAM OFF
```


### CLIP SEMI `x`

Adjust Audio Clip Transpose value. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP SEMI -12
CLIP SEMI >
```

### CLIP SIG `x`/`y`

x``` is the Time Signature Numerator and `y` is the Denominator. 

```
CLIP SIG 4/4
CLIP SIG 6/8
```

### CLIP SPLIT `x`


`x` is the length of the segments in Beats (specify **B** for Bars) to split a Clip into. This will duplicate the Clip and set each segment to be the specified length. As with any duplication of a Clip, this will overwrite Clips that exist in the Clip Slots beneath the Clip that will be duplicated.

```
CLIP SPLIT 4
CLIP SPLIT 1B
```

### CLIP START `x`

Adjust Clip Start position. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP START 1.4.2
CLIP START 4
CLIP START >
```

### CLIP START <`x` or >`x`

Decrement/increment the Clip's Start by `x` Beats (specify **B** for Bars). 

```
CLIP START <2B
CLIP START >1
```

### CLIP TOARR `x`

Copy the Clip to Arrangement View at the given position.

```
CLIP TOARR 4.1.1
```

### CLIP TODR

Create a new MIDI Track with a Drum Rack containing the Audio Clip
as well as any other Devices that were on the Clip's Track.

### CLIP TOMIDI `x`

Convert the Audio Clip to a MIDI Clip where `x` is the type of conversion to perform.

```
CLIP TOMIDI DRUMS
CLIP TOMIDI HARMONY
CLIP TOMIDI MELODY
```

### CLIP TOSIMP

Create a new MIDI Track with a Simpler device containing the Audio Clip as well as any other Devices that were on the Clip's Track.

### CLIP TGRID

Toggle, turn on or turn off the Clip's triplet grid setting.

```
CLIP TGRID
CLIP TGRID ON
CLIP TGRID OFF
```

### CLIP WARP 

Toggle, turn on or turn off the Clip's Warp switch.

```
CLIP WARP
CLIP WARP ON
CLIP WARP OFF
```

### CLIP WARPMODE `x`

Adjust Audio Clip Warp Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). 

```
CLIP WARPMODE BEATS
CLIP WARPMODE >
```

### CLIP VELOCITY `x`

Adjust Clip Velocity Amount. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP VELOCITY 50
CLIP VELOCITY >
```

### REALIGN

Bring a Clip back into sync with the Set after manipulating its playing position.
