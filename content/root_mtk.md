+++
title = 'Root Mediatek devices'
date = 2024-01-16T16:49:51+05:30
description = "mtk tool for rooting, reading/writing flash and doing crazy stuff."
tags = ["boot", "root", "vbmeta", "mtkclient"]
+++

# [MTKClient](https://github.com/bkerler/mtkclient)  


## Install  

### ArchLinux  

```bash
sudo pacman -S python python-pip git libusb usbutils android-tools
```
or  
```bash
yay -S python python-pip git libusb usbutils android-tools
```

#### Grab files   
```bash
git clone https://github.com/bkerler/mtkclient
cd mtkclient
pip install -r requirements.txt
python setup.py build
python setup.py install
```
---------------------------------------------------------------------------------------------------------------  

### Windows  

#### Install python
- Install [python-3.9](https://www.python.org/ftp/python/3.9.11/python-3.9.11-amd64.exe)
- during setup, remember to click "Add to path" [✅] option.  


#### Grab files and install  
- Download Zip by clicking on [Code](https://github.com/bkerler/mtkclient) button. 
- Extract zip file, go into the folder.
- Press [Ctrl+l], type cmd [Enter] 
```
pip install -r requirements.txt
```

#### Get latest UsbDk 64-Bit  
- Install normal MTK Serial Port driver (or use default Windows COM Port one, make sure no exclamation is seen)  
- Get usbdk installer (.msi) from [here](https://github.com/daynix/UsbDk/releases/) and install it  
- Test on device connect using "UsbDkController -n" if you see a device with 0x0E8D 0x0003  
- Works fine under Windows 10 and 11 :D  

---------------------------------------------------------------------------------------------------------------  

## Usage  

### Boot into brom mode  
Once the mtk script is running, boot into brom mode by powering off device,  
press and hold either *vol up + power* or *vol down + power* and connect the phone.  
Once detected by the tool, *release the buttons*.  
  
  
### Using MTKTools via the graphical user interface:  
For the 'basics' you can use the GUI interface. This supports dumping partitions or the full flash for now. Run the following command:  
```bash
python mtk_gui
```

### Run multiple commands
```bash
python mtk script run.example
```
See the file "run.example" on how to structure the script file  
  
### Root the phone (Tested with android 9 - 12)  
  
1. Dump boot and vbmeta  
```bash
python mtk r boot,vbmeta boot.img,vbmeta.img
```

2. Reboot the phone
```bash
python mtk reset
```

3. Download latest [Magisk](https://github.com/topjohnwu/Magisk/releases)  

4. Install on target phone
- you need to enable usb-debugging via Settings/About phone/Version, Tap 7x on build number
- Go to Settings/Additional settings/Developer options, enable "OEM unlock" and "USB Debugging"
- Install magisk apk
```bash
adb install Magisk.apk
```
- accept auth rsa request on mobile screen of course to allow adb connection

5. Upload boot to /sdcard/Download
```bash
adb push boot.img /sdcard/Download
```

6. Start magisk, tap on Install, select boot.img from /sdcard/Download, then:  
- Copy to pc and rename to boot.patched  
```bash
adb pull /sdcard/Download/[DISPLAYED MAGISK PATCHED BOOT FILENAME HERE]
mv [DISPLAYED MAGISK PATCHED BOOT FILENAME HERE] boot.patched
```

7. If these two commands below doesnt work 
- Putting into FASTBOOT MODE 
```bash
adb reboot bootloader ## OR manually via buttons.  
```
- Unlocking bootloader (via fastboot)  
```bash
fastboot flashing unlock ## your's might be different
```
- Unlocking bootloader (if fastboot is unavailable/command is not known/hard bricked?)  
```bash
python mtk e metadata,userdata,md_udc
python mtk da seccfg unlock
```

8. Flash Magisk patched `boot.patched`  
```bash
python mtk w boot,vbmeta boot.patched,vbmeta.img.empty
```
- If ^ command didn't work, rename your device's `vbmeta.img` to `vbmeta.img.empty` then execute again..  
```bash
python mtk w boot,vbmeta boot.patched,vbmeta.img.empty
```

9. Reboot the phone  
```bash
python mtk reset
```

10. Disconnect usb cable and enjoy your rooted phone :) 
   

## Troubleshooting  
- Struggle to get phone detected by pc in mtkclient?  

:: Phone must be switched off.  
:: Could be bad a usb cable or improper connection to USB port of pc/phone.  
:: Disconnect and connect again..  
 
- If command sent by 2nd terminal fails and show some error message, means it probably worked.  

## Credits   
- kamakiri [xyzz]   
- linecode exploit [chimera]   
- Chaosmaster   
- Geert-Jan Kreileman (GUI, design & fixes)   
- All contributors   
[MTKClient](https://github.com/bkerler/mtkclient)  
