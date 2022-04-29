# vChromebook
Chromebook VM for Windows devices made easier, running on QEMU.

# Requirements
- 4GB of RAM
- At least 8.1GB of storage
- Latest release of Windows 10, no other OS
- Windows Hypervisor Platform

# How to use
First, download vChromebook from [here](https://drive.google.com/file/d/1fMEW_0HI0ghsvvhyjZsy9EpY86UQGhKX/view?usp=sharing). Once you have downloaded it, extract it, and run "install.exe". Once finished installing, open "Edit the system enviroment variables", look for PATH, and add this:
```
C:\Program Files (x86)\vChromebook\files
```
If you have not turned on Windows Hypervisor Platform, search up "Turn windows features on or off", then look for Windows Hypervisor Platform, and check it. This is done for acceleration of ChromeOS.

Now run CMD or press Win+R, and type in "chromebook". Wait about a few seconds, and if you see a screen, it works!

Once you're done, turn off the VM by clicking on the bottom right corner and pressing the off button. It should return to normal.

# Notes
Running vChromebook takes a lot of space (unless you have a terabyte or two of storage), and is also slow. You cannot speed this up unless you use another QEMU accelerator, like HAXM or GVM. To do this, open `C:\Program Files (x86)\vChromebook\files`, and replace the needed files. Then open boot.bat in a text editor and add "-accel gvm" or "-accel haxm" to the command.
