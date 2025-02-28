---
weight: 6
search:
  boost: 2
---

# Device Actions

The following Actions are [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to control parameters, properties and functions of Devices. By default, these Actions will apply to the Device selected on the Track. If no Device is selected, these Actions will apply to the first Device on the Track. You can apply these Actions to other Devices or to ranges of Devices [as described here](/manual/general-action-information/#applying-actions-to-specific-objects-and-ranges). However, unless a Device's name is specified, these will strictly apply to Devices that are not nested within Racks. You can apply these Actions to Devices that are nested within Racks by specifying the Device's name or [as described here](/manual/general-action-information/#applying-actions-to-nested-devices).

!!! note "Notes"
    - If the Device you're looking to control is not a native Live Device, Actions will only apply to the configured parameters of the Device.

    - When it comes to controlling parameters, if the parameter is mapped to a Macro, the parameter cannot be controlled. You should control the Macro instead.

---

### DEV

Toggle, turn on or turn off Device On/Off switch.

```
DEV
DEV ON
DEV OFF
```

### DEV `x`

x is the name of the Device parameter to adjust. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters). [^1]

```
DEV "Frequency" RND
DEV "My Parameter" 100
```

### DEV ADDMACRO or DEV REMMACRO

Add or remove a Macro from a Rack. 

```
DEV ADDMACRO
DEV REMMACRO
```

### DEV B`n` P`p` `x`

Adjust Device Bank parameter 1 - 8 where `n` in the number of the bank and `p` in the number of the parameter within the bank to adjust. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters). [^1]

```
DEV B1 P1 50
DEV B2 P1 >
```

### DEV CS `x`

Adjust Device Chain Selector value. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters). [^1]

```
DEV CS 50
DEV CS >
```

### DEV CSEL `x`

`x` is the number or name of the Device Chain to select. 

```
DEV CSEL 10
DEV CSEL "My Chain"
```

### DEV CSEL < or >

Navigate to the previous/next Device Chain. 

```
DEV CSEL <
DEV CSEL >
```

### DEV DEL 

Delete the Device. Only top-level Devices (Devices that aren't nested within Racks) can be Deleted.

### DEV DR SCROLL `x`

Adjust the Drum Rack's Selector. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
DEV DR SCROLL 5
DEV DR SCROLL >
```

### DEV FOLD

Toggle, turn on or turn off Device Fold.

```
DEV FOLD
DEV FOLD ON
DEV FOLD OFF
```

### DEV P`p` `x`

Adjust Device Best-of-Bank parameter 1 - 8 where p in the number of the parameter to adjust. This is a [Continuous Parameter](/manual/general-action-information#continuous-parameters). [^1]

### DEV PRESET `x`

Adjust the preset selection of the Plug-in. Preset selection is only possible if the Plug-in's preset list is exposed (visible in the Plug-in's container in Live). This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
DEV PRESET >
DEV PRESET "Lead Synth"
```

### DEV RESET

Reset Device parameters. [^2]

### DEV RND

Randomize Device parameters. [^2]

### DEV SEL

Select the Device and bring the Track it is on into view. If the Device is nested in a Rack and is hidden, it cannot be selected.

### DEV SET

This Action is only accessible to [X-Clips](/manual/core-concepts/#x-clips) and [X-Scenes](/manual/core-concepts/#x-scenes) and should not be combined with other Actions. This will capture the values of the 16 Macros in a Rack and add them to the X-Clip/X-Scenes's name, thus creating a `DEV SET x` Action.

Once the `DEV SET x` Action has been created, you can then combine it with other actions if you like.

### DEV SET `x`

`x` is a space-separated list of between 1 and 16 [Continuous Parameter](/manual/general-action-information#continuous-parameters) values/keywords (except for [RAMP](/manual/general-action-information/#ramping-parameters)) that will set the values of the Macros in a Rack at once. You can alternatively specify `CUR` to leave a Macro's value
unchanged.

```
DEV SET 0 10 20 30 40 50 60 70
DEV SET 1 RND 3 > < 127 CUR <5
```

### DEV SHOWCH

Toggle, turn on or turn off the visibility of Devices on a Rack's Chains.

```
DEV SHOWCH
DEV SHOWCH ON, DEV SHOWCH OFF
```

### DEV VAR `x`

Select a Macro Variation. This is an [Adjustable Property](/manual/general-action-information/#adjustable-properties).

```
DEV VAR 5
DEV VAR >
```

### DEV VARDEL

Delete the selected Macro Variation.

### DEV VARRECALL

Recall the selected Macro Variation.

### DEV VARLRECALL

Recall the Macro Variation that was recalled most recently.

### DEV VARSTORE

Store a new Macro Variation



[^1]: See the Device Parameter Reference and/or the Device Parameter Name Reference section of the [ClyphX Pro Live Lessons](/manual/setup/#documentation) for more information on the parameters of Live's built-in Devices. In the case of non-native Devices, the parameter names you should use are defined in the Device itself. For example, for a Plug-in Device, you can find its parameter names by clicking the Unfold Device Parameters button for the Plug-in.

[^2]: The `DEV RND` and `DEV RST` Actions will not affect Chain Selectors, on/off switches or multi-option controls (like a filter type chooser).
