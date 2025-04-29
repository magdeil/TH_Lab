<div align="center">
  <img src="https://rivanit.com/assets/logo-DaYZ0U1G.png" alt="Logo" title="TH_Lab Logo"/> <h1> Rivan Cyber </h1>
</div>

# 📘 DAY 1 — TH_Lab

![Day](https://img.shields.io/badge/Day-1-blue)
![Lab](https://img.shields.io/badge/Lab-TH_Lab-blueviolet)

---

![{528B51F1-FE6C-4BB4-9EA0-2E85A57CCB55}](https://github.com/user-attachments/assets/d61f16f4-1741-43e1-ab04-41f4e3c7c278)

| Switch Port | Device Type | Description       |
|-------------|-------------|-------------------|
| 0/1/1      | Telephony   | Cisco IP Phone    |
| 0/1/3      | Camera      | Security Camera   |
| 0/1/5      | Access Point| Wireless AP       |
| 0/1/7      | PC          | Workstation       |


## 🛠️ Task 1: Physical Ports Check

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
