+++
title = 'Disable touchpad gestures'
date = 2023-10-13T15:22:57+05:30
description = "Disable touchpad corner gestures Win 8.1"
[taxonomies]
tags = ["windows", "touchpad", "gesture"]
+++

Save this as **gestures.reg** make sure it is NOT **.txt**  
```
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Synaptics\SynTPEnh\ZoneConfig\TouchPadPS2\Right Edge Pull]
"ActionType"=dword:00000000
[HKEY_CURRENT_USER\Software\Synaptics\SynTPEnh\ZoneConfig\TouchPadPS2\Left Edge Pull]
"ActionType"=dword:00000000
[HKEY_CURRENT_USER\Software\Synaptics\SynTPEnh\ZoneConfig\TouchPadPS2\Right Edge Pull Extended Zone]
"ActionType"=dword:00000000
[HKEY_CURRENT_USER\Software\Synaptics\SynTPEnh\ZoneConfig\TouchPadPS2\Top Edge Pull]
"ActionType"=dword:00000000
```

Double click **gestures.reg** to apply.  

Note: Depending on device, sometimes TouchPadPS2 can be TouchPadPS2_1, TouchPadPS2_2 or similar.  
replace with your specific.  


### Additionally:   
Download skipMetroSuite from [winaero](https://winaero.com/download-skip-metro-suite/)  
mirror gdrive: [skipMetroSuite](https://drive.google.com/file/d/1N2Ne33yU1bQUqZZdt08ULpObLXd8kQR6/view?usp=sharing)  