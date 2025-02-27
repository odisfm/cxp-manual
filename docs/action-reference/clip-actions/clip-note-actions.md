---
weight: 17
---

# Clip Note Actions

The following Actions are all [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to manipulate the Notes within a Clip in various ways. These Actions can be applied to Clips in the same way as [Clip Actions](/action-reference/clip-actions/).

___

### Details

By default, these Actions will apply to all the Notes in a MIDI Clip that fall within the Loop Start/End markers (if Loop is on) or the Start/End markers (if Loop is off). To operate only on Notes selected within the Clip, specify `SEL` enclosed in parentheses after the word `NOTES`. For example:

`CLIP NOTES(SEL) SCRP`

To operate just on a particular Pitch (or a range of Pitches), specify the name (or number) of the Pitch(or range) enclosed in parentheses after the word `NOTES`. For example:

```
CLIP NOTES(C#3) REV
CLIP NOTES(F4-F#5) VELO <<
CLIP NOTES(60) NUDGE >
```

To operate on Notes that fall on a particular time position (or a range of time positions) in the Clip, specify the position (or range) and use `@` as a prefix. For example:

```
CLIP NOTES @1.1.1 GATE >
CLIP NOTES @2.1.4-5.1.1 SPLIT
```

You can specify both a Pitch (or Pitch range) and a position (or position range) to operate on. For example:

`CLIP NOTES(C3-F3) @2.1.1 DEL`

---

### CLIP NOTES

Toggle, turn on or turn off the mute status of Notes.

```
CLIP NOTES
CLIP NOTES ON
CLIP NOTES OFF
```

### CLIP NOTES CMB

Combine each set of two consecutive Notes into a single Note.

### CLIP NOTES COMP

Compress the duration of Notes.

### CLIP NOTES DEL

Delete Notes.

### CLIP NOTES EXP

Expand the duration of Notes.

### CLIP NOTES GATE < or >

Decrement/increment the length of Notes by one 128th Note. 

```
CLIP NOTES GATE <
CLIP NOTES GATE >
```

### CLIP NOTES GATE <`x` or >`x`

Decrement/increment the length of Notes by `x` 128th Notes.

```
CLIP NOTES GATE <4
CLIP NOTES GATE >8
```

### CLIP NOTES INV

Invert the pitches of Notes.

### CLIP NOTES NUDGE `<` or `>`

Nudge Notes Backward/Forward by one 128th Note.

```
CLIP NOTES NUDGE <
CLIP NOTES NUDGE >
```

### CLIP NOTES NUDGE <`x` or >`x`

Nudge Notes Backward/Forward by `x` 128th Notes.

```
CLIP NOTES NUDGE <4
CLIP NOTES NUDGE >8
```

### CLIP NOTES REV

Reverse the position of Notes.

### CLIP NOTES SCRP

Scramble the position of Notes while maintaining pitches.

### CLIP NOTES SEMI < or >

Transpose Notes up or down by 1 semitone.

```
CLIP NOTES SEMI >
CLIP NOTES SEMI <
```

### CLIP NOTES SEMI <`x` or >`x`

Transpose Notes up or down by `x` semitones.

```
CLIP NOTES SEMI >12
CLIP NOTES SEMI <4
```

### CLIP NOTES SPLIT

Split each Note into two equally sized Notes.

### CLIP NOTES VELO `x`

`x` is the Note velocity to set.

```
CLIP NOTES VELO 64
CLIP NOTES VELO 127
```

### CLIP NOTES VELO < or >

Decrement/increment the velocity of Notes by increment of 1.

```
CLIP NOTES VELO <
CLIP NOTES VELO >
```

### CLIP NOTES VELO <`x` or >`x`

Decrement/increment the velocity of Notes by increment of `x`.

```
CLIP NOTES VELO <5
CLIP NOTES VELO >10
```

### CLIP NOTES VELO << or >>

Apply a decrescendo (descending velocities) or a crescendo (ascending velocities) to Notes.

```
CLIP NOTES VELO <<
CLIP NOTES VELO >>
```

### CLIP NOTES VELO RND

Randomize the velocity of Notes in the range of 64 - 127.

### CLIP NOTES VELO RND`x`-`y`

Randomize the velocity of Notes in the range of `x`-`y` (where both `x` and `y` are in the range of 1 - 127).

```
CLIP NOTES VELO RND1-32
CLIP NOTES VELO RND32-127
```