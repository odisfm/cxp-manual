---
weight: 16
---

# Clip Envelope Capture Action

This Action creates Envelopes in the Clip for the current settings of the associated Track’s mixer and/or Devices. This is a [Track-based Action](/manual/general-action-information/#track-based-actions) and can be applied to Clips in the same way as [Clip Actions](/action-reference/clip-actions). 

The default Action name is `CLIP ENVCAP`. This will apply to the Volume, Pan and Sends settings of the associated Track. This also applies to the settings of the first Device on the associated Track.

You can modify the settings that the Action will capture by using optional words/numbers (Modifiers) in the Action Name.

___

### DEV(`x`)

`x` specifies the Device(s) whose settings should be captured. You can specify Devices as covered in [Device Actions](/action-reference/device-actions).

```
CLIP ENVCAP DEV(ALL)
CLIP ENVCAP DEV("My Cool Device")
```

### MIX

Capture the Volume, Pan and Sends settings of the Track.

### MIX-

Same as MIX, but without Sends.

### MIXS

Store the Sends settings of the Track.

!!! warning
    Multiple Modifiers can be used although you should not use more than one of the Mix Modifiers. For example, to capture the settings of all of the Devices on a Track as well as settings stored by MIX-: `CLIP ENVCAP DEV(ALL.ALL) MIX-`

!!! note
    - When creating Envelopes for a large number of parameters, Live’s GUI may momentarily freeze.
    - The mixer settings of the Chains of Racks will be captured along with the Rack itself.


