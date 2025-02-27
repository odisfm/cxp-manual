# Core Concepts

ClyphX Pro is a deceptively simple scripting language for music producers and performers who use
Ableton Live that allows for easy control and manipulation of virtually every aspect of a Live Set in
highly useful and interesting ways.

At the heart of ClyphX Pro is its extensive list of Actions. Actions produce changes in Live and are
associated with simple words or phrases. For examples, `BPM 100` will set the Tempo of the Set to 100
and `LOADDEV "Auto Filter"` will load Auto Filter onto the selected Track. Actions are specified in Action Lists, which are described below.

Action Lists are triggered by X-Triggers, which are events (such as a Clip being launched or a button on
a controller being pressed) that occur in Live. So, the basic idea here is that you'll use X-Triggers to
trigger Action Lists, which are comprised of Actions.

ClyphX Pro also includes a component called Macrobat that adds new functionality to Racks. This
component is covered in its own manual, which is provided along with ClyphX Pro.

## Action Lists

An Action List is comprised of one or more [Actions](/action-reference/global-actions). As an example, a simple Action List might toggle Session Record: `SREC`. A more complex Action List might mute Tracks 1 and 4, arm Track 2 and turn on the first Device on Track 2: `1, 4/MUTE ON ; 2/ARM ON ; 2/DEV(1) ON`

When specifying an Action List, each Action should be separated by a semicolon ( `;` ) as shown in the
second example above.

The Actions in an Action List are performed sequentially (first Action performed, then second Action,
etc), but the processing is nearly instantaneous, so it appears that all Actions in an Action List are
performed at the same time.

### Sequential action lists

