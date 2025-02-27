---
weight: 7
---

# Simpler Actions

The following Actions are [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to control parameters, properties and functions of Simpler. The Device to apply these Actions to can be specified in the same way as described in [Device Actions](/action-reference/device-actions).

### DEV SIMP BPM `x`

Halve or double the Tempo of the Sample. 

```
DEV SIMP BPM *0.5
DEV SIMP BPM *2
```

### DEV SIMP CLR

Clear all Slices when in Transient or Manual Slicing Mode.

### DEV SIMP CROP

Crop the loaded Sample.

### DEV SIMP DEL

Delete the selected Slice when in Transient or Manual Slicing Mode.

### DEV SIMP END `x`

Adjust the Sampler's End Marker (in the range of 0 - 127). This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
DEV SIMP END 100
DEV SIMP END >
```

### DEV SIMP GAIN `x`

Adjust the Sample's Gain value (in the range of 0 - 127). This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
DEV SIMP GAIN 64
DEV SIMP GAIN >
```

### DEV SIMP GATE

Toggle, turn on or turn off Gate Trigger Mode.

```
DEV SIMP GATE
DEV SIMP GATE ON
DEV SIMP GATE OFF
```

### DEV SIMP MULT `x`

Adjust the primary property of the current Slicing Mode.

For Transient, this will adjust Sensitivity.

For Beat, this will adjust Beat Division.

For Region, this will adjust Regions.

This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters), but because it applies to multiple properties of differing types, it's recommended that you primarily only use it for relative adjustments.


```
DEV SIMP MULT <
DEV SIMP MULT >
```

### DEV SIMP NUDGE < or >

Nudge the selected slice Backwards or Forwards when in Transient or Manual Slicing Mode.

```
DEV SIMP NUDGE <
DEV SIMP NUDGE >
```

### DEV SIMP PLAYMODE `x`

Toggle Playback Mode or set a particular Mode where `x` is the Mode to set.

```
DEV SIMP PLAYMODE
DEV SIMP PLAYMODE CLASSIC
DEV SIMP PLAYMODE 1-SHOT
DEV SIMP PLAYMODE SLICE
```

### DEV SIMP PSLICE

Toggle, turn on or turn off Pad Slicing. When on, Slices can be created by playing notes on a MIDI controller (starting at C1) while the Sample is playing back.

```
DEV SIMP PSLICE
DEV SIMP PSLICE ON
DEV SIMP PSLICE OFF
```

### DEV SIMP RESET

Reset all Slices back to their default positions when in Transient or Manual Slicing Mode.

### DEV SIMP RETRIG

Toggle, turn on or turn off Retrigger. 

```
DEV SIMP RETRIG
DEV SIMP RETRIG ON
DEV SIMP RETRIG OFF
```

### DEV SIMP REV

Reverse the loaded Sample.

### DEV SIMP SMODE `x`

Toggle Slicing Mode or set a particular Mode where `x` is the Mode to set.

```
DEV SIMP SMODE
DEV SIMP SMODE TRANSIENT
DEV SIMP SMODE BEAT
DEV SIMP SMODE REGION
DEV SIMP SMODE MANUAL
```

### DEV SIMP SPLAYMODE `x`

Toggle Slice Playback Mode or set a particular Mode where `x` is the Mode to set.

```
DEV SIMP SPLAYMODE
DEV SIMP SPLAYMODE MONO
DEV SIMP SPLAYMODE POLY
DEV SIMP SPLAYMODE THRU
```

### DEV SIMP START `x`

Adjust the Sample's Start Marker (in the range of 0 - 127). This is a
[Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
DEV SIMP START 4
DEV SIMP START >
```

### DEV SIMP TODR

Convert Simpler slices to a Drum Rack.

### DEV SIMP WARP

Toggle, turn on or turn off Warping.

```
DEV SIMP WARP
DEV SIMP WARP ON
DEV SIMP WARP OFF
```

### DEV SIMP WARP AS

Trigger Warp As.

### DEV SIMP WARPMODE `x`

Adjust the Sample's Warp Mode. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).
