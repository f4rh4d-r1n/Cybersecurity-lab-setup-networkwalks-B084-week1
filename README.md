<div align="center">

# 🛡️ Cybersecurity-lab-setup-networkwalks-B084-week1

**Task Tag:** `networkwalks-B084-week1_Cybersecurity-Lab-Setup`  
**Author:** [Farhad Khan](https://www.linkedin.com/in/farhadmkhan/)

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
</p>

---

## 📝 Executive Overview

This repository about creating a home `kali linux` Practice lab and setting up their installation process and network setting by changing the default `NAT` network setting into `NAT Network` which is `10.0.0.1/24` and we will do that process with other VM's. So they can easily interact with each other. 

So this is basically the project task from `NETWORKWALKS-INTERNSHIP-BATCH-B084` of week1 and this is my week1 day 3 completing before the due date.

---

## 🎯 Lab Objectives

* Installing the Softwear that allow us to use the VM's VM_box/VMware in our windows system 
* Then installing our main virtual machine kali linux and moving it into VM box.
* After that then Changing the default network setting of VM box .
* Checking the connection if its working or not. 
* Make sure the connection wroking smoothly then check the ip.

---

## ⚙️ Core Technical Specifications

| Parameter | Operational Environment Values |
| :--- | :--- |
| **Host System Architecture** | Windows 10 / Intel Core i7 / 8 GB RAM |
| **Hypervisor Software** | Oracle VirtualBox v7.2 |
| **Active Instance** | Kali Linux v2026.2 (Allocated: 2048 MB RAM) |
| **Network Type** | Custom NAT Network (`NatNetwork`) |
| **IP Allocation Scheme** | Static Allocation |
| **Subnet Mask / Block** | 10.0.0.0/24 |
| **Assigned Node IP** | 10.0.0.2 |
| **Default Gateway IP** | 10.0.0.1 |
| **Primary Domain Resolver** | 8.8.8.8 (Google Public DNS) |

---

## 🪜 Step-by-Step Practical Build

### Phase 1: Install 7-zip & Extract the kali linux 

<img width="1038" height="94" alt="1" src="https://github.com/user-attachments/assets/34a7d779-1cd8-4417-8fef-00cd8345c91b" />

---

### Phase 2: Moving kali linux files ISO,VDI into VM Box

<img width="1062" height="203" alt="2" src="https://github.com/user-attachments/assets/3bda4675-1fa2-4b79-95ff-1c1d6ee8966c" />


Select the new button then import the VM file. VDI,ISO

<img width="959" height="539" alt="3" src="https://github.com/user-attachments/assets/4e7c4f2e-7b4c-444b-b78e-9e0cfa5a9cce" />


visit to the file location and select it it will imported automatically just named it and click Finish.

---

### Phase 3: Configuring the Network
Click that tabs.

<img width="959" height="302" alt="4" src="https://github.com/user-attachments/assets/bbd058bf-9851-4265-be05-781ee3eba6cc" />


Then navigate to this and use the same settings and click apply.

<img width="960" height="539" alt="5" src="https://github.com/user-attachments/assets/9465515c-abfd-42b4-88ba-83a6f24648ac" />


### Phase 4: Working with kali linux 

Start you kali linux machine and Move to there.



Use the same settings

<img width="707" height="318" alt="Screenshot 2026-10-28 124013" src="https://github.com/user-attachments/assets/dc45b50b-a9ac-4d24-9696-1e83db18e5d8" />

### Phase 5: Checking the ip and network connection.
Check that the connection is now working or not.

<img width="1220" height="441" alt="6" src="https://github.com/user-attachments/assets/43c1c969-f40f-4528-88ec-5c2555a30ed5" />

looking for IP if its changed or not.

<img width="299" height="100" alt="7" src="https://github.com/user-attachments/assets/d01953cb-b044-464f-a6bf-d38d873dcec2" />

And yeah everything worked smoothly so now we are able to move forward and configure the same ip connection with other OS systems.


---

## 🔎 Comprehensive Subnet Verification

To guarantee that the virtual networking stack behaves exactly as required, the interface metrics were probed directly from the terminal layer.

### Interface Property Examination
Running the interface identification tool confirmed that our primary network link has successfully obtained the designated internal routing address:

```bash
ip a show eth0
```


### Diagnostics Matrices

| Verification Test Vector | Terminal Command Executed | Expected Sandbox Outcome | Status |
| :--- | :--- | :--- | :--- |
| **Address Assessment** | `ip a` | Interface matches `10.0.0.2/24` precisely | ✅ Verified |
| **Gateway Reachability** | `ping -c 3 10.0.0.1` | Round-trip transmission with zero packet drop | ✅ Verified |
| **Outbound Wan Verification** | `ping -c 3 8.8.8.8` | ICMP traffic clears hypervisor translation layer | ✅ Verified |
| **DNS Resolution Validation** | `nslookup networkwalks.com` | Upstream resolvers answer with correct A-records | ✅ Verified |
| **Tool Inventory Audit** | `nmap --version` | Auditing bin files are present and mapped | ✅ Verified |
| **State Preservation Audit** | `VirtualBox Snapshot Tool` | System states can freeze and roll back on demand | ✅ Verified |

---

## 🛟 Resilience & Fault Tolerance Strategy

With the initial connection rules and static setups completed, a complete virtual disk snapshot was committed to the platform repository under the designation: `Clean Kali - Network Setup`.

This acts as our master restore checkpoint. Should heavy scanning scripts, raw system exploits, or breaking package configurations corrupt the kernel settings during future assessment labs, the node can be reset back to this specific verified operating baseline instantly.

