---
weight: 7
---

# Troubleshooting

This section provides resolutions to common problems that you may run into when installing or using ClyphX Pro. If you do not find a resolution to your problem here, please contact [support](/manual/support).

## General Troubleshooting

### I can't trigger any ClyphX Pro Actions

Make sure that you’ve got ClyphX Pro [selected as a Control Surface](/manual/setup/#live-settings/).

### I can't trigger ClyphX Pro Actions from X-Clips, X-Cues or X-Scenes

Make sure that you’ve listed an [Identifier](/manual/core-concepts#identifiers) at the beginning of the [X-Clip](/manual/core-concepts#x-clips), [X-Cue](/manual/core-concepts#x-cues) or [X-Scene](/manual/core-concepts#x-scenes) name.

### I can't trigger ClyphX Pro Actions from X-Controls or X-OSCs

Make sure that you’ve defined the X-Controls or X-OSCs correctly in [X-Controls.txt](/manual/core-concepts/#settings-foldersfiles) or [X-OSC.txt](/manual/core-concepts/#settings-foldersfiles) and that you’ve [selected the controller](/manual/setup/#live-settings/) as the **Input** of the ClyphX Pro Control Surface.

## None of this troubleshooting helped or I think I've found a bug

Please do the following:

1. Add an X-Clip named `[] DEBUG` in Session View and launch it.
2. Trigger the Action List(s) you're having trouble with.
3. Close Live (or load a new Live Set).
4. [Submit a support ticket or post on the forum](/manual/support) with your `Debug Log.txt` file as an attachment and please provide as much information on the problem as possible. You can find Debug Log.txt in the settings folder.


