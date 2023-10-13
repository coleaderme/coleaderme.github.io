+++
title = 'Audio Redirection speaker output to mic input | Pulseaudio'
date = 2023-10-13T14:26:26+05:30
description = "Audio Redirection speaker output to mic input using Pulseaudio in linux"
tags = [
    "Audio redirections",
    "speaker output",
    "mic input",
    "Equalizer",
]
+++

# Pulseaudio setup    
## Why?  
- Easy Equalizer  
- Easy Audio redirection/piping speaker output to mic input.  

Note: Alsa is all you need for basic media consuming, pulseaudio is required for points above^^.  
* firefox audio doesn't work with alsa, you will need to install **apulse** from AUR.  
`$ yay -S apulse`  
`$ apulse firefox` *voila!*  

## Installation:  
`$ sudo pacman -S pulseaudio pavucontrol pulseaudio-alsa pulseaudio-equalizer-ladspa pulseaudio-zeroconf pulsemixer`  

## Basic audio control:  
`$ pulsemixer`: [ENTER] to set your default output (so you dont have use ID)  
toggle  mute: `$ pulsemixer --toggle-mute`  
decrease vol: `$ pulsemixer --change-volume -5`  
increase vol: `$ pulsemixer --change-volume +5`  

## Equalizer:  
**open** `pulseaudio-equalizer-gtk` which is installed by *pulseaudio-equalizer-ladspa*.  

## Audio redirection/piping:  
`$ pavucontrol`  
goto **Recording** tab, show: **All Streams**  
select from there.  
  
  
  
  
`.`