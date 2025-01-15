<h1>Network Segmentation Basics VLANs and Inter VLAN Communication</h1>


<h2>Description</h2>
<br>This project aims to provide hands-on experience with VLAN segmentation and inter-VLAN routing using Cisco devices. The goal was to set up a simple yet effective network that segregates departments into different VLANs—HR, Sales, and IT—while ensuring communication between the VLANs. The focus was on learning the key concepts behind VLAN creation, trunking, and configuring subinterfaces on the router to enable inter-VLAN communication. The project demonstrates how a network can be organized logically using VLANs to improve performance, security, and network management.

Learning to configure VLANs and set up inter-VLAN routing is crucial in real-world networking. It’s a skill that enables network administrators to control traffic flow between various parts of the organization, enhancing network security and performance. Mastering these foundational skills is important for handling real-world network infrastructure where businesses must separate their departments or user groups while maintaining communication across those groups when required.<br />


<h2>Languages and Utilities Used</h2>

- <b>Cisco Packet Tracer</b> 


<h2>Environments Used </h2>

- <b>macOS</b>

<h2>Walk-through:</h2>
<br>
<br>
<p align="left">
<b> The project begins by building the core network topology. Six computers are connected to a single switch, which is then linked to a router. Each computer is assigned to a specific FastEthernet (Fa0) port on the switch. For instance, PC0 is connected to Fa0/1, PC1 to Fa0/2, and so on, with PC5 connected to Fa0/6. The switch is subsequently connected to the router using the switch’s GigabitEthernet (Gi0/1) interface and the router’s Gi0/0 interface.

 With the topology in place, the next step involves planning VLANs. Three VLANs are created to segment the network for different departments: VLAN 10 for HR, VLAN 20 for Sales, and VLAN 30 for IT. Each VLAN is assigned a unique subnet for logical addressing. VLAN 10 uses the subnet 192.168.10.0/24, VLAN 20 is allocated 192.168.20.0/24, and VLAN 30 is assigned 192.168.30.0/24. These subnets will help organize and manage the network efficiently.
<b/>
  <img src="https://i.imgur.com/jtJMSMX.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br>
<br>

<b> With the planning phase complete, we proceed to configure the VLANs on the switch. To begin, we access global configuration mode by running the commands enable and then configure terminal. Within this mode, we create and name each VLAN. For VLAN 10, the commands vlan 10, name HR, and exit are used to create the VLAN, assign it the name "HR" for the Human Resources department, and exit VLAN configuration mode.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/78Dg5y6.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Similarly, we configure VLAN 20 by running the commands vlan 20, name Sales, and exit, which establish VLAN 20, name it "Sales" for the Sales department, and conclude the configuration.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/O07WwqR.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Finally, VLAN 30 is set up using the commands vlan 30, name IT, and exit to create the VLAN, name it "IT" for the Information Technology department, and exit configuration. These steps ensure the network is logically segmented according to departmental requirements.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/1gWmqfK.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> After creating the VLANs, the next step is to assign switch ports to their respective VLANs, which is done in global configuration mode. For VLAN 10, we use the commands interface range fa0/1-2, switchport mode access, switchport access vlan 10, and exit. These commands select the range of interfaces fa0/1 and fa0/2, set the mode to access for single VLAN communication, and assign these interfaces to VLAN 10 before exiting configuration mode.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/clmMR2J.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Similarly, for VLAN 20, the commands interface range fa0/3-4, switchport mode access, switchport access vlan 20, and exit are used to configure ports fa0/3 and fa0/4 as access ports assigned to VLAN 20.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/mzOYpuZ.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Lastly, the ports assigned to VLAN 30, fa0/5 and fa0/6, are configured with the commands interface range fa0/5-6, switchport mode access, switchport access vlan 30, and exit. This setup ensures that each VLAN is mapped to its designated interfaces on the switch, isolating traffic based on departmental VLAN assignments.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/8EpBnvA.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> SHOW VLAN DO STEP.<b/> 
<br>
<br>
  <img src="" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> To enable inter-VLAN routing, we need to configure subinterfaces on the router for each VLAN. First, access the router's global configuration mode by using the commands enable and configure terminal. For VLAN 10, enter the commands interface g0/0/0.10, encapsulation dot1Q 10, ip address 192.168.10.1 255.255.255.0, and exit. This creates a subinterface for VLAN 10, assigns it to the correct VLAN with dot1Q encapsulation, and sets its IP address as the default gateway for the devices in this VLAN..<b/> 
