---
weight: 13
---

# Clip Loop Actions

The following Actions are all [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to manipulate the Loop of a Clip in various ways. These Actions can be applied to Clips in the same way as [Clip Actions](/action-reference/clip-actions).

---

### CLIP LOOP

Toggle, turn on or turn off Clip Loop. 

```
CLIP LOOP
CLIP LOOP ON
CLIP LOOP OFF
```

### CLIP LOOP `x`

`x` is the Loop Length to set in Beats (specify `B` for Bars). If the Clip is playing, this will move the start of the Loop to the current Playback Position.

```
CLIP LOOP 1
CLIP LOOP 5
CLIP LOOP 1B
CLIP LOOP 2B
```

### CLIP LOOP *`x`

`x` is the value to multiply the Loop Length by. 

```
CLIP LOOP *0.5
CLIP LOOP *2
```

### CLIP LOOP < or >

Move the Clip Loop backward/forward by its length. 

```
CLIP LOOP <
CLIP LOOP >
```

### CLIP LOOP <`x` or >`x`

Move the Clip Loop Backward/Forward by `x` Beats (specify `B` for
Bars).

```
CLIP LOOP <4
CLIP LOOP >16B
```

### CLIP LOOP END `x`

`x` is the Clip Loop End (or Clip End if Loop is off) to set in Bars.Beats.Sixteenths (for Clips that are Warped) or absolute beat time.

```
CLIP LOOP END 1.4.1
CLIP LOOP END 16
```

### CLIP LOOP END < or >

Decrement/increment the Clip Loop End (or Clip End if Loop is off) by 1 Beat. 

```
CLIP LOOP END <
CLIP LOOP END >
```

### CLIP LOOP END <`x` or >`x` 

Decrement/increment the Clip Loop End (or Clip End if Loop is off) by `x` Beats (specify `B` for Bars).

### CLIP LOOP RESET 

Reset Clip Loop Start to 1.1.1 and Clip Loop End to Clip End Marker.

### CLIP LOOP SHOW 

Zoom in or out to show the Clip's entire Loop. This will do nothing if the Clip isn't visible or its Loop is off.

### CLIP LOOP START `x`

Adjust Clip Loop Start (or Clip Start if Loop is off) position. This is a [Quasi Continuous Parameter](/manual/general-action-information/#quasi-continuous-parameters).

```
CLIP LOOP START 1.4.2
CLIP LOOP START 4
CLIP LOOP START >
```

### CLIP LOOP START <`x` or >`x`

Decrement/increment the Clip Loop Start (or Clip Start if Loop is off) by `x` Beats (specify `B` for Bars).

```
CLIP LOOP START <2
CLIP LOOP START >4B
```
