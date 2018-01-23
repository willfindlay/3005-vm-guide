William Findlay's 3005 VM Setup
===============================
William Findlay's settings to get the COMP3005 VM up and running and user friendly.

VirtualBox Settings
-------------------
First you need to configure your VirtualBox network settings for your VM.
The prof's settings do not work properly. In fact, they prevent the VM from booting
altogether! **Damn it, Mengchi.**

To get this working, you need to do the following:

**VirtualBox** -> **Click on the 3005 VM** -> **Click Settings**<br/>
-> **Click Network** -> **Click Adpater 2** -> **Uncheck Enable Network Adapter**<br/>
-> **Click Adapter 1** -> **Open the DropDown** -> **Select NAT**<br/>
-> **Click Advanced** -> **Under ADAPTER TYPE Select PCnet-FAST III**<br/>
-> **Click Port Forwarding** -> **Click the + Symbol**

Once you have reached this step, simply make sure you have the following:

**Name: guestssh
Protocol: TCP
Host Port: 3005 or some other high number
Guest Port: 22**

Now, you should be ready to start your VM. ***Hurray!***
