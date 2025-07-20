
<h1 align="center">Implementing a Managed Network Switch to Monitor All Traffic on a Home Network</h1>

![image](https://github.com/user-attachments/assets/4e26b68d-1817-49a9-b553-5f08876c22a8)


<h2>Project Overview</h2>
In this project, all network traffic that flows through the router of a home network will be monitored using a managed network switch that supports "port-mirroring." The traffic will be monitored on a Windows 10 PC using the packet sniffing software, "Wireshark." This particular setup has various possible applications, mostly related to network security.<br />

<h2>Visual Representation of Changes to Home Network Setup</h2>

<h3>Before (Typical Home Network Setup):</h3>

<h2 align="center">

![normalsetup](https://github.com/user-attachments/assets/cb9e02d9-5be2-49ad-94ba-127c2725463c)

</h2>

<h3>After Implementation of Network Switch:</h3>

<h2 align="center">

![network_diag_w_switch](https://github.com/user-attachments/assets/e26ebcc9-8d42-4767-97fb-c83862ce277e)

</h2>
 
<h2>Environments and Technologies Used</h2>

- "Web-Managed" Network Switch
- 3 Cat6 Ethernet Cables
- Wireshark (Packet Sniffer)
- Google Chrome (Used to configure settings on "web-managed" network switch)
- PingTools (Networking tools application for Android)
  
<h2>Operating Systems Used </h2>

- Windows 10 Pro
- Android 15

<h1>Step-by-step Deployment and Configuration</h1>

<h3>Step 1: Install Wireshark on PC that will be used as a traffic monitor</h3>

<p>
Navigate to https://www.wireshark.org/download.html to download Wireshark. Run the installation wizard using the default selections.
</p>

![image](https://github.com/user-attachments/assets/3f14212d-e9cb-4546-bceb-61ab891e327e)

<h3>Step 2: Installation of Appropriate Network Switch</h3>
<p>
The next step is to ensure you have the appropriate network switch for this setup. This particular setup requires either a "smart-managed" or a "fully-managed" switch that supports port mirroring. The switch used in this demonstration is a "smart managed" switch that can be configured using a web browser on a device that is on the same subnet (in this demonstration, a Windows 10 PC.) Specifically, I am using a Goalake Web-Managed Switch Model: GS105 V1.
</p>
   
![image](https://github.com/user-attachments/assets/38483e11-a8f4-4cb0-974f-51fc678a19be)

This particular network switch has 5 ports:

- Port 1 will be used to connect the modem 
- Port 2 will be used to connect the router
- Port 3 will be used to connect to the PC with the packet sniffer installed (Wireshark).

<p>
 This switch has a POE (power-over-ethernet) port, which can supply power to the switch. In this setup, the switch is powered by a separate power cable that is plugged into an outlet.
</p>

<h3>Step 3: Manually Configuring the Subnet of a Windows 10 PC</h3>
<p>
Open "Network and Sharing Center" and click "Change Adapter Settings" on the left.
</p>

![network and sharing](https://github.com/user-attachments/assets/5d4d876e-8184-4bc9-a5ff-c8a85799d6b4)

<p>
Right click on the Local Area Connection and click "Properties".
</p>

![rightclickconnection](https://github.com/user-attachments/assets/49582c72-5d1a-4723-8b7d-6eb0e5f72014)

<p>
 Click on Internet Protocol Version 4 and click "Properties" again.
</p>

![propertiespage](https://github.com/user-attachments/assets/440236e7-347e-42b6-9737-d37c2680fa95)

<p>
 Click on "Use the following IP address:" and manually enter in the following IP address and Subnet mask. This subnet configuration is unique to this particular switch, other "web-managed" switch models may use different subnet masks.
</p>

![image](https://github.com/user-attachments/assets/a7d15650-fa51-480d-accd-8e081feb5013)

<h3>Step 4: Enabling "Port-Mirroring" on Network Switch</h3>

<p>
 Using a web browser, navigate to the switches IP address, which in this case is "10.0.0.10"
</p>

![webnavigation](https://github.com/user-attachments/assets/003e1da5-4f90-42eb-a763-415bfe02cc6f)

<p>
 The switch's webpage will ask you to set a password the first time you access it. If you forget your password, you will have to reset the switch. This particular switch also supports "cloud-based" configuration. If this is enabled, the switch's settings can be manipulated using an application.
</p>

![switchpasswordlandingpage](https://github.com/user-attachments/assets/8fb050af-8f7c-4c8f-b758-ca39812c9c23)

<p>
 Navigate to the switch's "Port Mirroring" settings. Set the "Capture" port to port 3 (the port that connects to the PC) and set the "Captured" port to Port 2 (the port that connects the router.) This specific configuration will have the switch create a copy of every packet that goes through port 2 and send those copies to the PC via port 3.
</p>

![switchconfig](https://github.com/user-attachments/assets/483725d8-bae6-4897-9d10-24a01493a6b7)

<h3>Step 5: Monitor Network Traffic using Wireshark</h3>

<p>
 Open Wireshark. There should be an active connection showing traffic. This is all of the traffic going to and from the router (mirrored from port 2).
</p>

![wiresharkconnection](https://github.com/user-attachments/assets/b605a7ba-aef7-4c7f-b82c-765e5e24c474)

<p>
 Click on the connection that is showing traffic (not the loopback traffic capture.) This will display every packet that is coming from or going to your router.
</p>

![wiresharkcapture](https://github.com/user-attachments/assets/8687d576-4917-4e35-b389-2c2d55f4bea6)

<p>
 From here, traffic can be filtered by IPV6 addresses, protocols, and port numbers. Filters can also be combined using logical operators such as:
</p>

- and (&&)
- or (||)
- not (!)

<p>
 Monitoring this traffic can be extremely useful. This setup allows the user to see exactly what devices are doing on the network, which websites are being accessed, and which services are running in the background. From a securty perspective, the network can now be monitored for malware, unauthorized access, or suspicious connections that can potentially harm the network.
</p>

<h1 align="center">Demonstration</h1>

<h2>Step 1: Applying Filters for Network Traffic</h2>

<p>
A filter has been applied for ICMP traffic AND the IPV6 address of a specific device connected to the router (android phone.) This filter will only show the packets of ICMP traffic that has this IPV6 address as either a source or a destination. Doing so will demonstrate that this setup monitors both ingressive and regressive traffic.
</p>

<img width="815" height="734" alt="demonstratincapturefilters" src="https://github.com/user-attachments/assets/13cd0c3c-5e6d-4b9d-972e-aba547d6ba8f" />

<h2>Step 2: Creating Network Traffic</h2>

<p>
 Now using the free app PingTools, the android phone will now ping Google.com and Facebook.com repectively.
</p>

<h1 align="center">
 
![screensh1](https://github.com/user-attachments/assets/e8ec723c-6766-4e67-90a3-9d6feda16223)

![screensh2](https://github.com/user-attachments/assets/6acb7f2e-aead-4c3a-bc27-b66ab63e11d9)

</h1>

<h2>Step 3: Monitor Traffic</h2>

<p>
 The replies and requests of these pings should show up immediately, demonstrating that the setup works as intended.
</p>

<img width="567" height="669" alt="demonstrationafterping_2" src="https://github.com/user-attachments/assets/72336a98-51c0-4088-a152-31a754f08163" />

