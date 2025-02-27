---
weight: 4
---

# Using MIDI Controllers

You can use the controls on your MIDI controllers with a variety of ClyphX Pro's features ([X-Controls](/core-concepts#x-controls), [G-Controls](/optional-accessories#clyphx-pro-g-controls) and [Bindings](/optional-accessories/#clyphx-pro-bindings) specifically). The ClyphX Pro Control Surface itself can be used with one MIDI controller, which you can specify by selecting the controller as the **Input** and (if the controller has LEDs that can be remotely controlled and/or motorized faders) **Output** of the ClyphX Pro Control Surface.

Each [XT Script](/core-concepts#xt-scripts) can be used with an additional MIDI controller, which you can specify by selecting the controller as the Input and (if the controller has LEDs that can be remotely controlled and/or motorized faders) Output of the XT Script.

In the rest of this section, when we refer to ClyphX Pro, we mean either ClyphX Pro or one of the XT Scripts.

When using controllers with ClyphX Pro, you can keep other settings for your controller(s) in place. However, if the controller is used as the Input for another Control Surface, you will need to ensure that the other Control Surface is not set up to receive the same MIDI messages that you’ve configured for the controller in ClyphX Pro. Also, a MIDI message can either be used as an X-Control, G-Control or binding.

In addition, if the **Remote** switch is turned on for the controller, make sure that MIDI mappings in your Live Set do not use the same MIDI messages you’ve configured for the controller in ClyphX Pro.

Lastly, if the **Track** switch is turned on for the controller, the MIDI messages you’ve configured for the controller in ClyphX Pro cannot be used for recording data into MIDI Clips or for playing instruments.