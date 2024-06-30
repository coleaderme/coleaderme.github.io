+++
title = "VDJ Script mapping"
date = "2024-06-30"
description = "Virtual DJ Script mapping"
+++

# Virtual DJ 2020++ script for mapping  

VDJscript knows 6 types of parameters:  
- text: need to be enclosed in either single quotes (') or double quotes ("): load 'myfile.mp3'  
- boolean: can be the keywords on, off or toggle. (they are often equivalent to the integers 1, 0 and -1 respectively): smart_play off  
- time: are specified by adding the keyword ms: nudge +100ms  
- integer: effect_select +1  
- decimal: crossfader 0.5  
- percentage: crossfader 50%  

Official Docs: https://virtualdj.com/goto/vdjscript  

## [Deck 1] operations on press of `{HOME}` button  

```rust
deck 1 repeat 200ms & effect_slider 1 +4% & eq_low -4% & eq_mid -4%
```
Explaination:  
- target deck 1  
- repeats every 200ms (on button hold)  
- do:  
    - 1st effect slider on rack increase by +4%  
    - eq_low (low range) reduce by -4%  
    - eq_mid (mid range) reduce by -4%  


## [Deck 2] operations on press of `{END}` button  

```rust
deck 2 repeat 200ms & effect_slider 1 +4% & eq_low -4% & eq_mid -4%
```
Explaination:  
- target deck 1  
- repeats every 200ms (on button hold)  
- do:  
    - 1st effect slider on rack increase by +4%  
    - eq_low (low range) reduce by -4%  
    - eq_mid (mid range) reduce by -4%  


## Reset effect_slider and eq:

If effect slider is **reverb** then reset value is 0%  
```rust
(deck 1 effect_slider 1 0% & eq_reset) & (deck 2 effect_slider 1 0% & eq_reset)
```

For any other effect slider where reset position is in middle.  
such as **noise**, then reset value is 50%  
```rust
(deck 1 effect_slider 1 50% & eq_reset) & (deck 2 effect_slider 1 50% & eq_reset)
```

Explaination:   
- in first `()` target deck 1  
- do:  
    - effect slider 1 to value 0%  
    - reset eq (low,mid,high)  
- same thing in second `()` but for deck 2  

## beatjump (seek around faster):  
[CTRL+Arrow]  `beatjump +1`  
[CTRL+Arrow]  `beatjump -1`  
try `nudge -100ms`  for cool reverse swipe  


*more to be added soon..*

