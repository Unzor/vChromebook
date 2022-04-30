# vChromebook
Chromebook VM for Windows devices made easier, running on QEMU.

# Requirements
- 4GB of RAM
- At least 8.1GB of storage
- Latest release of Windows 10, no other OS
- Windows Hypervisor Platform

# How to use
First, download vChromebook from [here](https://drive.google.com/u/0/uc?id=1I_3073gPdl2zFFill6e8JKJM83hp5lm0&export=download). Once you have downloaded it, extract it, and run these commands on an admin-priveledged command prompt:
```
mv files "C:\Program Files (x86)\vChromebook"
cd C:\Program Files (x86)\vChromebook
tar -xf chromeos_14516.0.0_reven_recovery_dev-channel_mp-v2.bin.zip
mv chromeos_14516.0.0_reven_recovery_dev-channel_mp-v2.bin chromeos.bin
rm chromeos_14516.0.0_reven_recovery_dev-channel_mp-v2.bin.zip
```
Once finished installing, open "Edit the system enviroment variables", look for PATH, and add this:
```
C:\Program Files (x86)\vChromebook\files
```
If you have not turned on Windows Hypervisor Platform, search up "Turn windows features on or off", then look for Windows Hypervisor Platform, and check it. This is done for acceleration of ChromeOS.

Now run CMD or press Win+R, and type in "chromebook". Wait about a few seconds, and if you see a screen, it works!

When setting up ChromeOS, boot from USB.

Once you're done, turn off the VM by clicking on the bottom right corner and pressing the off button. It should return to normal.

# Notes
Running vChromebook takes a lot of space (unless you have a terabyte or two of storage), and is also slow. You cannot speed this up unless you use another QEMU accelerator, like HAXM or GVM. To do this, open `C:\Program Files (x86)\vChromebook\files`, and replace the needed files. Then open boot.bat in a text editor and add "-accel gvm" or "-accel haxm" to the command.