<br>
<br>
  <img src="https://i.imgur.com/EXOt1jV.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Repeat the process for VLAN 20 by running interface g0/0/0.20, encapsulation dot1Q 20, ip address 192.168.20.1 255.255.255.0, and exit. This establishes the subinterface and gateway IP for the Sales department (VLAN 20)..<b/> 
<br>
<br>
  <img src="https://i.imgur.com/YIgb6GR.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Finally, configure VLAN 30 by entering interface g0/0/0.30, encapsulation dot1Q 30, ip address 192.168.30.1 255.255.255.0, and exit. This sets up the subinterface and default gateway for the IT department (VLAN 30).<b/> 
<br>
<br>
  <img src="https://i.imgur.com/FC5FNSH.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> At this point, if we run the show ip interface brief command, we’ll see that the subinterfaces are marked as administratively down.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/GYxSvLh.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> To bring them online, enter global configuration mode and use the command interface g0/0/0 followed by no shutdown. This command brings the physical interface up, which allows the subinterfaces to activate as well. After this, running the command again will show that all interfaces are now up and ready for operation, ensuring the network functions as expected across all VLANs.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/amXV6sW.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
  <img src="https://i.imgur.com/k7ue1dX.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> To configure the default gateways for each VLAN, start by setting the default gateway for VLAN 10 (192.168.10.1). For PC0, go to the desktop settings, navigate to IP Configuration, and assign it 192.168.10.2. Then for PC1, assign it 192.168.10.3.<b/> 
<br>
<br> 
  <img src="https://i.imgur.com/F1SB75F.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
  <img src="https://i.imgur.com/lTuJ7ja.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Next, for VLAN 20 (192.168.20.1), go to PC2, access the desktop settings, and assign 192.168.20.2. For PC3, set it to 192.168.20.3..<b/> 
<br>
<br>
  <img src="https://i.imgur.com/JIJviHR.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
  <img src="https://i.imgur.com/tuZfNms.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Finally, for VLAN 30 (192.168.30.1), click on PC4, go to the desktop settings, and assign 192.168.30.2. For PC5, assign it 192.168.30.3. This will ensure that each computer in the respective VLANs is correctly pointed to the router’s subinterface for inter-VLAN routing.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/Cz8Ngxe.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
  <img src="https://i.imgur.com/8CIhp5M.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> At this stage, we should have confirmed connectivity within the same VLANs, but not across VLANs. To verify this, we start by testing connectivity within VLAN 10. From PC0, open the command prompt and run ping 192.168.10.3. As shown in the screenshot, we receive ping replies, indicating successful connectivity between PC0 and PC1 in VLAN 10.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/sjSnzIP.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> However, there should not yet be any connectivity between different VLANs. To test this, continue on PC0 and attempt to ping PC2 in VLAN 20 using ping 192.168.20.2. As seen in the screenshot, there is no reply, confirming that there is no connectivity between VLAN 10 and VLAN 20.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/cvfitkY.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> Similarly, from PC0, try pinging PC4 in VLAN 30 with the command ping 192.168.30.2. Again, there is no reply, confirming that there is no connectivity between VLAN 10 and VLAN 30.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/7Mn0tvu.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> To enable communication between VLANs, we need to configure trunking on the switch interface. To do this, we enter global configuration mode on the switch and execute the command interface g0/1, followed by switchport mode trunk. Once the command is applied, the output will confirm that the interface is now in trunk mode.

Allowing VLANs to communicate with one another is crucial for an organization that needs segmented network traffic but still requires connectivity between departments or groups. For instance, an HR VLAN may need to communicate with a Sales VLAN for collaborative projects, or IT may need access to both HR and Sales to manage infrastructure and provide support. By enabling inter-VLAN routing, organizations can ensure that data and services flow between different VLANs while maintaining the security and performance benefits of VLAN segmentation. This routing capability is fundamental for managing large and complex networks, as it provides controlled access to resources and reduces unnecessary congestion on the network.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/dtpk3pc.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

<b> We can now test connectivity by going to PC0 and pinging the same computers as before. First, ping VLAN 20 by entering ping 192.168.20.2, and then ping VLAN 30 with ping 192.168.30.2. As shown in the screenshot, we now receive ping replies from both VLANs, confirming that communication between the VLANs is working as expected.<b/> 
<br>
<br>
  <img src="https://i.imgur.com/Ougw5fz.png" height="80%" width="80%" alt="Network Segmentation Basics VLANs and Inter VLAN Communication Steps"/>
<br />
<br />

