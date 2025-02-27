---
weight: 8
---

# Device Chain Actions

The following Actions are [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to control parameters, properties and functions of Device Chains as well as Drum Rack Pads. The Device to apply these Actions to can be specified in the same way as described in [Device Actions](/action-reference/device-actions). By default, these Actions will apply to the Chain that is selected within the Device. You can apply these Actions to other Chains or to ranges of Chains [as described here](/manual/general-action-information/#applying-actions-to-specific-objects-and-ranges).

!!! note
    If the Chain parameter you're looking to control is mapped to a Macro, the parameter cannot be controlled. You should control the Macro instead.

___


### DEV CH CHOKE `x`

Adjust Drum Rack Chain Choke Group. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
DEV CH CHOKE 5
DEV CH CHOKE >
```

### DEV CH COLOR `x`

`x` is the index of the Color (in the range of 1 - 70) to set the Chain to. 

```
DEV CH COLOR 5
DEV CH COLOR 43
```

### DEV CH COLOR < or >

Select the previous/next Color for the Chain.

```
DEV CH COLOR <
DEV CH COLOR >
```

### DEV CH MUTE

Toggle, turn on or turn off Chain Mute.

```
DEV CH MUTE
DEV CH MUTE ON
DEV CH MUTE OFF
```

### DEV CH NOTE `x`

Adjust Drum Rack Chain Out Note (in the range of 0 - 127) allowing for
transposition. This is a [Quasi Continuous Parameter](manual/general-action-information/#quasi-continuous-parameters).

```
DEV CH NOTE 60,
DEV CH NOTE >
```

### DEV CH PAN x 

Adjust Chain Pan. This is a [Continuous Parameter](/manual/general-action-information/#continuous-parameters).

```
DEV CH PAN 100
DEV CH PAN >
```

### DEV CH SEND `ltr` `x` 

`ltr` is the letter of the Chain Send to adjust. Specify `ALL` to adjust all Chain Sends. This is a [Continuous Parameter](/manual/general-action-information/#continuous-parameters).

### DEV CH SOLO 

Toggle, turn on or turn off Chain Solo. 

```
DEV CH SOLO
DEV CH SOLO ON
DEV CH SOLO OFF
```

### DEV CH VOL `x`

Adjust Chain Volume. This is a [Continuous Parameter](/manual/general-action-information/#continuous-parameters).

```
DEV CH VOL 100
DEV CH VOL
```
