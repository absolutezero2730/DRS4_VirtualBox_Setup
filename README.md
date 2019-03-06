# DRS4_VirtualBox_Setup
Running DRS4 Evaluation Board on Virtualbox (Linux) in Win7/8.X/10 (for beginners)
***
## Getting Start
1. From your Windows PC, download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads).
2. Search to the [Ubuntu.com](https://www.ubuntu.com/download/alternative-downloads). 
   + Download Ubuntu16.04-Disktop, or later version. Copy and past it from your /download folder to the /VirtualBox VMs folder.
3. Launch VirtualBox, click <b>New</b> and name your VM. Next drop down the <b>Type</b>, select "Linux." Drop down the <b>Version</b> and select "Ubuntu(64bit)."
   + Click <b>Next</b>. Set memory size to 4096MB or above. 
   + Click <b>Next</b>. Select "Create a virtual hard drive now," by default. Click <b>Next</b>, Hard drive file type "VDI" by default. 
   + Click <b>Next</b>. The Storage on physical hard drive is optional (prefer <b>Dynamically allocated</b>). 
   + Click <b>Next</b>. Set File size to at least 20GB or above. 
   + Click <b>Create</b>. 
4. Right click the created VM. Now click <b>Settings</b>. 
   + Click the Advanced tab from the General tab. To allow you copy and past between the two operating machines, select <b>Bidirectional</b> for both Shard Clipboard and Drag/Drops. 
   + Browse to the System tab. Under the Processor tab, I would like to increase it to at least 3 CPUs. 
   + Last, go to the Storage tab. In the controller section you just click on the following Host drive Disk. You can then see a CD symbol from the top-right of the panel. Click it and select "choose a virtual CD/DVD disk File..." Find the Ubuntu16.04-Disktop from the selecting path folder. That is, the file you download from the Ubuntu website. Now just click <b>OK</b> and finish the settings. 
5. Start the virtual machine. Finish the Ubuntu installation and re-boot it. This may take a while. 
6. After re-booting or restarting the VM, first open a terminal and type the command: su. You may have noticed that you can’t login to root account on Ubuntu. It is because root doesn’t actually have a password default set. 
   + Now type the following command: sudo passwd
   + Type new UNIX password: [Type the root password you want]
   + Retype new UNIX password: [Retype the root password you chosen before]. Now you can use the command: su
7. On the top of the list, Click <b>Device</b> and select "Insert Guest Additions CD Images..." Click <b>Run</b>. Then, you may need to enter the super user password. After things are done, press enter to close the window. 
8. Restart the VM. The screen resolution should be the same as your PC now.
9. Software Download for the DRS4 Evaluation Board requires the [wxWidgets package](http://www.wxwidgets.org/downloads/) and the [libusb-1.0 package](https://libusb.info/). Open a terminal, step-by-step: 
   + First activate the super user to change the working directory.
   ```
   su
   cd
   sudo apt search wxWidgets
   sudo apt search libwxgtk
   ```
   + From the searching list, find <b>libwxgtkX.X-XvX</b>, <b>libwxgtkX.X-XvX-dbg</b>, and <b>libwxgtkX.X-XvX-dev</b>. You will need to install these three packages. 
   ```
   sudo apt-get install libwxgtkX.X-XvX libwxgtkX.X-XvX-dbg libwxgtkX.X-XvX-dev
   ```
   + Search and install the libusb package. 
   ```
   sudo apt search libusb
   sudo apt-get install libusb-1.0-0
   sudo apt-get install libusb-1.0-0-dev
   ```
   + Now create a new folder for the [DRS4 software](https://www.psi.ch/drs/software-download). 
   ```
   cd /home/username/Documents
   mkdir DRS4
   cd DRS4
   ```
   + Download the source code tar ball from their [Dropbox](https://www.dropbox.com/sh/clqo7ekr0ysbrip/AACoWJzrQAbf3WiBJHG89bGGa?dl=0).
   ```
   wget -c https://www.dropbox.com/sh/clqo7ekr0ysbrip/AAAJ3eaYX7SmgKybswyaRZ6aa/drs-5.0.5.tar.gz
   ls
   tar -xzvf drs-5.0.5.tar.gz
   ls
   ```
   + Now change to the drs directory.
   ```
   cd drs-5.0.5
   make
   ```
10. After the compilation has finished, you can now connect the DRS4 evaluation board to your PC. When connecting the device, you might notice that Windows loads Winusb.sys automatically. This may take a few minutes. Please be patient. 
11. On the top of the list, Click <b>Device</b> again and select "USB." A new device named "DRS4 Evaluation Board" should have existed on the sub list. Click it. 
   + Run drscl and drsosc
   ```
   ./drscl
   ./drsosc
   ```
