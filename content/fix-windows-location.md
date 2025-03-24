+++
title = "Fix Greyed out Windows Location"
date = "2025-03-24"
description = "Windows 10 location greyed out / disabled in settings"
 +++


1. Ensured that the `Geolocation` service is running and set to Automatic  

2. Replace `0` with `1` in the registry **(IMPORTANT)** :  
`Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\LocationAndSensors`  
Restart PC  
If this does not fix then most likely you need to Clean Install Windows.  

3. Ensured that this registry key is set to "Allow":  
`HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager\ConsentStore\location`  

4. Deleted this key in the registry:  
`HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\lfsvc\TriggerInfo\3`  

5. Ensured that the three policies in this folder are all not configured:  
Administrative `Templates\Windows` `Components\Location` and `Sensors`  

6. Ensured that the policy "Turn off Windows Location Provider" is not configured in this folder:  
Administrative `Templates\Windows` `Components\Location` and `Sensors\Windows` Location Provider  