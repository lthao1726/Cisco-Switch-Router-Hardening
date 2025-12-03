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
- <b>Storm Control </b>
- <b>ERR-DISABLE Recovery </b>
- <b>Secure Unused Ports (VLAN 999) </b>
- <b>Verify all Running-Config </b>

<h2>Program walk-through:</h2>

<p align="left">
SOHO Network:

[<img width="1580" height="884" alt="image" src="https://github.com/user-attachments/assets/00f7b73f-0dfd-430a-bfaf-dcfcf03c9a2f" />](https://i.imgur.com/ejQSMsl.png)

Step 1: We will implementing the Cisco Switch's basic system identity and security.

- <b>hostname </b>
- <b>no ip domain-lookup </b>
- <b>domain-name </b>
- <b>password-encryption </b>
- <b>enable secret </b>
- <b>banner motd </b>
  
<img width="901" height="407" alt="image" src="https://github.com/user-attachments/assets/be651034-64f1-4bbe-b0c8-620e197c0850" />

<br />
<br />
Step 2: Implementing Secure Management Access (AAA, SSH, VTY and console hardening)

 - <b>aaa new-model </b>
 - <b>aaa authentication login default local </b>
 - <b>crypto key generate rsa keys modulus 2048 </b>
 - <b>ip ssh version 2 </b>
 - <b>line cty 0 4 </b>
 - <b>transport input ssh </b>
   
<img width="902" height="441" alt="image" src="https://github.com/user-attachments/assets/ce808cf7-5085-4533-ad81-f9bd224f1610" />
<img width="904" height="303" alt="image" src="https://github.com/user-attachments/assets/5e00d990-6622-46ae-b585-e08f12a4d4e9" />

<br />
<br />
Step 3: Enabling NTP Synchronization and setting to Central Time zone  <br/>

- <b>ntp server </b>
- <b>clock timezone CST -6 0 </b>
<img width="905" height="258" alt="image" src="https://github.com/user-attachments/assets/3c59e0a5-4121-4282-983b-44b42c7046b0" />
<br />
<br />
Step 4: Enabling Syslog and SNMP  <br/>

- <b>logging host </b>
- <b>logging trap </b>
- <b>snmp-server </b>

<img width="882" height="125" alt="image" src="https://github.com/user-attachments/assets/e2190d5a-bf5e-478f-9385-c64ee314bde0" />

<br />
<br />
Step 5: Trunking & STP Hardening  <br/>

- <b>switchport mode trunk </b>
- <b>switchport trunk allowed vlan </b>
- <b>spanning-tree guard root </b>
- <b>spanning-tree guard loop (unsupported) </b>
- <b>spanning-tree portfast default </b>
- <b>spanning-tree bpduguard default (unsupported) </b>

<img width="859" height="318" alt="image" src="https://github.com/user-attachments/assets/945b5138-2ef4-4afe-8168-ac5a9a2b91c4" />

<br />
<br />
Step 6: DHCP Snooping   <br/>

- <b>ip dhcp snooping </b>
- <b>ip dhcp snooping vlan </b>

<img width="858" height="216" alt="image" src="https://github.com/user-attachments/assets/bf76db43-33c8-4d87-b145-1e3680416c2d" />

<br />
<br />
Step 7: Dynamic ARP Inspection   <br/>

- <b>ip arp inspection vlan </b>

<img width="748" height="279" alt="image" src="https://github.com/user-attachments/assets/8a821fd7-4b6f-4642-b31c-de32658ed6ca" />

<br />
<br />
Step 8: Storm Control   <br/>

- <br>storm-control broadcast level 10 </b>
- <br>storm-control multicast level 10 (unsupported) </b>
- <br>storm-control unicast level 10 (unsupported) </b>

<img width="898" height="195" alt="image" src="https://github.com/user-attachments/assets/0b8650e3-17a2-49a7-8a43-c6376d2e90be" />


<br />
<br />
Step 9: ERR-DISABLE Recovery  <br/>

- <b>errdisable recovery cause bpdugaurd (unsupported) </b>

<img width="884" height="228" alt="image" src="https://github.com/user-attachments/assets/4b3d8bea-32f0-43a8-a08d-13e4de14c538" />

<br />
<br />
Step 10: Secure Unused Ports with dead-end VLAN 999  <br/>

- <b>vlan 999 <br/>
- <b>interface range fa0/11-24 </b>
- <b>switchport mode access </b>
- <b>switchport access vlan 999 </b>
- <b>shutdown </b>

<img width="903" height="622" alt="image" src="https://github.com/user-attachments/assets/46d6aa56-75c0-4b81-a59f-f89854748768" />

<br />
<br />
Step 11: Finally we verify our switch configuration <br/>

- <b>show running-config </b>

<img width="700" height="895" alt="image" src="https://github.com/user-attachments/assets/4511fc18-e9ba-45e6-a18f-fc60dcfa6479" />
<img width="899" height="427" alt="image" src="https://github.com/user-attachments/assets/1643a131-6f58-41d2-9063-75f6043f295b" />

<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
