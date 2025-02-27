# General Action Information

The following sections provide general information that applies to various ClyphX Pro Actions.

## Track-based actions

Track-based Actions, which include [Track Actions](/action-reference/track-actions) through [Clip Note Actions](/action-reference/clip-note-actions), are Actions that can be applied to Tracks and the objects they contain (such as Devices and Clips). If no Track is specified, these Actions will be applied to either the Track the [X-Clip](/core-concepts#x-clips) resides on or (in the case of other [X-Triggers](/core-concepts#x-triggers)) the selected Track. You can apply these Actions to other Tracks or to ranges of Tracks as described below.

## Applying Actions to Specific Objects and Ranges

At the topmost level, Track-based Actions can be applied to Tracks or ranges of Tracks. You'll specify the Track or range followed by a slash ( `/` ) before the Action name. For example:

`1/MUTE` 

_Toggle the Mute state of Track 1._

When applying Actions to the objects a Track contains, you'll specify the object or range enclosed in parentheses after the word `DEV`, `CH`, `PAD` or `CLIP`. For example:

`DEV(2) RND` 

_Randomize the parameters of the 2nd Device on the Track._

`CLIP(5) LOOP`

_Toggle the Loop state of the Clip on the 5th Scene on the Track._

In all cases, objects can be specified by their Track number, Device number (based on the Device's position on the Track), Device Chain number, Drum Pad number or the Clip Slot number of the Clip as shown in the previous examples. Objects can also be specified by their name enclosed in quotes. For example:

`"Vox"/DEV("EQ") CH(1) MUTE`

_Toggle the Mute state of the 1st Chain in the Device named `EQ` on the Track named `Vox`._

`"Bass"/CLIP("Verse") LOOP `

_Toggle the Loop state of the Clip named `Verse` on the Track named `Bass`._

When specifying names, Actions will be applied to the last object with the given name. When working with multiple objects that have the same name, you should use numbers instead of names in most cases. Also, Tracks that are auto-named by Live are not displayed correctly in Live (Live omits the hyphen).

For example, an auto-named Track that is displayed as `1 MIDI` is actually named `1-MIDI`. You need to
use the Track's actual name when accessing it by name in ClyphX Pro.

### Specifying objects with keywords

Objects can also be specified via keywords:

- `SEL` - applies to the selected object. In the case of Device and Drum Pad Actions, this cannot be
used in ranges
- `LAST` - applies to the last object
- `<` **and** `>` - applies to the previous or next object relative to the selected object. This is not supported
for Device or Drum Pad Actions 
- `ALL` - applies to all objects (all Tracks in the Set, all Devices/Clips on a Track, all Chains in a Rack or all visible Drum Rack Pads). This cannot be used in ranges.

When specifying [Tracks](/action-reference/track-actions), some additional keywords are available:

- `MST` - applies to the `Master` or `Main` track
- `A`-`L` - applies to Return Tracks `A` - `L`

For [Device Actions](/action-reference/device-actions), the `RACKS` keyword is available which applies to all of the Racks (including nested Racks) on a Track. This cannot be used in ranges.

For [Clip Actions](/action-reference/clip-actions), some additional keywords are available:

- `DETAIL` - applies to the Clip selected in Detail View and cannot be used in ranges. This is useful for applying Actions to Clips in Arrangement View.
- `SELF` - applies to the [X-Clip](/core-concepts#x-clips) that triggered the Action and cannot be used in ranges. This is really only useful for applying Actions to an X-Clip after it has stopped playing. For example:
`[] D : CLIP(SELF) COLOR 12`

Unless otherwise noted, object numbers, names and keywords can all be utilized when specifying ranges of objects to apply Actions to. Contiguous ranges (like `1-5`), broken ranges (like `1, 3, 5`) and mixed ranges (like `1-2, 5, 10-15`) are supported. Here are some examples:

`"My Track"/DEV(ALL) OFF`

_Turn off all Devices on the Track named `My Track`._

`1, 3, 5, "My Track", A-MST/MUTE`

_Toggle the Mute state of Tracks `1`, `3`, `5`, `My Track`
and `Return A` through the `Master Track`._

`>-5/CLIP(SEL-7) WARP`

_Toggle the Warp state of the Clip on the selected Scene through the Clip on the `7`th Scene on the Track to the right of the selected Track though Track `5`._

## Applying Actions to Nested Devices

All Actions that work with Devices can be applied to Devices that are not nested within Racks as covered in [Device Actions](/action-reference/device-actions). It's also possible to apply Actions to Devices nested within Racks by either specifying the Device's name or by using the following dotted notation.

### Single Devices

To apply Actions to a single Device nested within a Rack, specify the number (based on the Rack's position on the Track) or name of the Rack, then the number or name of the Chain and then the number( based on the Device's position on the Chain) or name of the nested Device. For example, this will apply to the 3rd Device on the 2nd Chain of the 1st Rack _(it's easier to comprehend this notation when read from right to left)_: 

`DEV(1.2.3)`

The `SEL` and `LAST` keywords are also supported. `LAST` applies to the last Rack, Chain or nested Device. `SEL` is a bit more complex and can only be used in specific cases. `SEL` can be used to specify the selected Rack on the Track providing the Rack is not nested. `SEL` can also be used to specify the selected Chain in a Rack. `SEL` cannot be used to specify the selected Device on a Chain since Chains have no notion of a selected Device.

Additionally, this notation can be extended as far as needed to access deeply nested Devices. For example, this will apply to the 7th Device on the 6th Chain of the 5th Rack on the 4th Chain of the 3nd Rack on the 2nd Chain of the 1st Rack: 

`DEV(1.2.3.4.5.6.7)`

### Multiple Devices

You can also apply Actions to multiple nested Devices by using the `ALL` keyword. For example, this will apply to all of the Devices on the 1st Chain of the Rack named `My Rack`:

`DEV("My Rack".1.ALL)`

This will apply to the 4th Device on all of the Chains of the 2nd Rack:

`DEV(2.ALL.4)`

This will apply to all of the Devices nested within the 1st Rack:

`DEV(ALL.ALL)`

As with Single Devices, this notation can be extended as far as needed to access deeply nested Devices. For example, this will apply to all of the Devices on the 1st Chain of the 2nd Rack on the 1st Chain of the 1st Rack:

`DEV(1.1.2.1.ALL)`

When applying Actions to all Chains, it is assumed that all Chains are identical to the 1st Chain. For that reason, in most cases, you shouldn't specify a Device name (`DEV(1.ALL."My Device"`) for example) unless all of the Chains contain `My Device` in the exact same position on each Chain.


## Adjustable Properties

All of the Adjustable Properties offer several control options via keywords.

### `x`

`x` is the property value/name to set as shown in Live.

```
IN "My Track"
GQ 1 BAR
```

### `<` or `>` 

Decrement or increment the property value by 1.

```
RQ < 
CLIP WARPMODE >
```

### `<X` or `>X` 

Decrement or increment the property value by `x`.

```
DEV PRESET <5
DEV DR SCROLL >4
```

## Continuous Parameters

#### Ramping parameters

All of the Continuous Parameters offer several control options via keywords.

The values of Continuous Parameters can also be ramped up or down over a number of milliseconds or in sync with Live's playback via the `RAMP` or `RAMPS` keywords respectively. After this keyword, you'll specify the ramp duration (in hundreds of milliseconds or Beats/Bars) and the keyword from above to use for setting the value at the end of the ramp. For examples

`VOL RAMP 8 *2` 

_Multiply the parameter value by 2 over 800 milliseconds_

`DEV P1 RAMPS 16 RESET` 

_Reset the parameter value over 16 Beats._

`SEND A RAMPS 16B RND`

_Randomize the parameter value over 16 Bars._

!!! note
    Chain Selectors, on/off switches and multi-option controls (like a filter type chooser) cannot be reset or randomized.

### `x`

`x` is the parameter value to set (in the range of 0 – 127). The value of some parameters can be set by the value's name. These names are listed in the [Device Parameter Name Reference Lesson](/setup/#documentation).

```
DEV CS 100
DEV "Filter Type" "Bandpass"
```

### `x%`

`x` is the parameter value to set in terms of a percentage (in the range of 0 – 100).

```
DEV "Frequency" 70.2%,
SEND A 50%
```

### `*x`

`x` is the value to multiply the parameter's value by.

```
VOL *0.5
```

### `<` or `>` 

Decrement or increment the property value by 1.

```
VOL <
PAN >
```

### `<X` or `>X` 

Decrement or increment the property value by `x`.

```
PAN <5
DEV B2 P1 >10
```

### ENABLE

Re-enable automation that has been overridden for the parameter. 

```
SEND C ENABLE
```

### RESET

Reset the parameter value to its default value. 

```
DEV P1 RESET
```

### RND

Randomize the parameter value.

```
SEND A RND
```

### RNDQ

Same as [RND](#rnd), but will quantize the randomization so that the
parameter's value will be a whole number.

```
SEND A RND
```

### RND`x`-`y`

Randomize the parameter value. The value produced will be in the range of `x`-`y` (where both `x` and `y` are in the range of 0 – 127) and will then be scaled to match the range of the given parameter.

```
VOL RND50-60
DEV P5 RND5-10
```

### TGL

Toggle the parameter's value between its minimum and maximum value.

```
DEV "Resonance" TGL
```

## Quasi Continuous Parameters

All of the Quasi Continuous Parameters offer the same control options as Continuous Parameters
(described above) with a few exceptions:

- Unless otherwise noted, when setting the value of a Quasi Continuous Parameter, you'll use the value shown in Live. For example, when setting Tempo value, you'll specify the value in BPMs (like `BPM 90.5`). Also, the value of a Quasi Continuous Parameter cannot be set based on percentage.
- Quasi Continuous Parameters can be randomized, but do not support custom random ranges.
- Quasi Continuous Parameters cannot be automated and so `ENABLE` does not apply to them.

