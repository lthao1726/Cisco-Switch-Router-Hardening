<h1>Cisco Switch+Router Hardening</h1>

<h2>Description</h2>

<b>All SOHO network and devices are up and functional, as the young network engineer who has been hired, implement Switch + Router hardening to improve the over security of the network.
</br>

<h2>Utility Used</h2>

- <b>Cisco Packet Tracer</b>

<h2>Technologies Implemented </h2>

- <b>One router and one switch are to be used (all CISCO products). </b>
- <b>Basic System Identity </b>
- <b>Secure Management Acces (AAA, SSH, VTY Hardening) </b>
- <b>NTP synchronization </b>
- <b>Syslog + SNMP </b>
- <b>Trunking & STP Hardening </b>
- <b>DHCP Snooping </b>
- <b>Dynamic ARP Inspection </b>
- <b>Port Security (Access Ports) </b>
- <b>Storm Control </b>
- <b>ERR-DISABLE Recovery </b>
- <b>Secure Unused Ports (VLAN 999) </b>
- <b>Verify all Running-Config </b>

<h2>Program walk-through:</h2>

<p align="left">
SOHO Network:

<img src="[[<img width="1580" height="884" alt="image" src="https://github.com/user-attachments/assets/00f7b73f-0dfd-430a-bfaf-dcfcf03c9a2f" />](https://i.imgur.com/ejQSMsl.png)](https://i.imgur.com/ejQSMsl.png)
" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Step 1: As the first step, we will implementing the Cisco Switch's basic system identity and security.

- <b>hostname </b>
- <no ip domain-lookup </b>
- <b>domain-name </b>
- <b>password-encryption </b>
- <b>enable secret <b>
  
<img src="https://i.imgur.com/5vfyuco.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 2: Creating and identifying the 3 different departments: Admin/IT, Finance/HR and Customer Service/ Reception.
 
<img src="https://i.imgur.com/WUAheAc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 3: Subnetting for the 3 departments with the IP address provided by the ISP: 192.168.1.0 and a Class C network: 255.255.255.0

Notice: The first IP address is the Network ID; and the last IP address is the Broadcast ID. Thus, allowing a range from 1-62 (62 available IP addresses).  <br/>
<img src="https://i.imgur.com/yb6FOG2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 4: Configuring the Switch, we used the built-in CLI to set up the 3 VLANs: VLAN10, VLAN20, VLAN30
   <br/>
<img src="https://i.imgur.com/ZiJPpwI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 5: Setting up the WAPs with the correct SSIDs according to each department and creating a WPA2-PSK security protocol password.  <br/>
<img src="https://i.imgur.com/dLOfXe2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 6: Creating the Sub-interfaces   <br/>
<img src="https://i.imgur.com/6CTLHfs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/t70jlQK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 7: Enabling DHCP and creating a pool of IP addresses for each of the departments.   <br/>
<img src="https://i.imgur.com/ICh1IJk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/M2Tg73y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 8: The finished product, showing all the different departments with their VLANs, DHCP IP addresses, WAPs and devices all connected.  <br/>
<img src="https://i.imgur.com/Wg2PGBa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Step 9: Verifying that the DHCP server is operating correctly by assigning the IP addresses for the devices.  <br/>
<img src="https://i.imgur.com/GIj642q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Final Step: Verifying that the Computers are on the network and are able to communicate with the other department. <br/>
<img src="https://i.imgur.com/FIJooKo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
