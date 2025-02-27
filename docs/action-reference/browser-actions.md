---
weight: 3
---

# Browser Actions

The following Actions allow you to load items from Live's Browser and control hotswapping. In all cases, only items that exist in the root folders of the Browser (listed in the CATEGORIES section of the Browser) can be loaded/swapped. Also, when specifying the name of an item, the name should be exactly as it appears in the Browser.

### INSERT `x`

`x` is the type of Device insertion mode to use when loading Devices. The options are `LEFT` or `RIGHT` (load Devices to the left or right of the selected Device on the selected Track) or `DEFAULT` (load Devices at the end of the Device list on the selected Track.).

```
INSERT DEFAULT
INSERT LEFT
INSERT RIGHT
```

### LOADCLIP `x`

`x` is the name of the Clip (from the Clips category) to load. This will create a new Track.

```
LOADCLIP "01_DemonChoir.alc"
LOADCLIP "2+2=4.alc"
```

### LOADDEV `x`

`x` is the name of the native Live Device to load onto the selected Track. 

```
LOADDEV "Amp"
LOADDEV "Auto Filter"
```

### LOADDRUMS `x`

`x` is the name of the item (from the Drums category) to load onto the selected Track.

```
LOADDRUMS "Analog Bully Kit.adg"
LOADDRUMS "A-Ping Ride 1.aif"
```

### LOADM4L `x`

`x` the name of the M4L Device to load onto the selected Track. 

```
LOADM4L "LFO.amxd"
LOADM4L "Max Cutkiller.amxd"
```

### LOADPACK `x`

`x` is the name of the item (from the Packs category) to load.

```
LOADPACK "HHat2.aif"
LOADPACK "Drums On Song 1.alc"
```

### LOADPLUG `x`

`x` is the name of the Plug-in (from the Plug-ins category) to load onto the selected Track.

```
LOADPLUG "Diva",
LOADPLUG "Transient Master"
```

### LOADSAMPLE `x`

x is the name of the Sample (from the Samples category) to load into a Simpler Device on the selected Track.

```
LOADSAMPLE "Junk Mail1.aif"
LOADSAMPLE "Mama Slug.aif"
```

### LOADSOUND `x`

`x` is the name of the Sound (from the Sounds category) to load onto the selected Track.

```
LOADSOUND "2020 Bass.adv"
LOADSOUND "Once Beaten.adg"
```

### LOADUSER `x`

`x` is the name of the item (from the User Library category) to load. You can alternatively specify a User Library folder path to randomly load an item from. When specifying folder paths, use a slash as the path separator.

```
LOADUSER "My Rack.adg"
LOADUSER "My Clip.alc"
LOADUSER "My Folder"
LOADUSER "Samples/Drums/Kicks"
```

### SWAP

Open the Browser and activate hotswapping for the selected Device.

### SWAP `x`

`x` is the name of the Preset to hotswap into the selected native Live Device or Max for Live Device.

```
SWAP "Bass Roundup.adv"
SWAP "Beat Morpher.adg"
```

### SWAP < or >

Swap to the Prev/Next Preset for the selected native Live Device or Max for Live Device.

```
SWAP <
SWAP >
```
