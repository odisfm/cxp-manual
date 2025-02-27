---
weight: 1
---

# Scene Actions

The following Actions allow you to manipulate and Launch Scenes in various ways. Unless otherwise noted, if no Scene number or name is specified, these Actions will apply to the selected Scene or, when triggered by an [X-Clip](/manual/core-concepts#x-clips), the Scene the X-Clip is on. Alternatively, you can specify the Scene to apply the Actions to by Scene number, name, `SEL` for the selected Scene or `LAST` for the last Scene.

In the case of the Launch-related Actions, these will not allow an X-Clip to Launch the Scene it resides on as that would cause a feedback loop. If you're using an X-Clip and need to Launch Clips on the same Scene as the X-Clip, you can use a [Track Action](/action-reference/track-actions) (like `ALL/PLAY`).

### ADDSCENE

Create a Scene below the selected Scene. [^1]

### ADDSCENE `x`

Create a Scene where `x` is the Scene number of the new Scene. Specify -1 to create the Scene at the end of the Scene list. [^1]

### CAPSCENE

Trigger Live's Capture and Insert Scene function.

### SCENE `x`

`x` is the Scene to Launch.

```
SCENE 10
SCENE SEL
SCENE "My Scene"
```

### SCENE < or >

Launch the Prev/Next Scene relative to the last Launched Scene.

```
SCENE <
SCENE >
```

### SCENE <`x` or >`x`

Launch the Scene that is `x` Scenes prior to or after the last Launched Scene.

```
SCENE <5
SCENE >3
```

### SCENE COLOR `x`

`x` is the index of the Color (in the range of 1 - 70) to set the Scene to. 

```
SCENE COLOR 5
SCENE 10 COLOR 43,
SCENE "My Scene" COLOR 60
SCENE SEL COLOR 25
```

### SCENE COLOR < or > 

Select the previous/next Color for the Scene. 

```
SCENE COLOR <
SCENE 10 COLOR >
SCENE "My Scene" COLOR <
SCENE SEL COLOR >
```

### SCENE DEL

Delete the Scene. It is not possible to Delete a Scene if it's the only Scene in the Set. [^1]

```
SCENE DEL
SCENE LAST DEL
SCENE "My Scene" DEL
SCENE SEL DEL
```

### SCENE DUPE

Duplicate the Scene. [^1]

```
SCENE DUPE
SCENE 10 DUPE
SCENE "My Scene" DUPE
SCENE SEL DUPE
```

### SCENE NAME `x`

`x` is the new name for the Scene. 

```
SCENE NAME "Verse"
SCENE 10 NAME "Hook"
SCENE SEL DUPE "Bridge"
```

### SCENE NAMEA `x`

Similar to [SCENE NAME](#scene-name-x), but adds `x` after the current name.

```
SCENE NAMEA "Alt"
```

### SCENE NAMEP `x`

Similar to [SCENE NAME](#scene-name-x), but adds `x` before the current name.

### SCENE NAMED `i` `x` 

Same as [SCENE NAME](#scene-name-x), but `i` is the new Identifier of the Scene. A timestamp will be added to the Identifier in order to make the Identifier unique for use in [Snap Actions](/action-reference/snap-actions).

### SCENE RND

Launch a randomly selected Scene. 

### SCENE RND`x`-`y`

Launch a randomly selected Scene in the range of `x`-`y` (where both `x` and `y` are in the range of 1 - the number of Scenes in the Set).

```
SCENE RND5-10
SCENE RND96-142
```

### SCENE SEL `x`

`x` is the Scene to Select. 

```
SCENE SEL 10
SCENE SEL "My Scene"
```

[^1]: When these Actions are triggered via an [X-Clip](/manual/core-concepts#x-clips), the X-Clip will be stopped to prevent the Actions from being retriggered.