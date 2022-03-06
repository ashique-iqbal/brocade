# brocade
https://extremeportal.force.com/ExtrArticleDetail?an=000087180


netinstall on VDX 6740 and 6940 via USB

These items will need to be downloaded before proceeding with the steps below for the netinstall process.
1. Open Mini Partition Manager (PartitionWizard.exe), right-click on the USB drive, then delete and create a new EXT2 partition:
**NOTE: If using a large USB stick larger than 4GB, format the USB to be 2-4GB to reduce formatting time**
2. Once EXT2 partition is created, remove and re-insert the USB. Then install and launch the Paragon ExtFS for Windows.
3. The newly formatted USB will be mounted automatically after which we can proceed with step 4. If not, choose the USB drive in Paragon and click "Mount"
4. Copy the boot file folder (based on hardware platform. castorXX for the 6740/6940-36S and rigelMor for the 6940-144S) and NOS firmware to the USB drive.
5. Click "Unmount" to unmount the USB drive (**IMPORTANT: Make sure the unmount process is completed before removing the USB from the computer. Windows may show it as 'hung' task, but the cache files are being written to the USB. Give it 3-5 mins to for the write to complete and USB to unmount.**)
6. Reboot the VDX and choose the option 3 below to enter the command shell

   `Hit ESC to stop autoboot:  5`

   `1) Start system.`
   `2) Recover password.`
   `3) Enter command shell.`

   `Option? 3`

   `Boot PROM password has not been set.`
7. Now, insert the USB stick into the switch and we are ready to perform the netinstall after booting into the boot prom.

   For the 6740/6940-36S:
   `=> usb reset 1` 
   
   For the 6940-144S:
   `=> usb reset 0`
8. 

