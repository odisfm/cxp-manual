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

_For use with the optional ClyphX Pro Bindings Accessory._

Bind the control named `i` to `x`.

```
BIND MY_BUTTON SELP
BIND MY_KNOB SEL/VOL
```

### BIND `i` `<x` or `>x` 

_For use with the optional ClyphX Pro Bindings Accessory_ 

Bind the control named `i` to the Prev/Next parameter relative to the currently bound parameter. This only applies to Device parameters, so will have no effect on Mixer parameter bindings.

```
BIND MY_BUTTON <,
BIND MY_KNOB >
```

## BOUNDP `x`

_For use with the optional ClyphX Pro Bindings Accessory_ 

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
