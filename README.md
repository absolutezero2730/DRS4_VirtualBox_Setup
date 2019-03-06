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
   + Browse to the System tab. Under the Processor tab, I would increase it to at least 3 CPUs. 
   + Last, go to the Storage tab. In the controller section you just click on the following Host drive Disk. You can then see a CD symbol from the top-right of the panel. Click it and select "choose a virtual CD/DVD disk File..." Find the Ubuntu16.04-Disktop from the selecting path folder. That is, the file you download from the Ubuntu website. Now just click <b>OK</b> and finish the settings. 
5. Start the virtual machine. Finish the Ubuntu installation and re-boot it. This may take a while. 
