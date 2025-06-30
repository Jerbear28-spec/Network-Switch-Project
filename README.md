
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
- "Smart/Web Managed" Network Switch
- Google Chrome (Used to configure settings on "web-managed" network switch)

<h2>Operating Systems Used </h2>

- Windows 10 Pro

<h1>Deployment and Configuration</h1>

<h3>Step 1: Install Wireshark on PC used for Monitoring Traffic</h3>
Navigate to https://www.wireshark.org/download.html to download Wireshark.

<h3>Step 2: Installation of Appropriate Network Switch</h3>
The next step is to ensure you have the appropriate network switch for this setup. This particular setup requires either a "smart-managed" or a "fully managed" switch that supports port mirroring. The switch I will be using in this demonstration is a "smart managed" switch that can be configured using a web browser of a device on the same subnet (my Windows 10 PC.) 

This switch has 5 ports:

- Port 1 will be used to connect the modem 
- Port 2 will be used to connect the router
- Port 3 will be used to connect to the PC with Wireshark installed (the packet sniffer).

<h3>Step 2: Manually configuring the Subnet of the PC</h3>
<h3>Step 3:</h3>
<h3>Step 4:</h3>
