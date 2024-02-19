**FTOptix Ubuntu License Client Procedure**

This assumes that the FTOptixOptixApplicationUpdateService and the FTOptixEntitlementCli have been successfully installed on the Ubuntu target machine.
Also, it assumes you have your Entitlement key, a string of the form:
	
	XXXXX-XXXXX-XXXXX-XXXXX-XXXXX

If the target computer can reach the internet, then you can perform an online entitlement installation. If the target cannot reach the internet, then you must perform an offline entitlement installation.

#### Online

- a.	Open terminal on the target and go to the directory:
opt/Rockwell_Automation/FactoryTalk_Optix/FTOptixEntitlementCli

- b.	Run the command:

```bash
    sudo ./FTOptixEntitlementCli --onlineActivate --entitlementKey XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
```

where XXXXX-XXXXX-XXXXX-XXXXX-XXXXX is your numeric entitlement key.

**Note: there is a space before each command line parameter.**

- c.	Verify the entitlement by running the command:

```bash
    sudo ./FTOptixEntitlementCli --showInstalledEntitlement
```

You should see the entitlement code echoed back.



**End of online entitlement procedure.**

---

#### Offline

- a.	Open terminal on the target and go to the directory:
opt/Rockwell_Automation/FactoryTalk_Optix/FTOptixEntitlementCli

- b.	Run the command:

```bash
sudo ./FTOptixEntitlementCli --offlineActivate --entitlementKey XXXXX-XXXXX-XXXXX-XXXXX-XXXXX --outputActivationRequestFile ./
```

**Note: there is a space before each command line parameter.**

You should see the text echoed back: 

Exported the Activation Request file for entitlement XXXXX-XXXXX-XXXXX-XXXXX-XXXXX to ./XXXXX-XXXXX-XXXXX-XXXXX-XXXXX.req

- c.	Copy the req file to a computer that has internet access and run the Entitlement Manager.

- d.	Under Activate a new entitlement, click <Online>

- e.	Under Select an option, select Activate an entitlement for different device and press <Next>

- f.	Press the ellipses button to browse for the req file you generated in step b.

- g.	Press Activate.

- h.	Go to the folder where to the req file is and find a new file, with the form 

    XXXXX-XXXXX-XXXXX-XXXXX-XXXXX.ent

- i.	Copy the ent file to the target computer and run the command:

```bash
sudo ./FTOptixEntitlementCli --offlineActivate --entitlementFile ./XXXXX-XXXXX-XXXXX-XXXXX-XXXXX.ent
```

- j.	Verify the entitlement by running the command:

```bash
sudo ./FTOptixEntitlementCli --showInstalledEntitlement
```

You should see the entitlement code echoed back.
		
**End of offline entitlement procedure.**
