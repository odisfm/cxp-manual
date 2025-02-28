---
weight: 7
---

# Macrobat

Macrobat is a component of ClyphX Pro that adds additional functionality to Ableton Live Racks while maintaining the default functionality of Racks. Racks that access this additional functionality are referred to as _Macrobat Racks_. Unless otherwise noted, any Rack can be turned into a Macrobat Rack
and Macrobat Racks can exist on any Track in your Live Set.

To turn a Rack into a Macrobat Rack, you'll need to specify a special name for the Rack and, in most cases, the Rack's Macros. These special names are **not** case sensitive unless they are enclosed in quotes, can exist anywhere within the Rack's/Macro's name and need to be enclosed in square brackets. For example:

`[TRACK]`

!!! Note
    - If the Macro or on/off switch of a Macrobat Rack is controlled by another Macro or otherwise disabled (such as when it's controlled by certain M4L devices), the Macro or on/off switch will not be able to access Macrobat functionality. 

    - ClyphX Pro Actions that apply to all of the Macros of a Rack (such as [DEV RND](/action-reference/device-actions#dev-rnd)) cannot be applied to Macrobat Racks aside from the MIDI Rack.

## Macrobat Rack Types

The following sections cover the types of Macrobat Racks that are available and the special names you'll need to use to access their functionality.

### Chain Mix Racks

The Chain Mix Racks are a group of three Macrobat Rack that allow you to control mixer parameters of the Chains of a Rack on the Track they are on. These Racks will operate upon the first Rack (that is not a MIDI Effects Rack or another Macrobat Rack) found on the Track.

#### Rack Names

`[CHAIN VOL]`

This Chain Mix Rack will control Chain Volumes.

`[CHAIN PAN]`

This Chain Mix Rack will control Chain Pannings

`[CHAIN SEND X]`

This Chain Mix Rack will control Chain Send Levels where X is the letter of the
Send to control.

#### Macro Names

The Macro names can either be the name of the Chain enclosed in quotes(`[“My Chain”]` for example) or the number of the Chain (`[5]` for example) to control.

### Selected Chain Rack

This Macrobat Rack allows you to control parameters of the selected Chain of a Rack on the Track it is on. This Rack will operate upon the first Rack (that is not a MIDI Effects Rack or another Macrobat Rack) found on the Track.

#### Rack Name: `[SEL CHAIN]`

#### Macro Names

- **[VOL]** — The Macro will control the Chain's Volume.
- **[VOL 0DB]** — The Macro will control the Chain's Volume, but with a limited range of -inf – 0db.
- **[PAN]** — The Macro will control the Chain's Panning.
- **[SEND X]** — The Macro will control one of the Chain's Send levels where X is the letter of the Send to control.
- **[NOTE]** — The Macro will transpose the Chain. This only applies to Drum Rack Chains.

### Chain Selector Rack

This Macrobat Rack allows you to use a Macro of a Rack to dynamically control the Rack’s Chain Selector. The range of the Macro will change depending on the number of Chains in the Rack. This is useful in cases where you're regularly adding/removing Chains to the Rack and don't want to have to continually edit the Rack's Chain zones.

#### Rack Name: `[CS]`

#### Macro Name:

**[CS]** – The Macro will control the Rack's Chain Selector.

### Learn Rack

This Macrobat Rack allows you to use a Macro of a Rack to control the last parameter that was selected in Live. You can select a parameter to control by clicking on it with your mouse. You can lock the Rack to the parameter it's currently controlling by turning the Rack off.

#### Rack Name: `[LEARN]`

#### Macro Name:

**[LEARN]** – The Macro will control the last parameter.

!!! note
    Although all parameters in Live can be clicked on, not all of them are classified as parameters that can be selected and so cannot be controlled. As an example, none of the parameters of a Clip can be controlled.

### MIDI Rack

This Macrobat Rack allows you to send MIDI messages (Control Change, Program Change and SysEx) from the Macros. These MIDI messages will be sent to the MIDI port selected as the Output of the ClyphX Pro Control Surface. They can optionally be sent to the MIDI port selected as the Output of a ClyphX Pro XT Script. To accomplish the latter, you'll specify the letter of the XT Script after the word `MIDI` in the Rack's name. For example, to send MIDI messages to ClyphX_Pro_XTB, you'd name the Rack `[MIDIB]`.

In all cases, these messages will only be sent when the Rack is on. Also, turning the Rack off and then on again will cause it to resend its MIDI messages with their current values.

#### Rack Name: `[MIDI]`

#### Macro Names

- **[CC X Y]** — The Macro will send Control Change number `X` on MIDI Channel `Y`. If a MIDI Channel is not specified, the Control Change message will be sent on MIDI Channel 1.
- **[PC X]** — The Macro will send Program Change messages on MIDI Channel `X`. If a MIDI Channel is not specified, the Program Change messages will be sent on MIDI Channel 1.

The Macros can also send SysEx messages. In order to access this functionality, you’ll first need to define the SysEx messages to send. You'll do this in `MIDI Rack-SysEx.txt`, which you can find in your User directory in the `nativeKONTROL/ClyphX_Pro` folder. 

To access the SysEx messages from Macros, you’ll use the names you specified in your SysEx list for the Macro Names. For example: `[MY SYSEX]`

#### Routing Options

Please see [this page](/action-reference/midi-actions#routing-options).

### Receiver Rack

The Macros of this Macrobat Rack (referred to as _Receivers_) allow you to control the Macros of other Racks (referred to as _Senders_) in your Live Set. In order to accomplish this, you'll specify a unique name for the Receiver and also add this unique name to the name of the Sender. Please note that a
Receiver can only control one Sender.

As with all Macrobat Racks, this Rack will update its connections any time you change its name or the names of its Macros. However, it will not update when the name of a Sender is changed. For that reason, you should add the unique name of the Receiver to the name of the Sender before adding it to the Receiver. Alternatively, after you've specified names for Senders and Receivers, you can turn the Rack off and then on again and all connections will be updated.

#### Rack Name: `[RECEIVER]`

#### Macro Name

`[X]` – The Macro will control the Sender that contains `[X]` in its name where `X` is a unique name.

### RnR Racks

RnR Racks are a group of four Macrobat Racks that can reset or randomize the parameters of other Devices. These Racks don't make use of Macros, they strictly use the Rack's on/off switch. To access the function of these Racks, just change the state of the on/off switch (if it's on, turn it off or vice versa).

These Racks are position-sensitive. This means that the Devices they will apply to depends on where they are located. If the RnR Rack is a top level Rack (not nested inside of another Rack), the RnR Rack will apply to other Devices on the Track. If the RnR Rack is nested inside of another Rack, the RnR Rack will apply to other Devices on the same Device Chain.

RnR Racks will **not** affect each other or other Macrobat Racks, only other Devices on the Track/Device
Chain.

#### Rack Names

`[RND]`

This RnR Rack will randomize the parameters of the Device to the right of it.

`[RND ALL]`

This RnR Rack will randomize the parameters of all of the Devices to the right of it.

`[RST]`

This RnR Rack will reset the parameters of the Device to the right of it.

`[RST ALL]`

This RnR Rack will reset the parameters of all of the Devices to the right of it.

#### Macro Names

Doesn't apply to RnR Racks.

### Snap Rack

This Macrobat Rack allows you to access Snap data stored via ClyphX Pro's [Snap Actions](/action-reference/snap-actions). The Macros can morph the values of all the parameters stored in a Snap between their current values and the values stored in the Snap.

Current values are assessed when the Macros of the Rack are initialized (either by being renamed or upon the Rack being loaded into a Live Set). You can cause the current values to be reassessed by turning the Rack off and then on again.

#### Rack Name: `[SNAP]`

#### Macro Names

`[X]` – The Macro will morph the Snap data of the Snap named `X`.

### Snap Alt Rack

This Macrobat Rack is similar to the Snap Rack described above, but works more directly with ClyphX Pro's Snap Actions and X-Triggers. Snaps can be sent to this Rack from any X-Trigger by using a modified RECALL Action like so: 

`[MY SNAP] RECALL RACK`

Once a Snap has been sent to this Rack, the Rack's first Macro can be used for morphing the values of all the parameters stored in the Snap between their current values and the values stored in the Snap. The Rack's name will also display the Snap's identifier.

Unlike other Macrobat Racks, you should have **only one** Snap Alt Rack in your Live Set and only its first Macro can access Macrobat functionality.

#### Rack Name: `[SNAP ALT]`

#### Macro Name

`[SNAP]` – The Macro (which can only be Macro 1) will morph the Snap data of the last Snap sent to the Rack.

### Track Rack

This Macrobat Rack allows you to control mixer parameters of the Track it is on.

#### Rack Name: `[TRACK]`

#### Macro Names

- `[VOL]` – The Macro will control the Track's Volume.
- `[0DB]` – The Macro will control the Track's Volume, but with a limited range of -inf – 0db.
- `[PAN]` – The Macro will control the Track's Panning.
- `[PANL]` – The Macro will control Track Left Split Stereo Panning.
- `[PANR]` – The Macro will control Track Right Split Stereo Panning.
- `[SEND X]` – The Macro will control one of the Track's Send levels where `X` is the letter of the Send to control.
