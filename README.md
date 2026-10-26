# Kali Linux Cybersecurity Lab Setup

A hands-on cybersecurity lab setup using Oracle VirtualBox and Kali Linux to practice networking, Linux commands, and network troubleshooting.

## 1. Project Overview

This project documents the setup of a virtual cybersecurity lab using Oracle VirtualBox and Kali Linux. The main objective was to configure a virtual network, troubleshoot Ethernet connectivity, verify internet access, and create a virtual machine snapshot for recovery.

## 2. Tools and Technologies

* **Virtualization:** Oracle VirtualBox
* **Operating System:** Kali Linux
* **Host Operating System:** Windows
* **Virtual Networking:** NAT Network
* **Network Management:** NetworkManager and `nmcli`
* **Linux Commands:** `ip`, `ping`, `nmcli`, `nmtui`

## 3. Lab Configuration

| Component | Configuration |
|---|---|
| Host OS | Windows |
| Guest OS | Kali Linux |
| Network Mode | NAT Network |
| Network Name | `NatNetwork` |
| IPv4 Network Prefix | `10.0.0.0/24` |
| DHCP | Enabled |
| Network Interface | `eth0` |
| Connectivity Testing | `ping` |

## 4. Step by Step Implementation

### Step 1: Install Oracle VirtualBox

Installed Oracle VirtualBox on the Windows host to create and manage a virtual machine for cybersecurity practice.

### Step 2: Set Up Kali Linux

Imported the Kali Linux virtual machine into VirtualBox, started the VM, and logged in to the Kali Linux desktop.

### Step 3: Configure the Virtual Network

Created a NAT Network in VirtualBox with the following settings:

* Network name: `NatNetwork`
* IPv4 prefix: `10.0.0.0/24`
* DHCP: Enabled

Configured the Kali Linux network adapter to use the NAT Network.

### Step 4: Troubleshoot Ethernet Connectivity

Initially, the Ethernet interface was disconnected, and the connection encountered IP configuration errors. I used Linux networking tools to inspect the interface and troubleshoot the connection.

Commands used:

```bash
nmcli device status
nmcli connection show
nmcli connection show "Wired connection 1"
ip -4 addr show eth0
ip route
```

I also explored `nmtui` to manage network connections through a terminal based interface.

### Step 5: Test Network Connectivity

Used `ping` to test connectivity to an external IP address and verify DNS resolution.

```bash
ping -c 4 8.8.8.8
ping -c 4 google.com
```

Both tests completed successfully, confirming internet connectivity and DNS resolution at the time of testing.

### Step 6: Create a Virtual Machine Snapshot

Created a VirtualBox snapshot named **Kali Linux - Fresh Setup** to preserve the current VM state and provide a recovery point before future cybersecurity exercises.

## 5. Screenshots

### Kali Linux Login Screen

![Kali Linux Login Screen](kali-linux%20login.png)

This screenshot shows the Kali Linux login screen after starting the virtual machine.

### Kali Linux Desktop

![Kali Linux Desktop](VirtualBox_kali-linux-home%20screen.png)

This screenshot shows the Kali Linux desktop after logging in successfully.

### Network Connectivity Test

![Kali Linux Network Connectivity Test](kali-linux%20network-connectivity.jpeg)

This screenshot shows the terminal output confirming successful connectivity tests using `ping`.

### VirtualBox Snapshot

![VirtualBox Snapshot](virtualbox-%20snapshot.jpeg)

This screenshot documents the snapshot created in VirtualBox for recovery.

## 6. Challenges Faced

* The Ethernet interface initially appeared as disconnected.
* NetworkManager encountered errors while attempting to obtain an IP address.
* The graphical network configuration was difficult to manage during troubleshooting.
* Some commands and connection activation attempts required corrections before the network was working properly.

Troubleshooting these issues helped me understand the importance of inspecting network interfaces, checking connection status, and verifying connectivity instead of relying only on graphical settings.

## 7. What I Learned

* How to configure a NAT Network in VirtualBox.
* The role of IPv4 addressing and DHCP in network configuration.
* How to inspect network interfaces and routing information in Linux.
* How to use `nmcli` and `nmtui` for network management.
* How to test IP connectivity and DNS resolution using `ping`.
* How to create VM snapshots for recovery and safe experimentation.
* How to document technical work using screenshots and GitHub.

## 8. Responsible Cybersecurity Practice

This lab is intended for educational purposes and authorized security testing. Future exercises will be conducted only on systems I own or have explicit permission to test.

## 9. Author

**Charan Tejavath**

GitHub: [Charan08-glitch](https://github.com/Charan08-glitch)

## 10. Conclusion

Setting up this lab gave me practical experience with Kali Linux, VirtualBox networking, and Linux command line troubleshooting. It also helped me build a foundation for future cybersecurity and penetration testing exercises.

This repository will serve as documentation for my continued hands-on learning in cybersecurity.
