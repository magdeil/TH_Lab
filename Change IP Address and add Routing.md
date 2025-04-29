# How to Change IP Address in Windows PC  

![Windows Version](https://img.shields.io/badge/Windows-10%20%7C%2011-blue?logo=windows)  ![License](https://img.shields.io/badge/License-MIT-green)  ![Difficulty](https://img.shields.io/badge/Difficulty-Beginner-yellow)  ![Category](https://img.shields.io/badge/Category-Networking-orange)  

## Step 1: Open Network Connections
Press `Windows Key + R` to open the Run dialog box.  
Type `ncpa.cpl` and press Enter.  

![{240D82E9-9492-4812-B27B-9AB03618B89A}](https://github.com/user-attachments/assets/5e38aa9e-2d65-40d5-b82e-464bac0c0865)

This will open the Network Connections window.

![{FF1F2C58-9A9A-44D2-9BA7-03AF5485DB64}](https://github.com/user-attachments/assets/9fe93472-746e-4e57-9bac-ef733c7de9cc)

## Step 2: Select Your Network Adapter
Right-click on the network adapter you're currently using (`Ethernet`).  
Select `Properties` from the context menu.

![{6E61E2F3-0AC1-45A5-93D0-296B7E366884}](https://github.com/user-attachments/assets/9887ed45-89f9-4397-8ef0-f1c93e2595a5)

## Step 3: Open IPv4 Properties
In the Properties window:  
1. Scroll down and select `Internet Protocol Version 4 (TCP/IPv4)`.  
2. Click the `Properties` button.

![{008A37CA-CED0-4FA2-B573-B0808AE12938}](https://github.com/user-attachments/assets/b7762398-fee8-4d66-bc0d-8514e0c0f7bc)

## Step 4: Change IP Address Settings
In the IPv4 Properties window:  
1. Select `Use the following IP address`.  
2. Enter your desired:
   - IP address (e.g., `10.28.1.10`)
   - Subnet mask (typically `255.255.255.0`)
   - Default gateway (usually your router's IP, e.g., `10.28.1.1`)
3. For DNS, you can use:
   - Preferred DNS server (e.g., `127.0.0.1`)
  
![{C5DD01F1-FC8E-4D5C-8B5C-CBCF65259D10}](https://github.com/user-attachments/assets/3f8b063f-33d7-4076-b6a1-05900ae95e14)

## Step 5: Save Changes
1. Click `OK` to save the IPv4 settings.  
2. Click `OK` again to close the adapter properties.  
3. Close the Network Connections window.

![{40446266-9047-4A1B-A10C-6A927945981C}](https://github.com/user-attachments/assets/6de36bd7-eb5c-4b4f-b78a-f844c2370c71) ![{54201DA1-6666-4A95-85E4-085A21B2E7B5}](https://github.com/user-attachments/assets/e45f1ecf-95f0-49a8-bf91-62e14c4b7c56)

## Step 6: Verify the Changes
1. Open Command Prompt (`Windows Key + R`, type `cmd`, press Enter).

![{EEF8D811-CC3A-4CCE-89A3-7C6A0F8ADE7C}](https://github.com/user-attachments/assets/47037dc6-7996-4562-bc25-030d1815f280)

2. Type `ipconfig` and press Enter.

![{080368EE-465D-4CC3-91DA-052FF7A97DD6}](https://github.com/user-attachments/assets/c1a8e5a8-fce6-4be5-85f6-8498cf297e40)


3. Check that your new IP address appears under the correct adapter.

![{4EE93F95-A72F-4DD8-9F58-A2C2D0CAF122}](https://github.com/user-attachments/assets/0db6b900-dfcf-4d32-a214-04c72670666a)


# How to Add a Static Route in Windows Using Command Prompt

![Windows Version](https://img.shields.io/badge/Windows-10%20%7C%2011-blue?logo=windows)  ![Command Prompt](https://img.shields.io/badge/Tool-Command%20Prompt-lightgrey)  ![Network Admin](https://img.shields.io/badge/Level-Advanced-red)  

## Step-by-Step Guide

### Step 1: Open Command Prompt as Administrator
1. Press `Windows Key + X`
2. Select `Command Prompt (Admin)` or `Windows Terminal (Admin)`
3. If prompted by UAC, click `Yes` to grant administrative privileges

![{EEF8D811-CC3A-4CCE-89A3-7C6A0F8ADE7C}](https://github.com/user-attachments/assets/47037dc6-7996-4562-bc25-030d1815f280)

### Step 2: Add Routing 
Add a static routing protocol in cmd
```cmd
route add 10.28.0.0 mask 255.255.255.0 10.28.1.10
```

![{043D8917-FDB1-41FA-BA44-A0799F954AA9}](https://github.com/user-attachments/assets/a3309d79-47b6-4b07-8612-a5b42441aaa8)
