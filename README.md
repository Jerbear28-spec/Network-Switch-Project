
<h1 align="center">Implementing a Managed Network Switch to Monitor All Traffic on Home Network</h1>

![image](https://github.com/user-attachments/assets/4e26b68d-1817-49a9-b553-5f08876c22a8)


<h2>Project Overview</h2>
In this project, I will be using a managed network switch that supports "port-mirroring" to monitor all internet traffic that flows through my router in my home network. The traffic will be monitored on Windows 10 PC using the packet sniffing software, "Wireshark." This particular setup has various possible applications, mostly related to network security.<br />


<h2>Visual Representation of Changes to Home Network Setup</h2>

<h3>Before:</h3>

![normalsetup](https://github.com/user-attachments/assets/cb9e02d9-5be2-49ad-94ba-127c2725463c)

<h3>After Implementation of Network Switch:</h3>

![network_diag_w_switch](https://github.com/user-attachments/assets/e26ebcc9-8d42-4767-97fb-c83862ce277e)
 
<h2>Environments and Technologies Used</h2>

- Wireshark (Packet Sniffer)
- "Web-Managed" Network Switch
- Google Chrome (Used to configure settings on "web-managed" network switch)

<h2>Operating Systems Used </h2>

- Windows 10 Pro

<h1>Deployment and Configuration</h1>

<h3>Step 1: Install Wireshark on PC you wish to use as traffic monitor</h3>

<p>
Navigate to https://www.wireshark.org/download.html to download Wireshark. Run the installation wizard using the default selections.
</p>

![image](https://github.com/user-attachments/assets/3f14212d-e9cb-4546-bceb-61ab891e327e)

<h3>Step 2: Installation of Appropriate Network Switch</h3>
<p>
The next step is to ensure you have the appropriate network switch for this setup. This particular setup requires either a "smart-managed" or a "fully-managed" switch that supports port mirroring. The switch used in this demonstration is a "smart managed" switch that can be configured using a web browser of a device on the same subnet (in this case, a Windows 10 PC.) Specifically, I am using a Goalake Web-Managed Switch Model: GS105 V1.
</p>
   
![image](https://github.com/user-attachments/assets/38483e11-a8f4-4cb0-974f-51fc678a19be)

This particular network switch has 5 ports:

- Port 1 will be used to connect the modem 
- Port 2 will be used to connect the router
- Port 3 will be used to connect to the PC with the packet sniffer installed (Wireshark).

<h3>Step 3: Manually Configuring the Subnet of the Windows 10 PC</h3>
<p>
Open "Network and Sharing Center" and click "Change Adapter Settings" on the left
</p>

![network and sharing](https://github.com/user-attachments/assets/5d4d876e-8184-4bc9-a5ff-c8a85799d6b4)

<p>
Right click on the Local Area Connection and click "Properties".
</p>

![rightclickconnection](https://github.com/user-attachments/assets/49582c72-5d1a-4723-8b7d-6eb0e5f72014)

<p>
 Click on Internet Protocol Version 4 and click properties
</p>

![propertiespage](https://github.com/user-attachments/assets/440236e7-347e-42b6-9737-d37c2680fa95)

<p>
 Click on "Use the following IP address" and manually enter in the following IP address and Subnet mask. This subnet configuration is unique to this particular switch, different "web-managed" switch models may be different.
</p>

![image](https://github.com/user-attachments/assets/a7d15650-fa51-480d-accd-8e081feb5013)

<h3>Step 4: Enabling "Port-Mirroring" on Network Switch</h3>

<p>
 Using a web browser, navigate to "10.0.0.10"
</p>

![webnavigation](https://github.com/user-attachments/assets/003e1da5-4f90-42eb-a763-415bfe02cc6f)

<p>
 The switch's webpage will ask you to set a password the first time you access it. If you forget your password, you will have to reset the switch. 
</p>

(insert picture of switch password screen)

<p>
 Navigate to 
</p>

(picture of correct settings config)

<h3>Step 5: Monitor Network Traffic using Wireshark</h3>

<p>
 
</p>
