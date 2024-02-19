**FTOptix Ubuntu Runtime Tools Procedure**


* Step 1. *Do NOT edit the /etc/gdm3/custom.conf file.* 

If you have previously uncommented the line: WayLandEnable=false
then you need to comment it again by adding a “#” to the beginning of the line and saving the file.


* Step 2. Run Software Updater (If you have the Ubuntu Desktop GUI) 


* Step 3. Open terminal and run:

```bash
sudo apt update
sudo apt upgrade -y
```

* Step 4. If you have a previous version, you must remove the prior Runtime Tools:

Run the command:

```bash
sudo rm -rf /opt/Rockwell_Automation/FactoryTalk_Optix
```

*Do NOT remove the opt/Rockwell_Automation directory or you will also delete any entitlements.*


* Step 5.	Copy the new Update Service and License Client installer script to the Ubuntu machine:

    a.	FTOptixApplicationUpdateService.Ubuntu_22_x64.1.3.0.110.sh

    b.	FTOptixEntitlementCli.Ubuntu_22_x64.1.3.0.113.sh



* Step 6.	Make the Update Service script executable.  In terminal, go to the directory with the scripts and run:

```bash
sudo chmod +x ./FTOptixApplicationUpdateService.Ubuntu_22_x64.1.3.0.110.sh
```

* Step 7.	Execute the script:

``` bash
sudo ./FTOptixApplicationUpdateService.Ubuntu_22_x64.1.3.0.110.sh
```

* Step 8.	Install the required dependencies (some or most may already be present):

```bash

sudo apt install libxcb1
sudo apt install libxcb-cursor0
sudo apt install libxcb-icccm4
sudo apt install libxcb-image0
sudo apt install libxcb-keysyms1
sudo apt install libxcb-randr0
sudo apt install libxcb-render0
sudo apt install libxcb-render-util0
sudo apt install libxcb-shape0
sudo apt install libxcb-shm0
sudo apt install libxcb-sync1
sudo apt install libxcb-xfixes0
sudo apt install libxcb-xkb1
sudo apt install libx11-xcb1
```

* Step 9.	Make the script executable.  In terminal, go to the directory with the scripts and run:

```bash
sudo chmod +x ./FTOptixEntitlementCli.Ubuntu_22_x64.1.3.0.113.sh
```

* Step 10.	Run the script:

```bash
sudo ./FTOptixEntitlementCli.Ubuntu_22_x64.1.3.0.113.sh
```

* Step 11.	Reboot the system.

* Step 12.	Check the service by opening terminal and running:

```bash
sudo systemctl status FTOptixApplicationUpdateService
```

You should see Active: active (running)


**End of Runtime Tools install procedure**
