---
weight: 5
---

# Track Actions

The following Actions are [Track-based Actions](/manual/general-action-information#track-based-actions) that allow you to control parameters, properties and functions of Tracks.

---

### ADDCLIP

Create a 1 Bar MIDI Clip in the selected Clip Slot on the Track.

### ADDCLIP `x`

`x` is the Scene number of the Clip Slot where a 1 Bar MIDI Clip will be created. Specify `SEL` for the selected Scene, `LAST` for the last Scene in the Set or `EMPTY` for the first empty Clip Slot on the Track.

```
ADDCLIP 10
ADDCLIP SEL
ADDCLIP EMPTY
```

### ADDCLIP `x` `y`

Same as [ADDCLIP x](#addclip-x), but creates a MIDI Clip that is `y` Bars long.

```
ADDCLIP 10 4
ADDCLIP SEL 0.25
```

### ADDSTOP or REMSTOP

Add or remove the Stop Button from the selected Clip Slot on the Track. 

```
ADDSTOP
REMSTOP
```

### ADDSTOP `x` or REMSTOP `x`

`x` is the Scene number of the Clip Slot whose Stop Button will be added or removed. Specify `SEL` for the selected Scene, `LAST` for the last Scene or `ALL` for all Clip Slots.

```
ADDSTOP 10 
REMSTOP SEL
REMSTOP ALL
```

### ARM

Toggle, turn on or turn off Track Arm. [^1]

```
ARM
ARM ON
ARM OFF
```

### COLOR `x`

`x` is the index of the Color (in the range of 1 - 70) to set the Track to.

```
COLOR 5
COLOR 43
```

### COLOR < or >

Select the previous/next Color for the Track. 

```
COLOR <
COLOR >
```

### COPYCLIP 

Copy the Clip playing on the Track for use with the [PASTECLIP](#pasteclip-x) Action.

### COPYCLIP `x`

Same as COPYCLIP, but `x` is the Scene number of the Clip Slot or the name of the Clip to copy. Specify `SEL` for the selected Scene or `LAST` for the last Scene.

```
COPYCLIP 10
COPYCLIP "My Clip"
COPYCLIP SEL
```

### CUE

Adjust Preview Volume (Master Track only). This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

```
MST/CUE 50
MST/CUE >
```

### DEL

Delete the Track. It is not possible to Delete a Track if it's the only Track in the Set or if it's the Master Track.

### DUPE

Duplicate the Track. Returns and the Master Track cannot be Duplicated.

### FOLD

Toggle, turn on or turn off Track Fold. 

```
FOLD
FOLD ON
FOLD OFF
```

### IN `x`

Adjust Input Routing. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). 

```
IN "Computer Keyboard
IN >
```

### INSUB `x`

Adjust Input Sub-Routing. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). 

```
INSUB "Ch. 1"
INSUB >
```

### JUMP < or >

Jump the Playback Position of the playing Clip on the Track Backward/Forward by 1 Beat.

```
JUMP <
JUMP >
```

### JUMP <`x` or >`x`

Jump the Playback Position of the playing Clip on the Track Backward/Forward by `x` Beats (specify `B` for Bars).

```
JUMP <4B
JUMP >16
```

### MON or MON `x`

Toggle Track Monitoring state or set a particular state where `x` is the state to set.

```
MON
MON IN
MON AUTO
MON OFF
```

### MUTE

Toggle, turn on or turn off Track Mute (track activator).

```
MUTE
MUTE ON
MUTE OFF
```

### NAME `x`

`x` is the new name for the Track. 

```
NAME "Bkg Vocals"
```

### NAMEA `x`

Similar to [NAME](#name-x), but adds `x` after the current name. 

```
NAMEA "Synth"
```

### NAMEP `x`

Similar to [NAME](#name-x), but adds `x` before the current name. 

```
NAMEP "Layer"
```

### OUT `x`

Adjust Output Routing. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). 

```
OUT "To MT Player 1"
OUT >
```

### OUTSUB `x`

Adjust Output Sub-Routing. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties). 

```
OUTSUB "Ch. 10"
OUTSUB >
```

### PAN `x`

Adjust Track Pan. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

```
PAN 100
PAN >
```

### PANL `x` or PANR `x`

Adjust Track Left or Right Split Stereo Panning. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

### PASTECLIP `x`

`x` is the Scene number of the Clip Slot to paste into for use with the [COPYCLIP](#copyclip-x) Action. Specify `SEL` for the selected Scene, `LAST` for the last Scene in the Set or `EMPTY` for the first empty Clip Slot on the Track.

```
PASTECLIP 10
PASTECLIP SEL
```

### PASTECLIPE `x`

Same as [PASTECLIP](#pasteclip-x), but will only paste into empty Clip Slots.

```
PASTECLIPE 4
PASTECLIPE LAST
```

### PLAY

When triggered via an [X-Clip](/manual/core-concepts#x-clips), Launch the Clip Slot on the same Scene as the X-Clip. Otherwise, re-Launch the playing Clip Slot or Launch the Clip Slot at the selected Scene.

### PLAY `x`

`x` is the Scene number of the Clip Slot or the name of the Clip to Launch. Specify `SEL` for the selected Scene, `LAST` for the last Scene in the Set or
`EMPTY` for the first empty Clip Slot on the Track.

```
PLAY 10
PLAY SEL
PLAY "My Clip"
```

### PLAY RND

Launch a Clip Slot at a randomly selected Scene.

### PLAY RND`x`-`y`

Launch a Clip Slot at a randomly selected Scene in the range of `x`-`y` (where both `x` and `y` are in the range of 1 - the number of Scenes in the Set).

```
PLAY RND5-10
PLAY RND96-142
```

### PLAY RNDC

Same as the `RND` Actions covered above, but will not not Launch empty Clip Slots and does not apply to Group Tracks.

```
PLAY RNDC
PLAY RNDC10-50
```

### PLAY < or >

Launch the previous/next Clip Slot relative to the playing Clip. This will not Launch empty Clip Slots and does not apply to Group Tracks.

```
PLAY <
PLAY >
```

### PLAY <`x` or >`x`

Launch the Clip Slot that is `x`-Scenes prior to or after the playing Clip. This does not apply to Group Tracks.

```
PLAY <5
PLAY >3
```

### PLAYC

Same as the `PLAY` Actions listed above, but will not Launch empty Clip Slots and does not apply to Group Tracks.

```
PLAYC "My Clip"
PLAYC RND
PLAYC >
```

### PLAYL

Same as the `PLAY` Actions listed above, but Launches the Clip with Legato using the current Global Quantization value, will not Launch empty Clip Slots and does not apply to Group Tracks.

```
PLAYL "My Clip"
PLAYL RND
PLAYL >
```

### PLAYQ

Same as the `PLAY` Actions listed above, but Launches the Clip using a specific quantization value (regardless of the current Global Quantization value or the Launch Quantization value of the Clip), will not Launch empty Clip Slots and does not apply to Group Tracks.

```
PLAYQ NONE "My Clip"
PLAYQ 1 BAR RND
PLAYQ 1/4 >
```

### PLAYLQ

This is a combination of [PLAYL](#playl) and [PLAYQ](#playq).

### RECFIX `x`

Trigger fixed-length Session Record into the Clip Slot on the same Scene as the X-Clip or (for other [X-Trigger](/manual/core-concepts#x-triggers) types) the selected Scene where `x` is the length to record in Bars. Note, however, that Session Recording is always quantized according to Global Quantization and so your Global Quantization value needs to be less than or equal to the number of Bars to record for. For example, to record for 4 Bars, Global Quantization would need to be 4 Bars or less.

```
RECFIX 4
RECFIX 16
RECFIX 0.5
```

### RECFIX `x` `y`

Same as above, but `y` is the Scene number of the Clip Slot to record into. Specify `SEL` for the selected Scene, `LAST` for the last Scene in the Set or `EMPTY` for the first empty Clip Slot on the Track.

```
RECFIX 2 5
RECFIX 16 10
RECFIX 1 EMPTY
```

### RENAMEALL

Rename all the Clips on the Track based on the Track's name.

### RENAMEALL `x`

Rename all the Clips on the Track where `x` is the base name to use.

```
RENAMEALL "Drums"
```

### SEL

Select the Track and highlight the playing Clip or the Clip at the selected Scene.

### SEL `x`

Select the Track and a particular Clip Slot where `x` is the Scene number of the Clip Slot or the name of the Clip. Specify `SEL` for the selected Scene, `LAST` for the last Scene in the Set or `EMPTY` for the first empty Clip Slot on the Track.

```
SEL 10
SEL "My Clip"
SEL EMPTY
```

### SEND `ltr` `x`

`ltr` is the letter of the Track Send to adjust. Specify `ALL` to adjust all Track Sends. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

```
SEND A 50
SEND B >
SEND ALL RND
```

### SOLO

Toggle, turn on or turn off Track Solo. [^1]

```
SOLO
SOLO ON
SOLO OFF
```

### SPLITPAN

Toggle, turn on or turn off Track Split Stereo Panning.

```
SPLITPAN
SPLITPAN ON
SPLITPAN OFF
```

### STOP

Stop the playing Clip on the Track.

### STOP NQ 

Stop the playing Clip on the Track immediately (not quantized).

### VOL `x`

Adjust Track Volume. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

### XFADE or XFADE `x`

Toggle Track Crossfade assignment or set a particular state where `x` is the state to set.

```
XFADE
XFADE A
XFADE B
XFADE OFF
```

### XFADER `x`

Adjust Master Crossfader (Master Track only). This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters).

```
MST/XFADER 50
MST/XFADER >
```


[^1]: The ARM and SOLO Actions will not obey your Preference settings for Exclusive Arm and Solo. If you’d like to exclusively arm/solo a Track, you can first disarm/unsolo all Tracks. For example, to exclusively solo the selected Track: `ALL/SOLO OFF ; SEL/SOLO`

