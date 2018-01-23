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

**Name: guestssh<br/>
Protocol: TCP<br/>
Host Port: 3005 or some other high number<br/>
Guest Port: 22**

Now, you should be ready to start your VM. ***Hurray!***

OracleVM Settings
-----------------
Now for the meat and potatoes. We're running ***Fedora Linux Server Edition***, so we
will be using the **yum** package manager here. Sounds delicious.

To get started, we need to install git.<br/>
<code>sudo yum install git</code> You will have to type your password here (oracle).

Now that we have git installed, let's configure it. If you have read my COMP3000 guide,
you'll know we need to do the following:

<code>
git config --global user.name "YOUR GITHUB USERNAME"<br/>
git config --global user.email "YOUR GITHUB EMAIL"<br/>
git config --global http.sslVerify false
</code>

With our git set up, we are almost ready to get going here. By now you may have noticed
that the sqlplus program we use to access and modify our DB doesn't support the arrow
keys! How dumb is that? Let's fix it.

To start, we are going to clone this repository into the root directory and cd into it:

<code>
git clone https://github.com/hanslub42/rlwrap<br/>
cd rlwrap
</code>

Now we need to install some other packages before we are ready to get going.

<code>
sudo yum install make autoconf automake
</code>

**Let's build autoconf!**

<code>
autoreconf --install<br/>
make<br/>
make install
</code>

Now, just run sqlplus with rlwrap sqlplus and you will have your arrow keys.<br/>
**BUT** if you are using ***my dotfiles*** you can just type sqlplus!

My Dotfiles
-----------

Use my dotfiles! They are sick. Just do the following:

<code>
cd ~<br/>
git clone https://github.com/HousedHorse/3005-vm-guide<br/>
cd 3005-vm-guide<br/>
cp ./.\* ..<br/>
**If you are not using termite, you are done.**<br/>
***If you are using termite:***<br/>
cp termite.terminfo ..<br/>
cd ~<br/>
tic termite.terminfo
</code>
