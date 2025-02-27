The following Actions allow you to control Live Set-wide properties and functions as well as access internal ClyphX Pro features.

## ADDAUDIO

Create an Audio Track to the right of the selected Track.

### ADDAUDIO `X`

Create an Audio Track where `x` is the Track number of the new Track.
Specify `-1` to create the Track at the end of the Track list.

```
ADDAUDIO 5
ADDAUDIO -1
```

## ADDMIDI

Create a MIDI Track to the right of the selected Track.

### ADDMIDI `X`

Create a MIDI Track where `x` is the Track number of the new Track.
Specify `-1` to create the Track at the end of the Track list.

```
ADDMIDI 10
ADDMIDI -1
```

## ADDRETURN

Create a Return Track at the end of the Return list.

## B2A

Back to Arrangement.

## BIND

### BIND `i` `x`

_For use with the optional [ClyphX Pro Bindings Accessory](/optional-accessories/#clyphx-pro-bindings)._

Bind the control named `i` to `x`.

```
BIND MY_BUTTON SELP
BIND MY_KNOB SEL/VOL
```

### BIND `i` `<x` or `>x` 

_For use with the optional [ClyphX Pro Bindings Accessory](/optional-accessories/#clyphx-pro-bindings)._

Bind the control named `i` to the Prev/Next parameter relative to the currently bound parameter. This only applies to Device parameters, so will have no effect on Mixer parameter bindings.

```
BIND MY_BUTTON <,
BIND MY_KNOB >
```

## BOUNDP `x`

_For use with the optional [ClyphX Pro Bindings Accessory](/optional-accessories/#clyphx-pro-bindings)._

Adjust the value of the last parameter that was adjusted via the Bindings Accessory.

This is a Continuous Parameter.

```
BOUNDP 100,
BOUNDP RND
```

## BPM `x`

Adjust Tempo. This is a Quasi Continuous parameter.

```
BPM 100, 
BPM 85.53, 
BPM >
```

## CAP

Trigger [Capture](https://help.ableton.com/hc/en-us/articles/360000776450-Capture-MIDI).

## DEBUG

Activate debugging mode, which causes ClyphX Pro to log events as they occur to assist in [Troubleshooting](/troubleshooting).

## DRAW

Toggle, turn on or turn off Draw Mode.

```
DRAW
DRAW ON
DRAW OFF
```

## DUMMY or D

This Action does nothing. This is intended for use with [PSEQ Action Lists](/core-concepts#sequential-action-lists) as well as LSEQ and Default with Stop X-Clips.

## FOLLOW

Toggle, turn on or turn off Follow.

```
FOLLOW
FOLLOW ON
FOLLOW OFF
```

## FULLVELO

Toggle, turn on or turn off Full Velocity. When on, notes sent from the controller selected as the Input of the ClyphX Pro Control Surface will have full velocity (127).

```
FULLVELO
FULLVELO ON
FULLVELO OFF
```

## GQ

Toggle Global Quantization value between None and the last value.

### GQ `x`

Adjust Global Quantization. This is an [Adjustable Property](/general-action-information/#adjustable-properties).

```
GQ NONE
GQ 8 BARS
GQ >
```

## GRV `x`

Adjust Global Groove Amount. This is a [Quasi Continuous Parameter](/general-action-information/#quasi-continuous-parameters).

## INSAUDIO or INSMIDI

Insert an Audio or MIDI Track to the right of the selected Track that will be armed and routed from the selected Track. This will not perform an insertion if the selected Track is not the correct type. For example, if the selected Track doesn't have Audio output, `INSAUDIO` will do nothing.

```
INSAUDIO
INSMIDI
```

## LOC `x`

`x` is the name of the Arrangement Locator to jump to.

```
LOC "Verse 1"
```

## LOC `<` or `>`

Jump to the Prev/Next Arrangement Locator.

```
LOC <
LOC >
```

## LOCLOOP `x`

`x` is the name of the Arrangement Locator to jump to. Also, the Arrangement Loop Start position will move to the position of this Locator.

```
LOCLOOP "Hook"
```

## LOOP

Toggle, turn on or turn off Arrangement Loop.

```
LOOP
LOOP ON
LOOP OFF
```

### LOOP *`x`

`x` is the value to multiply the Arrangement Loop Length by. 

```
LOOP *0.5
LOOP *2
```

### LOOP `<` or `>`

Move the Arrangement Loop Backward/Forward by its length.

```
LOOP <
LOOP >
```

### LOOP <`x` or >`x`

Move the Arrangement Loop Backward/Forward by `x` Beats (specify `B` for Bars).

```
LOOP <4
LOOP >16
LOOP >8B
```

### LOOP RESET

Reset Arrangement Loop Start position to 1.1.1.

### LOOP START `x`

`x` is the Arrangement Loop Start position to set in Bars.Beats.Sixteenths. Alternatively, you can specify the name of an Arrangement Locator to move the Arrangement Loop Start position to the position of the named Locator.

```
LOOP START 4.1.1
LOOP START 1.1.1
LOOP START "My Locator"
```

## METRO

Toggle, turn on or turn off Metronome. 

```
METRO
METRO ON
METRO OFF
```

## MSG `x`

`x` is the message to show in Live's Status Bar. By default, this will show the message in lower case. If you'd like capitalization to be preserved, use quotes.

```
MSG HELLO WORLD
MSG "Preserve Caps"
```

## OPEN `x`

x is the path to the file to open in its default application. When opening Sets, dialogs that come up upon closing the current Set will be managed.

```
OPEN "/Users/Stray/My File.txt"
OPEN "C:\My Live Set.als"
```

## OVER

Toggle, turn on or turn off Arrangement Overdub. 

```
OVER
OVER ON
OVER OFF
```

## PIN

Toggle, turn on or turn off Punch In. 

```
PIN
PIN ON
PIN OFF
```

## POUT

Toggle, turn on or turn off Punch Out.

```
PIN, PIN ON, PIN OFF
```

## PSEQ RESET

Reset all [PSEQ Action Lists](/core-concepts#sequential-action-lists) so that they start back at their beginning.

### PSEQ RESET `x`

`x` is the [Identifier](/core-concepts#identifiers) of the PSEQ Action List to reset. 

## REC

Toggle, turn on or turn off Arrangement Record. 

```
REC
REC ON
REC OFF
```

## REINIT

Reinitialize all [Macros](/core-cocncepts#macros) and [Variables](/core-concepts#variables) to their initial states. This will cause the related files to be re-read allowing you to modify the files, trigger this Action and have the changes to the files immediately be applied.

## RESTART

Restart Arrangement to Position 1.1.1.

## RQ

Adjust Record Quantization. This is an [Adjustable Property](/general-action-information/#adjustable-properties). The names of the available Quantization value are: 

- `NONE`
- `1/4`
- `1/8`
- `18T`
- `1/8+T`
- `1/16`
- `1/16T`
- `1/16+T`
- `1/32`

```
RQ NONE
RQ 1/4
RQ >
```

## RPT

!!! note
    The RPT Actions require that a controller be selected as the Input of the ClyphX Pro Control Surface and that its Track switch be turned on. When RPT is on, notes sent from the controller will produce a consistent stream of rhythmic notes at the specified rate. Additionally, the available Note Repeat rates are as follows: `OFF`, `1/4D`, `1/4`, `1/4T`, `1/8D`, `1/8`, `1/8T`, `1/16D`, `1/16`, `1/16T`, `1/32D`, `1/32`, `1/32T`, `1/64D`, `1/64`, `1/64T` (where 'D' stands for dotted and 'T' stands for triplet).

Toggle Note Repeat on/off.

### RPT `x`

`x` is the Note Repeat rate to set.

```
RPT OFF
RPT 1/4
RPT 1/32T
```

## RTRIG

Retrigger all Clips that are currently recording.

## SATM

Toggle, turn on or turn off Automation Arm. 

```
SATM
SATM ON
SATM OFF
```

## SATMR

Re-enable automation that has been overridden.

## SELP `x`

Adjust the value of the selected parameter. This is a [Continuous Parameter](/general-action-information/#continuous-parameters).

```
SELP 100
SELP >
```

## SETCONT

Continue playback from the last stop point. This is only useful when triggered from an [X-Control](/core-concepts#x-controls) or [X-OSC](/core-concepts#x-osc).

## SETJUMP `x`

`x` is the Arrangement Playback Position to jump to in
Bars.Beats.Sixteenths.

```
SETJUMP 8.1.1
```

### SETJUMP `<` or `>`

Jump the Arrangement's Playback Position Backward/Forward by 1 Beat.

```
SETJUMP <, SETJUMP >
```

### SETJUMP `<x` or `>x`

Jump the Arrangement's Playback Position Backward/Forward by `x` Beats (specify `B` for Bars).

## SETLOC

Add a Locator at the current Arrangement position or, if a Locator already exists at the position, delete the Locator.

## SETPLAY

Toggle, turn on or turn off playback. 

```
SETPLAY
SETPLAY ON
SETPLAY OFF
```

## SETPLAYSEL

Play the selection in Arrangement View if there is one.

## SETSTOP

Stop playback. This will actually toggle playback state, so it can be used to start/stop playback when triggered from an [X-Control](/core-concepts#x-controls) or [X-OSC](/core-concepts#x-osc).

## SIG `x`/`y`

`x` is the Time Signature Numerator and `y` is the Denominator. 

```
SIG 4/4
SIG 6/8
```

## SREC

Toggle, turn on or turn off Session Record.

```
SREC
SREC ON
SREC OFF
```

## SRECFIX `x`

Trigger fixed-length Session Record on all armed Tracks where x is the length to record in Bars. Note, however, that Session Recording is always quantized according to Global Quantization and so your Global Quantization value needs to be less than or equal to the number of Bars to record for. For example, to record for 4 Bars, Global Quantization would need to be 4 Bars or less.

```
SRECFIX 4
SRECFIX 16
SRECFIX 0.5
```

## STOPALL

Stop all Clips

### STOPALL NQ

Stop all Clips immediately (not quantized).

## SWING `x`

Adjust the Swing amount (in the range of 0 - 100) to apply to Note Repeat(RPT). This is a [Quasi Continuous Parameter](/general-action-information/#quasi-continuous-parameters).

## TAPBPM

Tap Tempo.

## TFOLLOW

Toggle, turn on or turn off Tempo Follower. 

```
TFOLLOW
TFOLLOW ON
TFOLLOW OFF
```

## TIME

Display the amount of time spent (in the format of hours:minutes:seconds) in Live's Status Bar since the current Live Set was loaded.

## UNBIND

_For use with the optional [ClyphX Pro Bindings Accessory](/optional-accessories/#clyphx-pro-bindings)._

Unbind all bound controls (leaving them with no binding).

## UNDO or REDO 

Undo or Redo.

```
UNDO
REDO
```

## WAIT `x`

