---
weight: 1
---

# Scene Actions

The following Actions allow you to manipulate and Launch Scenes in various ways. Unless otherwise noted, if no Scene number or name is specified, these Actions will apply to the selected Scene or, when triggered by an [X-Clip](/manual/core-concepts#x-clips), the Scene the X-Clip is on. Alternatively, you can specify the Scene to apply the Actions to by Scene number, name, `SEL` for the selected Scene or `LAST` for the last Scene.

In the case of the Launch-related Actions, these will not allow an X-Clip to Launch the Scene it resides on as that would cause a feedback loop. If you're using an X-Clip and need to Launch Clips on the same Scene as the X-Clip, you can use a [Track Action](/action-reference/track-actions) (like `ALL/PLAY`).