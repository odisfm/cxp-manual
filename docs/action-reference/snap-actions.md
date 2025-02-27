---
weight: 10
---

# Snap Actions

The following Actions are [Track-based Actions](/manual/general-action-information/#track-based-actions) that allow you to store and recall Snapshots (Snaps) of Track and Device settings. Unlike other Actions, when using these Actions in an Action List, the Action List must be preceded by a unique [Identifier](/manual/core-concepts/#identifiers) (even in the case of [X-Controls](/manual/core-concepts/#x-controls) and [X-OSCs](/manual/core-concepts/#x-osc), which normally don't require any sort of Identifier). The Identifier is used as the unique name for the Snap. Additionally, Snap Actions should always be the first (or only) Action in an Action List.

---

### RECALL

Recall the settings stored in a Snap immediately.

### RECALL RAMP `x`

Recall the settings stored in a Snap with ramping where `x` is the ramp duration in hundreds of milliseconds.

```
RECALL RAMP 5
RECALL RAMP 20
```

### RECALL RAMPS `x`

Recall the settings stored in a Snap with ramping synced to Live's playback where `x` is the ramp duration in Beats (specify **B** for Bars)

### SNAP

Store a Snap.

### SNAPDEL `x`

Delete the Snap named `x`.

```
SNAPDEL MY SNAP
```

### SNAPDELALL

Delete all Snaps stored within the Set. [^1]

### SNAPSHOW

Create a MIDI Track at the end of the Track list that contains an X-Clip for each Snap stored within the Set. [^1]

[^1]: These Actions are only usable with Snaps stored with ClyphX Pro v1.0.4 or later.

## Details

By default, the [SNAP](#snap) Action will store the Volume, Pan and Send settings of the Track as well as the settings of the first Device on the Track. It's possible to modify the settings that will be stored as we'll see shortly.

The [RECALL](#recall) Action will recall the Snap associated with the Identifier used when storing the Snap. This makes it possible to recall a Snap from multiple different [X-Triggers](/manual/core-concepts/#x-triggers). Each X-Trigger simply has to include the Identifier of the Snap. It's also possible to recall Snaps with morphing using the [Macrobat](/manual/core-concepts) Snap or Snap Alt Rack.

When the `SNAP` Action is triggered from an X-Clip or [X-Scene](/manual/core-concepts/#x-scenes), the name of the X-Clip/X-Scene will be updated such that the `SNAP` Action will be removed and replaced by the `RECALL` Action. This allows you to store and then recall Snaps without having to change anything in your X-Clip/X-Scene. You can achieve the same effect with X-Controls and X-OSCs [as described here](/manual/addendum/). Unfortunately, this is not possible with [X-Cues](/manual/core-concepts/#x-cues). For that reason, it's recommended that you only use X-Cues for recalling (not storing) Snaps.

### Snap Action Modifiers

You can use the following Modifiers with the [SNAP](#snap) Action to modify the settings that will be stored.


#### DEV(`x`)

`x` specifies the Device(s) whose settings should be stored. You can specify Devices as covered in [Device Actions](/action-reference/device-actions).

```
SNAP DEV(ALL)
SNAP DEV("My Cool Device")
```

#### DEV-

Do not store the settings of any Devices. Unless this is used, the settings of the first Device on the Track (at the very least) will be stored.

#### MIX

Store the Volume, Pan and Sends settings of the Track.


#### MIX+

Same as MIX, but also store Mute, Solo and Crossfade settings of the Track. You can opt to also store Arm and Monitoring status in [Preferences.txt](/manual/core-concepts/#settings-foldersfiles).

#### MIX-

Same as MIX+, but without Sends.

#### MIXS

Store the Sends settings of the Track.

#### PLAY

Store the playing status of the Track. This does not apply to Group Tracks, Return Tracks or the Master Track.

!!! note
    Multiple Modifiers can be used although you should not use more than one of the Mix Modifiers. For example, to store all of the Devices on Tracks 1-3 as well as settings stored by MIX+:

    `[MY SNAP] 1-3/SNAP DEV(ALL.ALL) MIX+`

### Snap Action General Notes

- A Snap recalled from an X-Clip can alternatively use the recall keyword enclosed in brackets at the end of the name of the Track the X-Clip is on. For example, you could name the Track something like this:

    `My Track [RAMPS 10]`
    
    That would cause all Snaps recalled from the Track to be recalled with the specified smoothing or(in the case of the RACK recall keyword) to be sent to the Macrobat Snap Alt Rack. However, any X-Clip on the Track that contains its own recall keyword will override the recall keyword specified in the Track name.

- A special reserved [Identifier](/manual/core-concepts#identifiers) (`LAST_SNAP`) can be used with the [RECALL](#recall) Action to recall the last Snap that was stored or recalled. This would allow you to recall Snaps stored/recalled via X-Clips from a single [X-Control](/manual/core-concepts#x-controls) (or other [X-Trigger](/manual/core-concepts#x-triggers)). Or, you could have several X-Triggers that all used the `LAST_SNAP` Identifier with each having a different recall keyword to allow Snaps to be recalled in different ways.

- Snaps are stored within your Live Set. After storing the Snap, the Live Set will be marked as changed so that you'll be prompted to save the Set if you try to close it after storing a Snap and before you've saved the Set.

- Snaps are stored based on the Identifier of the Action List containing them. You can overwrite a Snap by storing a new Snap using the Identifier associated with the Snap to overwrite.

- It may take a few moments to entirely recall Snaps of large numbers of Tracks and/or Devices.

- If you’re attempting to take a Snap that would exceed the Snapshot Parameter Limit specified in [Preferences.txt](/manual/core-concepts/#settings-foldersfiles), an error message will be shown in Live's status bar.

### Snap Action Settings Notes

- The settings for each Track are stored by the name of the Track. This allows you to add/remove/re- arrange Tracks without affecting your ability to recall Snaps you’ve stored. However, if multiple Tracks have the same name, only the first of these will apply in Snaps.

- The settings for each Device are stored by the Device's position on the Track. If Devices are added/removed/re-arranged, this may affect your ability to recall Snaps you've stored.

- Snaps store all of the exposed parameters of a Device. If the number of exposed parameters changes, which can occur with some of Live's native Devices when certain parts of the Device are turned on/off and can also occur with Plug-ins, this may affect your ability to recall Snaps you've stored.

- The mixer settings of the Chains of Racks will be stored along with the Rack itself.
