# MyWInTweaks
Tweaking Windows

Cant change Profile Picture anymore.
Well. Thats easy to fix.
Task Scheduler -> Microsoft -> Windows -> Shell -> Enable CreateObjectTask

**Cannot get Store to download some Apps?**
> Task Scheduler -> Microsoft -> Windows -> Subscription -> Enable Both Entries if disabled

**Welp. cant Install and use WSL**
> Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Mup -> Turn it on

**Auto Regedit Backup is busted.**
> Task Scheduler -> Microsoft -> Windows -> Regedit -> Enable Entry if disabled

**I cant defrag anymore**
> Start Defrag Service -> Open Cmd as Admin -> chkdsk *drive*: /f /r -> N -> Y -> Restart

**I cant see the Internet Icon anymore**
> CMD as Admin -> sc config "RmSvc" start=manual

**Create new Recovery Partition**
- Download Windows ISO and unpack it to a folder.
- Open CMD as Admin -> 
- md c:\test -> dism /mount-image /imagefile:E:\UserFolders\Desktop\meow\sources\install.wim /index:1 /mountdir:C:\test\ /readonly
- Go to C:\test\Windows\System32\Recovery -> copy the winRe.wim -> C:\Windows\System32\Recovery -> paste
- and at last
reagentc /setreimage /path C:\windows\system32\recovery -> dism /unmount-image /mountdir:C:\test\ /discard -> reagentc /enable

**Other Store Fix**
Download https://www.tweaking.com/content/page/windows_repair_all_in_one.html
Select Portable and open it.
In the Program itself, select Repairs and continue.
Then Select all repairs and deselect them.
After that select
1. Register System Files, 2. Repair Firewall, 3. Repair Hosts File, 4. Repair Network, 5. Repair Proxy Settings, 6. Repair App Store (Complete Reset), 7. Window Component Storage.
After that give it some time, reboot and it should work again.

Fix Windows 11 Action Center.
1. Go to Services -> Enable CDPSvc

AMD Chipset Driver crashes after opening?
Option 1: Create New User -> Open the Exe and install it there..
Option 2: Create New User -> Download AMD Cleanup Utility -> Reboot into safemode -> download Windows Uninstall Troubleshooter -> Uninstall everything AMD -> Run AMD Cleanup and reboot -> Download Driver and open CMD as Admin -> Input: START /WAIT *Admin Driver exe* /S -> Enter and Wait.

0x80072EE7 in Windows Store
Open Regedit >> Computer\HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Dnscache and set Start to 2

Rant Section
my FUCKING SUBSYSTEM WONT WORK BUT I HAVE ALL FUCKING FEATURES INSTALLED
1. Im facing this atm. So basically. Fucking. Enable. No-Page Exection back on your Motherboard if u have it disabled...
2. Also enable any Virtual Device Things in Device Manager and set the Server Service to Startup Manual aswell as any HyperV Services