On a related note, Actions that apply to selected items (such as a Track) will apply to the item selected at
the time the Action List was processed as opposed to items that become selected as part of the same
Action List. If you'd like an Action List to select an item and then apply to the item that was selected,
you can use the [WAIT](/action-reference/global-actions#wait-x) Action after the selection Action.

It's also possible to step through an Action List and trigger each Action one at a time each time the
Action List is triggered. To accomplish this, the Action List should be preceded by `(PSEQ)`. For
example: `(PSEQ) 1/ARM ; 2/ARM ; 3/ARM`.

In this example, the first time the Action List is triggered, Track 1 will be Armed. The second time, Track 2 will be Armed. The third time, Track 3 will be Armed. The fourth time, it will wrap back around to be beginning and Track 1 will be disarmed.

You can alternatively use `(RPSEQ)` instead of `(PSEQ)` to step through the Action List randomly.


!!! note
    In the rest of this document, we'll use CAPITAL LETTERS when referring to Action Lists. However, Action Lists are not case-sensitive. You can use capitalization that is comfortable for you. There is just one exception to this. Names specified within quotes are case-sensitive. So, for example, `"My Name"` is not the same as `"my name"`.

## Identifiers

Some of the X-Triggers (described below) require an Identifier at the beginning of their name before their Action List. For example, in the case of X-Clips (described below), the Identifier is what distinguishes an X-Clip from a regular Clip. An Identifier is any word or phrase enclosed in square brackets. As an example:

`[THIS IS AN IDENTIFIER]`

## X-Triggers

X-Triggers are events that occur in Live that can, in turn, trigger [Action Lists](#action-lists). There are currently six types of X-Triggers.

### Startup Actions

This is an event that occurs each time a Live Set is loaded. The [Action List](#action-lists) it should trigger is specified in Preferences.txt.

### X-Cues

An X-Cue is any Locator in Arrangement View that includes an [Identifier](#identifiers) and an [Action List](#action-lists). An X-Cue will trigger its Action List when the playhead crosses over the X-Cue. Its Action List will not be triggered when the X-Cue to jumped to, only when the playhead crosses over it.

### X-Clips

An X-Clip is any Clip in Session View that includes an [Identifier](#identifiers) and an [Action List](#action-lists).

#### Default
`[IDENT] 3/CLIP SEMI > ; 3/CLIP CENT -25`

This X-Clip will trigger its Action List when the X-Clip starts playing (not when it's launched). This way, its Action List can be quantized via Global or Launch Quantization.

#### Default with Stop
`[IDENT] REC ON ; 1-2/ARM : UNARM ; REC OFF`

This X-Clip has two Action Lists, that are separated by a colon ( `:` ). The first Action List will be triggered when the X-Clip is played. The second Action List will be triggered when the X-Clip stops playing. To trigger the same Action List for play and stop, specify an asterisk ( `*` ) for the second Action List (for example `[IDENT] MUTE : *`).

#### LSEQ or RLSEQ
`[IDENT] (LSEQ) 1/CLIP(2) CUE >1 ; 1/MUTE`

This X-Clip works similar to a `PSEQ` Action List except it will step through and trigger the Actions in its Action List one at a time each time the X-Clip Loops. You can alternatively use (`RLSEQ`) instead of (`LSEQ`) to step through the Action List randomly.

!!! note "X-Clip notes"
    * An X-Clip’s [Action List](#action-lists) will not be triggered while the X-Clip is recording.
    - If a Clip-related Action is triggered from the X-Clip that it’s applied to, this could cause the Action to be triggered repeatedly. In general, it’s recommended that you do not trigger Clip-related Actions from the X-Clip that the Actions will be applied to.
    - Selection and navigation-related Actions may not work correctly when triggered from an X-Clip if 'Select on Launch' is turned on in your Live Preferences.

### X-Scenes

An X-Scene is any Scene in Session View that includes an [Identifier](#identifiers) and an [Action List](#action-lists). An X-Scene will trigger its Action List upon the X-Scene being triggered.

### X-Controls

An X-Control is a control on a MIDI controller. An X-Control will trigger its [Action List](#action-lists) upon the control sending an on message (a MIDI message with a value that is 34 or higher). It can optionally trigger a second Action List upon the control sending an off message (a MIDI message with a value of 32 or less). The on value threshold can be changed in Preferences.txt. You'll define controls on your controller to use as X-Controls in X-Controls.txt. Please refer to Using MIDI Controllers for information on how to set up MIDI controller(s) to use with ClyphX Pro.

### X-OSC

An X-OSC is an OSC address. An X-OSC will trigger its [Action List](#action-lists) upon receiving an on value (a value that is not 0). It can optionally trigger a second Action List upon receiving an off value (a value of 0).

You'll define OSC addresses to use as X-OSCs in X-OSC.txt. By default, ClyphX Pro will receive OSC messages on port 7005. If need be, you can change this in Preferences.txt. In either case, the port your OSC addresses are sent on and the port that ClyphX Pro receives from need to be the same.

## XT Scripts

Upon [installing ClyphX Pro](/setup/#installing-clyphx-pro), five additional Control Surface scripts (ClyphX_Pro_XTA – ClyphX_Pro_XTE) will be installed. XT Scripts allow you to use the controls on additional MIDI
controllers and also use the Midi Actions to send MIDI messages to the MIDI port selected as the
Output of each XT Script.

!!! warning
    XT Scripts **must** be selected in Control Surface slots **beneath** ClyphX Pro in order for them to properly connect to ClyphX Pro.

## Max for Live

In addition to [X-Triggers](#x-triggers) and [XT Scripts](#xt-scripts), it's also possible to trigger ClyphX Pro Actions from Max for Live. The [ClyphX Pro Live Lessons](/setup/#documentation) include a Max for Live Integration Lesson and an example Max for Live Device that demonstrates how this works. Additionally, the Triggering Actions via Notes in a Clip Lesson provides a Max for Live Device that allows ClyphX Pro Actions to be triggered via Notes in MIDI Clips.

## Settings Folders/Files

ClyphX Pro includes a variety of optional settings files that can be found within its settings folder. This folder will be created upon selecting ClyphX Pro or one of the [XT Scripts](#xt-scripts) as a Control Surface in Live. You can find this folder (named `ClyphX_Pro`) in the `nativeKONTROL` directory within your User directory. This folder will contain the following files:
    
- **Macros.txt** - contains [Macro](#macros) definitions
- **MIDI Rack-SysEx.txt** - contains SysEx messages for use with the Macrobat MIDI Rack
- **Preferences.txt** - contains general preference settings
- **Script Linking.txt** - contains settings related to [Script Linking](#script-linking)
- **Variables.txt** - contains [Variable](#variables) definitions
- **X-Controls.txt** -  contains [X-Control](#x-controls) definitions
- **X-OSC.txt** - contains [X-OSC](#x-osc) definitions

## Script Linking

ClyphX Pro allows you to link up to 6 Control Surface scripts together so that they will control groups of Tracks and/or Scene relative to each other. In order for a script to be linked, it needs to include a linkable component. Many of the scripts built into Live (such as Push or APC40) include such a component. In general, if a script has an associated colored border (with a fixed size) that surrounds the Tracks and Scenes it’s controlling, it can be linked.

Script Linking-related settings can be made in `Script Linking.txt`.

## Macros

Macros are [Action Lists](#action-lists) that are associated with user-specified names. Here is an example of a Macro:

`$MY_MACRO$ = 1, 4/MUTE ON ; 2/ARM ON ; 2/DEV(1) ON`

To trigger a Macro from an [X-Trigger](#x-triggers), you simply have to specify its name:

`$MY_MACRO$`

Macros are useful in the case of [X-Clips](#x-clips), [X-Cues](#x-cues) and [X-Scenes](#x-scenes) as Macros allow you to trigger long Action Lists via the short names you specified for them, and thus you don't need to have X-Clips, X-Cues and X-Scenes with really long names that are difficult to edit.

Macros are also useful in the case of [X-Controls](#x-controls) and [X-OSCs](#x-osc) since Macros can be reassigned on the fly. So, you can assign a Macro to an X-Control or X-OSC and then reassign the Macro at will and thus change the Actions the X-Control or X-OSC triggers.

### Defining macros
**There are two ways to define Macros:**

- You can define Macros in `Macros.txt`. Macros you define here will always be available in any Live Set.
- You can define Macros and reassign existing Macros from within Action Lists. Macros defined this way are temporary (only accessible to the current Live Set). Note, however, that Macro definitions/reassignments cannot be combined with other Actions. They should be the only Action in an Action List. The reason for this is that Macros _are_ Action Lists themselves.

In both cases, the syntax is as shown in the example above. Also, as shown in the examples above, when defining, reassigning or using Macros, the Macro's name always needs to be enclosed in dollar signs ( `$` ).

## Variables

!!! warning "Advanced"
    This is an advanced concept that is really only useful in very rare circumstances. If you're not already familiar with the concept of Variables in other programming scenarios, you can safely skip this section.

Variables are values of some sort that are associated with user-specified names, which can be used in your [Action Lists](#action-lists). Here is an example of a Variable:

`%MY_VARIABLE% = 10`

To use a Variable in an Action List, you simply have to specify its name:

`%MY_VARIABLE%/MUTE`


### Defining variables
**There are two ways to define Variables:**

- You can define Variables in Variables.txt. Variables you define here will always be available to any Action List in any Live Set.

- You can define Variables and reassign existing Variables from within Action Lists (but not from within [Macros](#macros)). Variables defined/assigned this way are temporary (only accessible to the current Live Set). Also, Variables defined/assigned this way can only be assigned once within an Action List.

In both cases, the syntax is as shown in the example above. Also, as shown in the examples above, when defining, reassigning or using Variables, the Variable's name always needs to be enclosed in percent signs ( `%` ).

### Using Python expressions in variables

As far as values, Variables can be assigned to virtually any value or to any valid Python expression, but the value cannot include a semicolon ( `;` ). Also, Variables can access properties of a Live Set through an attribute named `song`. This attribute provides access to the majority of Live's API. For example, through it, you can access the name of the selected Track like so:

`%MY_VARIABLE% = song.view.selected_track.name`

To learn more about what you can access through song, see the [LOM documentation](https://docs.cycling74.com/apiref/lom/), which covers a subset of the API (known as the LOM). Note, however, API paths and LOM paths are slightly different. This example demonstrates how to transpose LOM paths to API paths:

**LOM:** `live_set tracks 4 clip_slots 6`

**API:** `song.tracks[4].clip_slots[6]`

### Built-in variables

In addition to Variables you define, you also have access to built-in Variables. The following builtin
Variables are available:

- `BPM` - the current Tempo of the Live Set in BPMs
- `RND` - a random integer in the range of 0 – 100000
- `RNDx-y` - a random integer in the range of `x` – `y`
- `TIME` - the current date and time in the format of year-month-day hour:minute:second

## User actions

!!! warning "Advanced"
    This is an advanced concept that is really only useful to Python programmers. If you're not already familiar with Python, you can safely skip this section.

In addition to all of the [Actions](/action-reference) you can access with ClyphX Pro, you can also create your own User Actions that function just like builtin Actions. User Actions are created in the ClyphX_Pro folder within your User Library. The exact location within the folder is `ClyphX_Pro/clyphx_pro/user_actions`.

!!! note "Editor's Note"
    An update to ClyphX Pro allows for another user actions folder. The location of this folder is `User Library/Remote Scripts/_user_actions`. 

    Using this new folder prevents the accidental deletion of your user actions when upgrading ClyphX.

In that location, you'll find a file name `ExampleActions.py` that includes instructions and examples on how to create User Actions. Although it is possible to edit/view this file with any text editor, it is recommended that you use an IDE when creating User Actions.

!!! note "Editor's Note"
    Since the release of ClyphX Pro, creator Stray released further materials explaining user actions.
    
    * [Tutorial (nativeKontrol forums](https://nativekontrol.proboards.com/thread/3022/tip-creating-user-actions)
    * [Tutorial (archived link)](https://archive.is/uZw3O)
    * [Video version (YouTube)](https://www.youtube.com/watch?v=tVUt4rByPU4&t=0s)
