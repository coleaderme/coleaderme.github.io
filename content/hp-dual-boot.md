+++
title = "HP Dual Boot workaround"
date = "2025-06-21"
description = "Stupid HP Dual boot workaround"
tags = ['Boot', 'Dual', 'Grub', 'Windows', 'Fixes', 'efi', 'Stupid', 'workaround', 'Microsoft']
+++

# Fixes: HP ignoring linux boot manager (Grub)

1. cd `/boot/efi/EFI`

```sh
Grub/       # or some custom name
Microsoft/  # Windows
Boot/       # default fallback (no OS)
```

2. rename/backup Windows boot manager, and replace it with Grub.
```sh
mv Microsoft Microsoft.bak
mkdir Microsoft
cp Grub/* Microsoft/
```

3. custom boot entry for Windows to chainload from Grub.

Find UUID of **/boot/efi**: `sudo blkid`
eg. D064-C2CB

edit `sudo nano /etc/grub.d/40_custom`:
```sh
menuentry "Windows Boot Manager (manual)" {
    insmod part_gpt
    insmod fat
    search --no-floppy --fs-uuid --set=root UUID_HERE  # <= UUID of /boot/efi
    chainloader /EFI/Microsoft.bak/Boot/bootmgfw.efi   # the folder we renamed in step 2.
}
```

4. Update grub (requires **os-prober**)

edit `sudo nano /etc/default/grub`:
un-comment this line -->
`GRUB_DISABLE_OS_PROBER="false"`


```sh
sudo os-prober
sudo grub-mkconfig -o /boot/grub/grub.cfg
```

Now you'll be able to boot directly into grub,
there you can decide to boot into Windows/Linux.