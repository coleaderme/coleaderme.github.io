+++
title = "Windows Tips n Tricks"
date = "2024-12-11"
description = "Windows tips and tricks"
+++

# Change to AHCI (without windows reinstall)
1. Run `cmd` as Admin
- `bcdedit /set {current} safeboot minimal`
- `shutdown /r /t 0`
2. Computer will restart now. Goto BIOS/UEFI and change to AHCI.
3. Now you'll be in safeboot mode. Run `cmd` as Admin.
- `bcdedit /deletevalue {current} safeboot`
- `shutdown /r /t 0`
DONE! Windows will start with AHCI enabled.


# Win8.1 Remove Modern Apps
1. Open `Powershell` as Admin.
- `Get-AppxPackage -AllUsers | Remove-AppxPackage`
- `Get-AppXProvisionedPackage -online | Remove-AppxProvisionedPackage –online`

# DNScrypt-proxy setup
Github Instructions: https://github.com/DNSCrypt/dnscrypt-proxy/wiki/Installation-Windows
Simple Instructions:
1. Download for x64 `https://github.com/DNSCrypt/dnscrypt-proxy/releases/download/2.1.5/dnscrypt-proxy-win64-2.1.5.zip` (Recommended)
1. Download for x32 `https://github.com/DNSCrypt/dnscrypt-proxy/releases/download/2.1.5/dnscrypt-proxy-win32-2.1.5.zip`
2. extract zip file
3. open folder, to open `cmd` in current folder, press {ctrl+L} and type `cmd` {Enter}.
4. Copy configuration file via **cmd**
- `copy example-dnscrypt-proxy.toml dnscrypt-proxy.toml`
5. start dnscrypt-proxy program
- `.\dnscrypt-proxy.exe`
6. change dns to `127.0.0.1`

from now onwards everytime windows start, just run `.\dnscrypt-proxy` in **cmd**
  