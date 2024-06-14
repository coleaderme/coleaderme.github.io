+++
title = "Improve Performance"
date = "2024-06-14"
description = "Some more info"
+++

# Memory 

Archlinux [wiki](https://wiki.archlinux.org/title/Improving_performance#Improving_system_responsiveness_under_low-memory_conditions)

**recommendations**: Disable swap completely (just skip swap partition during installation)   

### Setting up systemd-oomd:  

install: systemd-oomd-defaults   
edit: /etc/systemd/oomd.conf   
```
[OOM]
# goes with disabled swap
SwapUsedLimit=0%

# take action on 75%
# too high can be too late to act
# too low can result in false positives
DefaultMemoryPressureLimit=75%
DefaultMemoryPressureDurationSec=10s
```

start:   
```bash
sudo systemctl enable systemd-oomd
sudo systemctl start systemd-oomd
```
