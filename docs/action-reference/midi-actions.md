---
weight: 4
---

# MIDI Actions

The following Actions allow you to send MIDI messages to the MIDI port selected as the Output of the ClyphX Pro Control Surface. They can optionally send MIDI messages to the MIDI port selected as the Output of an [XT Script](/manual/core-concepts#xt-scripts). To accomplish the latter, you'll specify the letter of the XT Script after the word MIDI. For example, to send a MIDI message to `ClyphX_Pro_XTB`, you'd use something like `MIDIB 176 1 127`. 

In all cases, the values used in these Actions should be entered in decimal (as opposed to hexadecimal).

---

### MIDI `x`

`x` is the MIDI message (of any type/length) to send.

```
MIDI 192 6
MIDI 240 1 2 3 4 247 # sysex message
```

### MIDI CC `x` `y` `z`

Send a MIDI Control Change message where `x` is the Channel (in the range of 1 - 16), `y` is the Control number (in the range of 0 - 127) and `z` is the Value (in the range of 0 - 127).

```
MIDI CC 1 0 127
MIDI CC 16 10 127
```

### MIDI NOTE `x` `y` `z`

Send a MIDI Note message where `x` is the Channel (in the range of 1 - 16),`y` is the Note number (in the range of 0 - 127) and `z` is the Velocity (in the range of 0 - 127). This will send a Note message with virtually no length.

```
MIDI NOTE 1 0 127
MIDI NOTE 16 10 127
```

### MIDI PC `x` `y`

Send a MIDI Program Change message where `x` is the Channel (in the range of 1 - 16) and `y` is the Value (in the range of 0 - 127).

```
MIDI PC 1 0
MIDI PC 16 10
```

## Routing options

The MIDI data that these Actions send can be used in a variety of ways via several routing options:

### Option A

_This is the only option usable with SysEx data in Live 9_

MIDI data to external MIDI device. In order to accomplish this, select the external MIDI device as the Output of the ClyphX Pro Control Surface or XT Script.

!!! note
    The next two options require a loopback device such as loopMIDI (Windows) or IAC (macOS, built-in).

### Option B :material-check-circle:
_This is the recommended option, but is not compatible with SysEx data in Live 9_

:material-done:

MIDI data to loopback device, re-routed back into Live as Track data. This option allows the MIDI data to be sent into MIDI Tracks in Live. From there, the data can be routed via the MIDI Track’s output routing and/or recorded.

In order to accomplish this, select the loopback device as the **Output** of the ClyphX Pro Control Surface or XT Script and turn the `Track` switch on for the loopback device’s input.

For any MIDI Tracks you wish to use this with, leave the Track’s input set to `All Ins` or choose the loopback device as the input, leave the Track’s input channel set to `All Channels` and Arm the Track or set its Monitor to `In`.

### Option C

MIDI data to loopback device, re-routed back into Live as Remote data. This option allows the MIDI data to be sent back into Live as Remote data (for MIDI mapping parameters).

In order to accomplish this, select the loopback device as the **Output** of the ClyphX Pro Control Surface
or XT Script and turn the `Remote` switch on for the loopback device’s input.


