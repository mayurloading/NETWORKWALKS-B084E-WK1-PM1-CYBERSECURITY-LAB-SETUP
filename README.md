<div align="center">

# 🛡️ Cybersecurity Lab Environment Setup

### Building an Isolated Virtual Lab for Penetration Testing and Ethical Hacking

![Windows](https://img.shields.io/badge/Host-Windows-blue?style=for-the-badge&logo=windows)
![VirtualBox](https://img.shields.io/badge/Hypervisor-VirtualBox-183A61?style=for-the-badge&logo=virtualbox)
![Kali Linux](https://img.shields.io/badge/Security_OS-Kali_Linux-557C94?style=for-the-badge&logo=kalilinux)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

**Week 01 Project | Cybersecurity at Networkwalks**

</div>

---

## 📌 Project Overview

In this project, I set up a virtual cybersecurity and penetration-testing laboratory using **Oracle VirtualBox and Kali Linux**.

I configured the lab on a dedicated **NAT Network** so that I can add more virtual machines later and use them as targets for authorized security testing.

This laboratory provides a foundation for practicing network reconnaissance, port scanning, vulnerability assessment, packet analysis, and other cybersecurity techniques in a controlled environment.

## 🎯 Objectives

My objectives for this project were to:

- Install Oracle VirtualBox.
- Create a private NAT Network for the laboratory.
- Import and run Kali Linux as a virtual machine.
- Verify the IP address of the Kali Linux VM.
- Test gateway connectivity and DNS resolution.
- Verify that Nmap is installed and working.
- Document the complete setup process with commands and screenshots.

## 🛡️ Purpose of the Lab

I built this lab as an isolated and controlled environment for cybersecurity learning and authorized security testing, including:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Security-tool experimentation

> ⚠️ **Ethical Use:** I will only use this laboratory on systems that I own or have explicit permission to test. I will not use the lab or its tools to attack unauthorized systems.

---

## ⚙️ Lab Configuration

| 🧩 Component | ⚙️ Configuration |
|---|---|
| 🖥️ Host OS | Windows |
| 🧳 Hypervisor | Oracle VirtualBox |
| 🐉 Security OS | Kali Linux 2026.3 (`kali-linux-2026.3-virtualbox-amd64`) |
| 📀 VM Name | My Fresh Kali Linux |
| 🌐 Virtual Network | NAT Network (`NatNetwork`) |
| 📡 Network Address | `10.0.0.0/24` |
| 🐧 Kali IP Address | `10.0.0.2/24` |
| 🚪 Default Gateway | `10.0.0.1` |
| 🌍 DNS Server | `8.8.8.8` |

---

# 🛠️ Lab Implementation

## Step 1: Install Oracle VirtualBox

I installed Oracle VirtualBox as my hypervisor for creating and managing virtual machines on Windows.

The screenshot below shows VirtualBox Manager ready to use.

**VirtualBox Manager**

![VirtualBox Manager](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/Screenshot%202026-10-29%20215516.png)

🔗 [View Original Screenshot on GitHub](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/Screenshot%202026-10-29%20215516.png)

---

## Step 2: Create the NAT Network

I created a dedicated NAT Network in VirtualBox under **NAT Networks**.

### Network Configuration

| Setting | Value |
|---|---|
| Network Name | `NatNetwork` |
| IPv4 Prefix | `10.0.0.0/24` |
| DHCP | Enabled |
| IPv6 | Disabled |

**NAT Network Configuration**

![NAT Network Configuration](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/image.png)

🔗 [View Original NAT Network Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/image.png)

I chose a NAT Network because multiple virtual machines connected to the same NAT Network can communicate with each other and access external networks through NAT.

This configuration will allow me to add attacker and target virtual machines to the laboratory in the future.

---

## Step 3: Import and Start Kali Linux

I imported the Kali Linux VirtualBox image (`kali-linux-2026.3-virtualbox-amd64`) into VirtualBox, connected the virtual machine to `NatNetwork`, and started it.

Kali Linux booted successfully to the desktop environment.

**Kali Linux Virtual Machine**

![Kali Linux Virtual Machine](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/Screenshot%202026-10-29%20215703.png)

🔗 [View Original Kali Linux Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/Screenshot%202026-10-29%20215703.png)

---

## Step 4: Verify the Kali Linux IP Address

I opened the Kali Linux terminal and executed the following command to inspect the network interfaces and their IP addresses.

### Command

```bash
ip a
```

The `eth0` interface was assigned the IPv4 address `10.0.0.2/24`.

**IP Address Verification**

![IP Address Verification](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/Screenshot%202026-10-29%20221930.png)

🔗 [View Original IP Address Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/Screenshot%202026-10-29%20221930.png)

---

# 🔎 Lab Verification

After configuring the virtual machine, I performed connectivity tests, checked DNS resolution, and verified the Nmap installation.

## Verification Summary

| ✅ Test | 🧾 Command | 🎯 Result |
|---|---|---|
| 🌐 Check IP Address | `ip a` | `eth0 = 10.0.0.2/24` ✔️ |
| 📡 Test Gateway | `ping 10.0.0.1` | 5/5 replies, 0% packet loss ✔️ |
| 🔍 Test DNS Resolution | `nslookup networkwalks.com` | Resolved to `192.232.216.135` ✔️ |
| 🧰 Verify Nmap | `nmap --version` | Nmap 7.99 ✔️ |

---

## 1. Test Gateway Connectivity

I used the `ping` command to confirm that my Kali Linux virtual machine could reach the lab network's gateway.

### Command

```bash
ping 10.0.0.1
```

**Result:** 5 out of 5 replies received with 0% packet loss.

**Gateway Connectivity Test**

![Gateway Connectivity Test](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/Screenshot%202026-10-29%20221958.png)

🔗 [View Original Gateway Test Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/Screenshot%202026-10-29%20221958.png)

---

## 2. Test DNS Resolution

I used `nslookup` to check whether the domain name `networkwalks.com` could be resolved to an IP address.

### Command

```bash
nslookup networkwalks.com
```

**Result:** The domain resolved to `192.232.216.135`.

**DNS Resolution Test**

![DNS Resolution Test](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/image-1.png)

🔗 [View Original DNS Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/image-1.png)

---

## 3. Verify Nmap Installation

I checked whether Nmap was installed and available on my Kali Linux virtual machine.

### Command

```bash
nmap --version
```

**Result:** Nmap version 7.99 was detected.

**Nmap Version Verification**

![Nmap Version Verification](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/raw/main/image-2.png)

🔗 [View Original Nmap Screenshot](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP/blob/main/image-2.png)

---

## 💡 What I Learned

Through this project, I gained practical experience in:

- **Virtualization:** Understanding how to create and manage virtual machines using Oracle VirtualBox.
- **Virtual Networking:** Learning how NAT Networks allow connected virtual machines to communicate and access external networks.
- **IP Configuration:** Using Linux commands to inspect network interfaces and verify IP addresses.
- **Network Testing:** Using `ping` to check connectivity and `nslookup` to verify DNS resolution.
- **Security Tools:** Verifying Nmap availability for network discovery and authorized security auditing.
- **Technical Documentation:** Recording configurations, commands, results, and screenshots in a professional README.

---

## 🔐 Security & Ethical Use

I built this laboratory strictly for educational purposes and authorized cybersecurity testing.

I will only test systems that I own or have explicit permission to assess. All experiments will be conducted responsibly and within the scope of the authorization provided.

---

## 🔗 Tools & Resources

| Resource | Description |
|---|---|
| [Oracle VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads) | Download virtualization software |
| [Kali Linux Downloads](https://www.kali.org/get-kali/) | Download Kali Linux |
| [Nmap Official Website](https://nmap.org/) | Network discovery and security auditing tool |
| [Project GitHub Repository](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP) | Source repository and project documentation |

---

## 👤 Author

**Mayuresh Sangale**

Third-Year Computer Engineering Student  
Cybersecurity Intern — Networkwalks

🔗 **LinkedIn:** [Mayuresh Sangale](https://www.linkedin.com/in/mayuresh-sangle-586879268/)

---

## 📌 Project Information

| Field | Details |
|---|---|
| Program Name | Cybersecurity at Networkwalks |
| Week | Week 01 |
| Project | Cybersecurity & Pentesting Lab Setup |
| Repository | [NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP](https://github.com/mayurloading/NETWORKWALKS-B084E-WK1-PM1-CYBERSECURITY-LAB-SETUP) |

---

<div align="center">

**Built with 💻, documented with 📝, and secured with 🛡️**

*Learning cybersecurity one lab at a time.*

</div>