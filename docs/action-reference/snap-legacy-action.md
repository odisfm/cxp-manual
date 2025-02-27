---
weight: 11
---

# Snap Legacy Action

This Action is quite similar to the standard [Snap Actions](/action-reference/snap-actions), so please refer to that section for information on Snaps in general. In this section, we'll cover how this Action differs from the standard Snap Actions and why you might use it.

## General Notes

- Unlike the standard Snap Actions, this Action stores Snap data within the name of the [X-Clip](/manual/core-concepts/#x-clips) that triggered it. This has several implications: 
    - **(a) Only X-Clips** can use this Action. 
    - **(b)** This Action should not be used in Action Lists with other Actions. 
    - **(c)** Since the Snap data is stored within the name of the X-Clip itself, the X-Clip can be used in other Live Sets. This is the primary benefit of this Action.
- The [Identifier](/manual/core-concepts/#identifiers) that precedes this Action is not relevant and does not have to be unique. This has two implications: 
    - **(a)** You can create a bunch of X-Clips containing this Action without concerning yourself with unique Identifiers, which is preferable in certain use cases. 
    - **(b)** Since the Snap data is not associated with an Identifier, it **cannot** be used with the Macrobat Snap Rack. However, it **can** be used with the Macrobat Snap Alt Rack.

## Storing Snaps

Storing Snaps with this Action is virtually identical to storing Snaps using the standard Snap Action and all of the Snap Action Modifiers can be used. The only difference is the name of the Action, which is `SNAPLEG`

Upon triggering this Action, a Snap will be stored in the name of the X-Clip. The name is not meant to be readable and will look something like this:

`[IDENT] Recleg ||(dp0 w"1-MIDI" p1 (dp2 S'devices'`

Once the Snap has been stored, you should **not** alter the name of the X-Clip except as is covered in the next section.

## Recalling Snaps

Once a Snap has been stored by this Action, it will immediately be ready for recall. As with the standard Snap Actions, you have options in terms of how the Snap will be recalled. By default, it will be recalled immediately.

You can add the [RAMP x, RAMPS x](/action-reference/global-actions/#wait-x) or RACK (for use with the Macrobat Snap Alt Rack) recall keywords after the word `Recleg` to recall the Snap with smoothing or morphing. For example:

`[IDENT] Recleg RAMP 4||(dp0 w"1-MIDI" p1 (dp2 S'devices'`


