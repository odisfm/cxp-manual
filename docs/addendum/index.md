# Addendum

ClyphX Pro has many [Actions](/action-reference/global-actions) and features that are useful in their own right but, when combined with each other, they become much more powerful. In this section, we'll look at some examples of how you can leverage the feature set in interesting ways.

## Space-friendly navigation

Here are a couple of examples (best suited for use with [X-Controls](/core-concepts#x-controls) and [X-OSCs](/core-concepts#x-osc)) of alternate forms of navigation that are handy when screen real estate is limited. These two [Action Lists](/core-concepts/action-lists) will navigate to the previous/next Device on the Track respectively, ensure Devices are visible and will fold all Devices except for the Device that is selected.

`SHOWDEV ; DEV(ALL) FOLD ON ; DEVLEFT ; DEV FOLD OFF`

`SHOWDEV ; DEV(ALL) FOLD ON ; DEVRIGHT ; DEV FOLD OFF`

The same approach works for Group Tracks in Session View as well.

`ALL/FOLD ON ; LEFT ; FOLD OFF`

`ALL/FOLD ON ; RIGHT ; FOLD OFF`

## Which Clips have been played?

In some cases, it's useful to not allow a Clip to be played more than once in a performance. The
following Action List (meant for use with [X-Clips](/core-concepts#x-clips)) deactivates the Clip once it's been played.

`[My Clip] D : CLIP(SELF) MUTE ON`

A variation on that approach, changing the color of the Clip to indicate that it has been played, can also
be useful. Here, we change its color to white.

`[My Clip] D : CLIP(SELF) COLOR 60`

## From Snap to ramp

The [Snap Action](/action-reference/snap-actions#snap) will automatically rename X-Clips after they have stored a Snap so that the Snap can immediately be recalled. But what if you want to recall the Snap with ramping and don't want to have to manually change the X-Clip's name?

`[IDENT] ALL/SNAP ; CLIP NAME "[IDENT] RECALL RAMP 10"`

The same approach can be used with X-Controls and X-OSCs by using [Macros](/core-concepts#macros). First, define a Macro like so:

`$BTN_1$ = ALL/SNAP`

Then, for the X-Control or X-OSC, specify the following for its On and Off Action Lists.

`[IDENT] $BTN_1$ : $BTN_1$ = RECALL RAMP 10`

## Dynamic X-Control and X-OSC assignments

Unlike other X-Triggers, X-Control and X-OSC assignments are static (the same for every Live Set). It's possible to make their assignments dynamic by assigning them to Macros and then reassigning the Macros from other X-Triggers. This allows X-Controls and X-OSCs to have static (default) assignments that can be overridden as needed per Live Set.

First, define a Macro like so:

`$BTN_1$ = MUTE`

Then, for the X-Control/X-OSC, specify the Macro for its On Action List. So, by default, the X-Control/X-OSC will toggle the Mute state of the selected Track.

Now, you can use an X-Clip or X-Cue to change that assignment like so:

`[IDENT] $BTN_1$ = SOLO`

And, now, the X-Control/X-OSC will toggle the Solo state of the selected Track until the Macro is reassigned or a Live Set is loaded.

## Omitting Devices from ranges

When using Device ranges in [Snap Actions](/action-reference/snap-actions) or the [Clip Envelope Capture Action](/action-reference/clip-envelope-capture-action), you'll sometimes want to omit one or more Devices in the range so that they're not included in Snaps or captures. To do that, you can add `[omit]` to the Device's name and it will be omitted. If the Device is a Plug-in, it can be omitted by placing the Plug-in in a Rack and adding `[omit] to the Rack's name.

## Triggering multiple Actions per step in a sequence

By default, [PSEQ/RPSEQ Action Lists](/core-concepts#action-lists) and [LSEQ/RLSEQ X-Clips](/core-concepts#x-clips) can only sequentially trigger one Action at a time. This can be changed by using slightly different syntax. You simply have to enclose the Actions you'd like to be triggered simultaneously in curly brackets. For example:

`[IDENT] (PSEQ) {BPM 100; GQ 1 BAR} ; METRO ; {BPM 200; GQ 2 BARS; RQ 1/4}`

In that example, the first time it's triggered, `BPM 100` and `GQ 1 BAR` will be triggered. The second time, `METRO` will be triggered. And the third time `BPM 200`, `GQ 2 BARS` and `RQ 1/4` will be triggered. As you can see, you can have steps that include multiple Actions and steps that just consist of a single Action.