### Installing Pintos and running in QEMU

_host platform independent procedure_

_all versions as of 2017-02-27_

* * *

#### Install VirtualBox

1. VirtualBox is an open-source [virtualizer](https://www.virtualbox.org/wiki/Virtualization). Essentially, it is an application running under you operating system (called the _host_) that allows you to run various other operating systems (called _guests_).

2. Open the downloads directory http://download.virtualbox.org/virtualbox/.

3. As of this writing, the latest version is 5.1.14. Open http://download.virtualbox.org/virtualbox/5.1.14/.

4. Download the installation image for your platform. Install.

5. Also download the guest extensions disc image *VBoxGuestAdditions_5.1.14.iso*. It's the same for all platforms.

#### Create an Ubuntu virtual machine

1. Open the desktop download site http://www.ubuntu.com/download/desktop. This is the _desktop_ version, rather than the _server_.

2. Download the latest 64-bit ISO image. As of this writing, that is Ubuntu 16.04.2 LTS. Read [here](https://wiki.ubuntu.com/LTS) about long-term support (LTS).

3. Open VirtualBox and create a new machine. Give it a name and select **Linux** and **Ubuntu 64-bit**.

4. Start the machine. When asked for the installation image, point to the ISO image you donwloaded and continue.

5. When asked to _Try_ or _Install_ Ubuntu, select _Install_. You can check the box to _"Download updates while installing Ubuntu"_. Choose to _"Erase disk and install Ubuntu"_. This is a virtual disk, not your hard drive. Confirm the installation when asked.

6. Create the username `pintos` and a password of your choice. Select _Log in automatically_. I suggest **Pintos Developer** as your name, **vb-ubuntu-pintos** as your computer's name, and **pintos2017** as password. The password doesn't have to be good, since this virtual machine will only be used for development on publically available code. _**Note:** Please, do not publish your solutions, since that degrades Pintos as an educational resource for others._

7. All installation defaults should be fine. Restart the machine when done.

#### Some housekeeping

1. Install the Ubuntu updates. There is a green button with an A in the vertical bar. Click on it, provide the password and let it install.

2. Open a terminal. Click on the topmost button on the left and start typing "termin...". Click on the Terminal app. When it opens, there will be a terminal button in the menu. Right-click and select "Lock to the tray". Next time you can open from there.

#### Install the guest additions

1. The virtual machine is called a _guest_. The extensions will give you, among other things, a resizeable display. The default resolution won't be useful for development. If you want, read more about them [here](https://www.virtualbox.org/manual/ch04.html).

2. Install the dynamic kernel module support (DKMS) framework. Execute the following commands:

   ```
   sudo apt-get update
   sudo apt-get upgrade
   sudo apt-get install dkms
  ```

3. Click on the small disk picture in the bottom bar of the virtual machine window. Click "Choose disk image" and select the _VBoxGuestAdditions_5.1.14.iso_ (downloaded earlier). Ubuntu will recognize that you want to install the Guest Additions. Agree to the installation.

4. After the installation, "eject" the virtual disk from the left-hand menu bar, or the same disc icon in the bottom bar, and restart the guest OS.

5. Now you can increase the resolution of the screen to something that is more convenient for development. Click the topmost button in the bar and start typing "displa...". Open the Displays app, adjust the screen resolution and click the (possibly partially hidden) button to apply the changes. Either accept the resolution or change it again. Don't get greedy with the resolution as it may load your CPU excessively.

#### Various tools

1. Open a terminal on your Ubuntu guest in VirtualBox.

2. Check if you have _cmake_ installed. This is a toolset for building and packaging software. If you want to know more, check out the [CMake](https://cmake.org/) webpage. If you don't have it, install it:

   ```
   which cmake
   sudo apt-get install cmake
   which cmake
   ```

3. Check if you have _git_ installed. This is a VCS. If you want to know more, check out the [git](https://git-scm.com/) webpage. If you don't have it, install it:
 
   ```
   which git
   sudo apt-get install git
   which git
   ```
   
4. Check if you have _QEMU_ installed. This is a virtualizer/**emu**lator. If you want to know more, check out the [QEMU](http://www.qemu-project.org/) webpage. If you don't have it, install it:

   ```
   which qemu-system-x86_64
   sudo apt-get install qemu
   which qemu-system-x86_64
   ```
