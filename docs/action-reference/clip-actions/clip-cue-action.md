---
weight: 14
---

# Clip Cue Action

This Action sets the Cue point (position to play from) of the Clip. Upon triggering an [X-Trigger](manual/core-concepts/#x-triggers) with a Clip Cue Action, the specified Clip’s Start and Loop Start (if Loop is on) will move to the specified Cue point. This is a [Track-based Action](/manual/general-action-information/#track-based-actions) and can be applied to Clips in the same way as [Clip Actions](/action-reference/clip-actions).


!!! warning
    This Action will not work on Audio Clips that aren’t Warped and will not work correctly with a Global or Launch Quantization of `None`.

___

### CLIP CUE `x`

`x` is the position of the Cue in Bars.Beat.Sixteenths. 

```
CLIP CUE 1.2.1
CLIP CUE 4.1.1
```

### CLIP CUE < or >

Move the Cue point backward/forward by 1 Beat. 

```
CLIP CUE <
CLIP CUE >
```

### CLIP CUE <`x` or >`x`

Move the Cue point backward/forward by `x` Beats (specify `B` for Bars). 

```
CLIP CUE <2
CLIP CUE >4B
```