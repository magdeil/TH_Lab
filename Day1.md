<div align="center">
  <img src="https://rivanit.com/assets/logo-DaYZ0U1G.png" alt="Logo" title="TH_Lab Logo"/> <h1> Rivan Cyber Training Institute </h1>
</div>

# 📘 DAY 1 — Take Home Laboratory

![Day](https://img.shields.io/badge/Day-1-blue)
![Lab](https://img.shields.io/badge/Lab-TH_Lab-blueviolet)

---

![{5802C41E-B0D1-43ED-A2B7-9B83F70A6C26}](https://github.com/user-attachments/assets/1f579574-5384-4dbb-9df6-c0973ae0af26)


| Switch Port | Device Type | Description       |
|-------------|-------------|-------------------|
| 0/1/1      | Telephony   | Cisco IP Phone    |
| 0/1/3      | Camera      | Security Camera   |
| 0/1/5      | Access Point| Wireless AP       |
| 0/1/7      | PC          | Workstation       |
| Console    | Console Cable to PC| Console Cable|

# 🔧 Connecting to a Cisco Device Using SecureCRT (Serial Connection)

![SecureCRT Icon](https://img.shields.io/badge/SecureCRT-Serial%20Connection-blue)

Follow these steps to establish a console session via RS232 using SecureCRT.

---

## 🔹 Step 1: Launch SecureCRT

- Double-click the **SecureCRT icon** on your desktop to open the application.

---

## 🔹 Step 2: Open Quick Connect

- Click on the **“Quick Connect”** button (🔌 icon) at the top left of the SecureCRT window.

---

## 🔹 Step 3: Select Protocol

- In the **Quick Connect** window:
  - Set **Protocol** to `Serial`.

---

## 🔹 Step 4: Select Serial Port

- Under **Port**, choose the correct COM port connected to your device.
  - Common example: `COM3`, `COM4`, etc.
  - Use *Device Manager* if unsure which COM port is used.

---

## 🔹 Step 5: Configure Serial Settings

Set the following serial parameters:

- **Baud rate**: `9600`
- **Data bits**: `8`
- **Parity**: `None`
- **Stop bits**: `1`
- **Flow control**: `None`

These are standard settings for Cisco console access.

---

## 🔹 Step 6: Start Session

- Click **Connect** to start your serial console session.
- If the device is powered and connected properly, you'll see the boot sequence or command prompt.

---


## 🔹 Below are the Step by Step Screenshots:

![{FD9E20A0-7D14-4EA7-A8F2-EF0B52532E2F}](https://github.com/user-attachments/assets/b773fdb2-bfd8-4d22-9b37-75544a9822d7)
![{EE65AD31-5077-4141-BA6C-A6C580ECF27B}](https://github.com/user-attachments/assets/12f814f6-3e7b-41ca-91b9-42043296991a)
![{4C430601-8BFC-4293-A68A-EB7943DFBF34}](https://github.com/user-attachments/assets/565e1334-a162-4577-ad50-b0e7c76987b9)

# 🛠️ Task 1: Physical Ports Check

![Task](https://img.shields.io/badge/Task-Physical%20Ports%20Check-orange)

### 🔌 Power over Ethernet (PoE) Status

![PoE Status](https://img.shields.io/badge/PoE-Status-brightgreen)
  
```cisco
show power inline 
```

<b>  *SAMPLE OUTPUT:*  </b>


### Power Supply Status
| PowerSupply | SlotNum. | Maximum | Allocated | Status   |
|-------------|----------|---------|-----------|----------|
| INT-PS      | 0        | 88.000  | 28.800    | PS GOOD  |
### Interface Power Allocation
| Interface | Config | Device   | Powered | PowerAllocated |
|-----------|--------|----------|---------|----------------|
| Fa0/1/0   | auto   | Unknown  | Off     | 0.000 Watts    |
| Fa0/1/1   | auto   | IEEE-2   | On      | 7.000 Watts    |
| Fa0/1/2   | auto   | Unknown  | Off     | 0.000 Watts    |
| Fa0/1/3   | auto   | IEEE-2   | On      | 6.400 Watts    |
| Fa0/1/4   | auto   | Unknown  | Off     | 0.000 Watts    |
| Fa0/1/5   | auto   | IEEE-4   | On      | 15.400 Watts   |
| Fa0/1/6   | auto   | Unknown  | Off     | 0.000 Watts    |
| Fa0/1/7   | auto   | Unknown  | Off     | 0.000 Watts    |

# 🧪 Task 2: VLAN Checking and Configuration

![Level](https://img.shields.io/badge/Level-Intermediate-yellow)
![Device](https://img.shields.io/badge/Device-Cisco%20Switch-blue)
![Focus](https://img.shields.io/badge/Focus-VLAN%20Configuration-critical)
![Type](https://img.shields.io/badge/Environment-Enterprise%20%26%20HomeLab-lightgrey)

---

## 📌 Objective

To understand the purpose of VLANs in enterprise and home network environments, and perform VLAN creation and verification using Cisco CLI commands.

---

## 💡 Why Do Companies Need VLANs?

> **Virtual LANs (VLANs)** allow organizations to segment a physical network into multiple logical networks.  
This improves:
- **Security** – Isolates sensitive data traffic (e.g., VoIP or video streams)
- **Performance** – Reduces broadcast domains, improving network efficiency
- **Manageability** – Simplifies network management through logical grouping

---



Run the following command to verify VLANs on enterprise Cisco switches:
```cisco
show vlan brief
```
Use the following command to view VLANs on a home-lab enterprise switch:
```cisco
show vlan-switch
```
## We need at least 4 VLANS and 4 Switched Vlan Interface:
```cisco
config t
vlan 1
name default
vlan 10
name RIVANWIFI
vlan 50
name RIVANVIDEO
vlan 100
name RIVANVOIP
exit
exit
show vlan-switch
```


# 🧪 Task 3: LAN/Ethernet Ports to VLAN Reassignment

![Level](https://img.shields.io/badge/Level-Intermediate-yellow)
![Function](https://img.shields.io/badge/Function-Port%20VLAN%20Assignment-blue)
![CLI](https://img.shields.io/badge/CLI-Cisco%20IOS-lightgrey)

## ⚙️ VLAN Port Assignment Configuration

Enter global configuration mode and assign VLANs to switchports:

```bash
configure terminal
interface FastEthernet0/1/1 
 switchport mode access
 switchport voice vlan 100
interface FastEthernet0/1/3 
 switchport mode access
 switchport access vlan 50
interface FastEthernet0/1/5 
 switchport mode access
 switchport access vlan 10
interface FastEthernet0/1/7 
 switchport mode access
 switchport access vlan 1
end
show vlan-switch
```

# 🧪 Task 4: Switch VLAN Interface (SVI) Configuration

![Level](https://img.shields.io/badge/Level-Intermediate-yellow)
![Focus](https://img.shields.io/badge/Focus-Switch%20Virtual%20Interfaces-blue)
![Device](https://img.shields.io/badge/Device-Cisco%20Switch-lightgrey)

## 📖 Concept Overview

- **VLANs** act like **folders** that logically separate different types of traffic.
- **SVIs** act like **names for those folders** to help the switch identify and route between them.
- Each VLAN should have a corresponding SVI with an IP address for network management and Layer 3 communication.

```bash
configure terminal
interface Vlan1
 no shutdown
 ip address 10.28.1.1 255.255.255.0
 description DEFAULT
interface Vlan10
 no shutdown
 ip address 10.28.10.1 255.255.255.0
 description RIVANWIRELESS
interface Vlan50
 no shutdown
 ip address 10.28.50.1 255.255.255.0
 description RIVANCAMS
interface Vlan100
 no shutdown
 ip address 10.28.100.1 255.255.255.0
 description RIVANVOIP
end
```

# 🧪 Task 5: Preparing Devices for DHCP IP Address Assignment

![Level](https://img.shields.io/badge/Level-Intermediate-yellow)
![Focus](https://img.shields.io/badge/Focus-DHCP%20Preparation-blue)
![Protocol](https://img.shields.io/badge/Protocol-DHCP-lightgrey)

## 💡 What is DHCP?

> **DHCP (Dynamic Host Configuration Protocol)** is a network protocol that automatically assigns IP addresses, subnet masks, default gateways, and other configuration information to devices on a network.

### ✅ Why DHCP is Important?

- **Automation**: Reduces manual IP configuration errors.
- **Efficiency**: Saves time in large environments.
- **Centralized Management**: All IP assignments can be managed from one DHCP server.
- **Dynamic Allocation**: IPs are reused when devices disconnect.

---

## 🧰 Requirement: MAC Address

Before a DHCP server can assign an IP address, it needs to identify the device through its **MAC (Media Access Control) address**, a unique hardware identifier.
## 🔎 How to Retrieve MAC Addresses
```bash
show mac
```
or 
```cisco
show mac-address-table
```

## *Sample Output*

| Destination Address   | Address Type | VLAN  | Destination Port          | 
|-----------------------|--------------|-------|---------------------------|
| `0027.0d5e.2562`     | **Self**     | 1     | `Vlan1`                   | 
| `6899.cda1.c909`      | Dynamic      | 1     | `FastEthernet0/1/1`       | 
| `a066.10b8.faff`      | Dynamic      | 1     | `FastEthernet0/1/7`       | 
| `0027.0d5e.2562`     | **Self**     | 10    | `Vlan10`                  |
| `881d.fc95.1fa4`      | Dynamic      | 10    | `FastEthernet0/1/5`       | 
| `001a.070b.4735`      | Dynamic      | 50    | `FastEthernet0/1/3`       |
| `0027.0d5e.2562`     | **Self**     | 50    | `Vlan50`                  |
| `0027.0d5e.2562`     | **Self**     | 100   | `Vlan100`                 |
| `6899.cda1.c909`      | Dynamic      | 100   | `FastEthernet0/1/1`       |


# 🧩 Task 6: Prepare the DHCP Server

![Level](https://img.shields.io/badge/Level-Intermediate-yellow)
![Focus](https://img.shields.io/badge/Focus-DHCP%20Preparation-blue)
![Protocol](https://img.shields.io/badge/Protocol-DHCP-lightgrey)

```cisco
config t
ip dhcp Excluded-add 10.28.1.1 10.28.1.100
ip dhcp Excluded-add 10.28.10.1 10.28.10.100
ip dhcp Excluded-add 10.28.50.1 10.28.50.100
ip dhcp Excluded-add 10.28.100.1 10.28.100.100
ip dhcp pool DEFAULT
   network 10.28.1.0 255.255.255.0
   default-router 10.28.1.1
   domain-name DEFAULT.COM
   dns-server 10.28.1.10
ip dhcp pool RIVANWIFI
   network 10.28.10.0 255.255.255.0
   default-router 10.28.10.1
   domain-name RIVANWIFI.COM
   dns-server 10.28.1.10
ip dhcp pool RIVANCAMS
   network 10.28.50.0 255.255.255.0
   default-router 10.28.50.1
   domain-name RIVANCAMS.COM
   dns-server 10.28.1.10
ip dhcp pool RIVANVOIP
   network 10.28.100.0 255.255.255.0
   default-router 10.28.100.1
   domain-name RIVANVOIP.COM
   dns-server 10.28.1.10
   option 150 ip 10.28.100.1   
  end
```

# 🎯 Special Case: Reserved IP for Security Cameras
Some security devices like IP Cameras require a reserved (static) IP address provided by DHCP..

```cisco
config t
ip dhcp pool SECURITYCAMERA
 host 10.28.50.8 255.255.255.0
 client-identifier 001a.070b.4735
 default-router 10.28.50.1
end
```

# 🛠️ Task 7: Super Call Center Setup

![Cisco Certified](https://img.shields.io/badge/Cisco-Configuration-blue?logo=cisco&style=for-the-badge)
![Voice Setup](https://img.shields.io/badge/Voice_Call_Center-Setup-success?style=for-the-badge)

<b>*Change the Underline to the mac-address of the Ephone-8945 on FastEthernet 0/1/1*</b>
```cisco
config t   
no telephony-service
telephony-service
   no auto assign
   no auto-reg-ephone
   max-ephones 5
   max-dn 20
   ip source-address 10.28.100.1 port 2000
   create cnf-files
ephone-dn 1
  number 2811
ephone-dn 2
  number 2822
ephone-dn 3
  number 2833
ephone-dn 4
  number 2844
ephone-dn 5
  number 2855
ephone-dn 6
  number 2866
ephone-dn 7
  number 2877
ephone-dn 8
  number 2888
 ephone-dn 9
   number 2899
ephone-dn 10
 number 2898
Ephone 1
  Mac-address ____.____.____ 
  type 8945
  button 1:8 2:7 3:6 4:5
  restart
end
```

# 🛠️ Task: Configure SVI for Voice Setup

![Cisco Certified](https://img.shields.io/badge/Cisco-Configuration-blue?logo=cisco&style=for-the-badge)
![Voice Setup](https://img.shields.io/badge/Voice_SVI-Setup-success?style=for-the-badge)

```cisco
config t
dial-peer voice 69 voip
 service rivanaa out-bound
 destination-pattern 2869
 session target ipv4:10.28.100.1
 incoming called-number 2869
 dtmf-relay h245-alphanumeric
 codec g711ulaw
 no vad
!
telephony-service
 moh "flash:/en_bacd_music_on_hold.au"
!
application
 service rivanaa flash:app-b-acd-aa-3.0.0.2.tcl
  paramspace english index 1        
  param number-of-hunt-grps 2
  param dial-by-extension-option 8
  param handoff-string rivanaa
  param welcome-prompt flash:en_bacd_welcome.au
  paramspace english language en
  param call-retry-timer 15
  param service-name rivanqueue
  paramspace english location flash:
  param second-greeting-time 60
  param max-time-vm-retry 2
  param voice-mail 1234
  param max-time-call-retry 700
  param aa-pilot 2869
 service rivanqueue flash:app-b-acd-3.0.0.2.tcl
  param queue-len 15
  param aa-hunt1 2800
  param aa-hunt2 2877
  param aa-hunt3 2801
  param aa-hunt4 2833
  param queue-manager-debugs 1
  param number-of-hunt-grps 4
```

# 📞 Task: CellPhone to IP Phone Connection (SIP Configuration)

![Cisco Certified](https://img.shields.io/badge/Cisco-Configuration-blue?logo=cisco&style=for-the-badge)
![SIP Setup](https://img.shields.io/badge/SIP_Connection-Setup-success?style=for-the-badge)

```cisco
conf t
 voice service voip
  allow-connections h323 to sip
          
  allow-connections sip to h323
  allow-connections sip to sip
  supplementary-service h450.12
 sip
   bind control source-interface fa0/0
   bind media source-interface fa0/0
   registrar server expires max 600 min 60
!
 voice register global
  mode cme
  source-address 10.28.100.1 port 5060
  max-dn 12
  max-pool 12
  authenticate register
  create profile sync
 voice register dn 1
   number 2823
   allow watch
   name 2823
 voice register dn 2
   number 2824
   allow watch
   name 2824
!
  voice register pool 1
    id mac 76e5.5268.cba5
    number 1 dn 1
    dtmf-relay sip-notify
    username 2823 password 2823
    codec g711ulaw
!
  voice register pool 2
    id mac ____.____.____
    number 1 dn 2
    dtmf-relay sip-notify
    username ____ password ____
    codec g711ulaw
	!
```
