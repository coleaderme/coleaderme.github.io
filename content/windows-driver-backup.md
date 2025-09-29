+++
title = "Windows Drivers Backup"
date = "2025-09-29"
description = "and Restore"
[taxonomies]
tags = ["Windows", "Drivers", "Backup", "Restore", "PowerShell", "Double Driver"]
+++

**Simple app**  
Download: Double Driver from (here)[https://www.majorgeeks.com/files/details/double_driver.html]  


example location `d:\drivers`  
# Backup
run `powershell`:  
```shell
Export-WindowsDriver -Online -Destination d:\drivers
```

# Restore
run `powershell`:  
```shell
pnputil /add-driver "d:\drivers\*.inf" /subdirs /install /reboot
```