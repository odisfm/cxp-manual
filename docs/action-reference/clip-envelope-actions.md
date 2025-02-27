---
weight: 15
---

# Clip Envelope Actions

The following Actions are all [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to manipulate the Envelopes of a Clip in various ways. These Actions can be applied to Clips in the same way as [Clip Actions](/action-reference/clip-actions).

### CLIP ENVCLR

Clear all parameter Envelopes from the Clip.

### CLIP ENVCLR `x`

`x` is the parameter associated with the Envelope to clear from the
Clip.

```
CLIP ENVCLR VOL
CLIP ENVCLR DEV B1 P6
```

### CLIP ENVCLRD DEV(`x`)

`x` is the Device(s) whose parameter Envelopes should be cleared from the Clip. You can specify Devices as covered in [Device Actions](/action-reference/device-actions).

```
CLIP ENVCLRD DEV(SEL)
CLIP ENVCLRD DEV(2-4)
```

### CLIP ENVHIDE 

Hide the Clip's Envelope view. This actually applies to all Clips.

### CLIP ENVINS `x`

`x` is the parameter to insert a single point Envelope for in the Clip. This will first clear the parameter's Envelope if one exists.

```
CLIP ENVINS VOL
CLIP ENVINS SEL
```

### CLIP ENVSHOW 

Show the Clip's Envelope view. This actually applies to all Clips.

### CLIP ENVSHOW `x`

`x` is the parameter associated with the Envelope to show in Envelope view.

```
CLIP ENVSHOW VOL
CLIP ENVSHOW DEV B1 P6
CLIP ENVSHOW SEL
```

## Specifying parameters

To specify the parameter to insert an Envelope for, you can use the following:

- `VOL` – Track Volume
- `PAN` – Track Pan
- `PANL` – Track Left Split Stereo Pan
- `PANR` – Track Right Split Stereo Pan
- `MUTE` – Track Mute
- `SEND ltr` – Track Send where `ltr` is the letter of the Send (such as SEND C)
- `SEL` – The last parameter on the Track that was clicked on with your mouse.
- `BOUND` – _For use with the optional [ClyphX Pro Bindings Accessory](/manual/optional-accessories/#clyphx-pro-bindings)._ The last parameter that was adjusted via the Bindings Accessory.

You can also insert an Envelope for the parameter of a Device. You'll specify the Device containing the parameter as covered in Device Actions (`DEV(1)` for example). Then, to specify the parameter to insert an Envelope for, you'll specify the parameter's name or `DEV Bn Pp` (`DEV B2 P8` for example) or `DEV Pp` (`DEV P5` for example), all of which work in the same way as they do in Device Actions.