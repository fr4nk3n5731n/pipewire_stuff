# Index of things inside here

## config files
### `/etc/pipewire/pipewire-pulse.conf`
add the following code to your main config
```
context.exec = [
    { path = "/usr/bin/pipewire" args = "-c /etc/pipewire/virtual_sinks.conf" }
]
```

### `/etc/pipewire/virtual_sinks.conf`
pipewire configuration combining Headset and VR Headset audio into 1 device, 
and creating various sinks that get streamed into the combined device

## useful things
### set GPU audio output to `Pro Audio`
this will give you all audio outputs at the same time so you can just reference the `node.name` of whatever HDMI/DP Output the HMDI is attached to instead of having to select a particular output in pavucontrol
### SteamVR launch options to mute/unmute HMD Audio upon start/exit of SteamVR
`pactl -- set-sink-mute "alsa_output.pci-0000_11_00.1.pro-output-8" off; %command%; pactl -- set-sink-mute "alsa_output.pci-0000_11_00.1.pro-output-8" on`
