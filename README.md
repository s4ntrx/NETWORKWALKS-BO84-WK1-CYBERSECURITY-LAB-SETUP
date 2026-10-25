<div align="center">

🔐 Building My Cybersecurity Lab: From Virtualization to Network Verification

Week 01 | Practical Assignment WK1-PM1 | Cybersecurity Lab Setup

A hands-on project documenting the creation of a virtual cybersecurity environment for learning network configuration, system administration, and ethical security testing.

<p align="center">
<img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" alt="Cybersecurity" />
<img src="https://img.shields.io/badge/VirtualBox-v7.2-0070C0?style=flat-square&labelColor=000000&logo=virtualbox&logoColor=white" alt="VirtualBox" />
<img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Kali Linux" />
<img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" alt="Linux" />
<img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" alt="Virtual Network" />
<img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Penetration Testing" />
<img src="https://img.shields.io/badge/Virtualization-404040?style=flat-square&labelColor=C00000" alt="Virtualization" />
<img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" alt="GitHub" />
<img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" alt="NetworkWalks" />
<img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" alt="Ethical Hacking" />
<img src="https://img.shields.io/badge/s4ntrx-C00000?style=flat-square" alt="s4ntrx" />
</p>

</div>

📌 1. Project Overview

This project focuses on building a controlled cybersecurity laboratory using virtualization technology and Kali Linux. The goal is to establish a reliable environment where security tools can be explored, network behavior can be observed, and practical cybersecurity exercises can be performed safely.

Instead of working directly on a physical machine or an everyday network, the lab uses virtual machines and a dedicated virtual network to separate testing activities from normal computing operations.

This repository serves as a technical record of the installation process, network configuration, connectivity tests, challenges encountered, and lessons learned during the setup.

🎯 2. Project Objectives

The key objectives of this assignment are to:

Install and configure Oracle VirtualBox.
Prepare Kali Linux as a virtual cybersecurity workstation.
Create and configure a dedicated virtual network.
Understand the relationship between IP addresses, subnet masks, gateways, and DNS.
Verify network connectivity using Linux networking utilities.
Confirm that essential cybersecurity tools are available.
Create a recoverable baseline using virtual machine snapshots.
Document configuration decisions and provide evidence of successful testing.
🧰 3. Tools and Technologies
Tool / Technology	Purpose	Official Resource
Oracle VirtualBox	Runs and manages virtual machines	Download VirtualBox
Kali Linux	Provides a Linux environment for cybersecurity learning	Kali Linux Downloads
7-Zip	Extracts compressed virtual machine files when required	Download 7-Zip
VirtualBox NAT Network	Provides networking for participating virtual machines	VirtualBox Networking Documentation
Linux Terminal	Used for configuration and diagnostic commands	Kali Linux Documentation
Nmap	Supports authorized network discovery and service enumeration	Nmap Official Website
Wireshark	Supports network traffic inspection and analysis	Wireshark Official Website
GitHub	Stores project documentation, screenshots, and configuration notes	GitHub
🏗️ 4. Laboratory Design

The laboratory consists of a host computer running VirtualBox, with Kali Linux operating as a guest virtual machine.

The virtual network is configured to support the intended lab activities. Additional virtual machines can be introduced later to create a multi-system testing environment.

Logical Architecture
text
                 HOST COMPUTER
                       |
                Oracle VirtualBox
                       |
                 Virtual Network
                       |
                  Kali Linux
              Security Workstation
                       |
            Future Authorized Targets


Note: This diagram represents the logical design of the lab. The actual topology depends on the virtual network and virtual machines configured.

⚙️ 5. Lab Configuration

The following table records the configuration used for this assignment. Replace the placeholders with the settings from your actual system.

Component	My Configuration
Host operating system	[Windows / Linux / macOS]
Host RAM	[Available RAM]
Virtualization software	Oracle VirtualBox v7.2
Guest operating system	Kali Linux v2026.2
Memory allocated to Kali	[RAM allocation]
Virtual network mode	[NAT Network / other]
Network name	[Your network name]
IPv4 network	[Your subnet in CIDR notation]
Kali IPv4 address	[Your Kali IP address]
Default gateway	[Your gateway]
DNS server	[Your DNS server]
Snapshot name	CyberLab-Baseline
Configuration note: The versions shown in the badges and table should match the software actually installed. The 10.0.0.0/24 badge is illustrative; replace it if your configured subnet differs. Do not assume that the network, gateway, or IP addresses match your environment without verification.
🪜 6. Implementation Procedure
Step 1: Prepare the Host Environment

I checked the host computer's available memory, storage, and virtualization support before creating the virtual machine.

I also obtained the required software from official download sources.

Purpose: Ensure that the host system can support the virtualized lab.

Resources:

VirtualBox Downloads
Kali Linux Downloads

Evidence: Add a screenshot showing the host system or downloaded installation files.

Step 2: Install VirtualBox

I installed Oracle VirtualBox and verified that the application opened correctly.

The hypervisor provides the resources needed to create, configure, start, stop, and recover virtual machines.

Evidence: Add a screenshot showing the VirtualBox Manager window.

Reference: VirtualBox User Manual

Step 3: Prepare Kali Linux

I downloaded or imported Kali Linux and checked its basic settings before starting the virtual machine.

The virtual machine's memory allocation and network adapter were configured according to the available host resources and lab requirements.

Evidence: Add a screenshot showing the Kali Linux virtual machine in VirtualBox.

Reference: Kali Linux Installation Documentation

Step 4: Configure the Virtual Network

I created or selected a virtual network appropriate for the assignment and attached the Kali Linux network adapter to it.

The network configuration was checked to ensure that the guest operating system used the intended virtual network.

A NAT Network can allow participating virtual machines to communicate with one another while providing outbound connectivity. Actual connectivity depends on the network settings and firewall rules.

Evidence: Add a screenshot of the VirtualBox network settings.

Reference: VirtualBox Networking Documentation

Step 5: Inspect Kali Linux Network Settings

After starting Kali Linux, I used the terminal to inspect its network interfaces and IP configuration.

Display the network interfaces and assigned addresses:

bash
ip a


Inspect the routing table:

bash
ip route


These commands help identify the assigned IP address, active interfaces, and configured network routes.

Evidence: Add a terminal screenshot showing your actual network configuration.

Reference: Linux manual pages

Step 6: Verify Connectivity

I tested the network configuration using diagnostic commands.

1. Check the routing configuration

bash
ip route


2. Test the configured gateway

Replace <gateway-ip> with the actual gateway address shown in your routing configuration.

bash
ping -c 4 <gateway-ip>


3. Test external IP connectivity

If outbound connectivity is permitted, test an external IP address:

bash
ping -c 4 1.1.1.1


4. Check DNS resolution

bash
getent hosts example.com


5. Check Nmap availability

bash
nmap --version


The results help distinguish local network connectivity, external IP connectivity, DNS resolution, and tool availability.

Important: A failed ping does not always indicate a broken network. The destination or a firewall may block ICMP traffic. Similarly, successful connectivity to an IP address does not guarantee that DNS resolution is working.

Evidence: Add a screenshot showing the commands and their actual output.

References:

Nmap Reference Guide
Cloudflare DNS
Linux manual pages
Step 7: Create a Recovery Snapshot

Once the initial configuration was verified, I created a VirtualBox snapshot named:

CyberLab-Baseline

The snapshot provides a recovery point that can be used if later experiments cause unwanted changes.

Evidence: Add a screenshot showing the saved snapshot in VirtualBox.

Reference: VirtualBox User Manual

🔎 7. Verification and Results

Complete the following table using your actual test results.

Test	Command / Method	Actual Result
IP address assignment	ip a	[Pass / Fail + observation]
Routing configuration	ip route	[Pass / Fail + observation]
Gateway reachability	ping -c 4 <gateway-ip>	[Pass / Fail + observation]
External IP connectivity	ping -c 4 1.1.1.1	[Pass / Fail + observation]
DNS resolution	getent hosts example.com	[Pass / Fail + observation]
Nmap availability	nmap --version	[Pass / Fail + observation]
Snapshot creation	VirtualBox Snapshot Manager	[Pass / Fail + observation]
Results Summary

Overall status: [Completed / Partially completed / In progress]

The verification process helped establish whether the virtual machine was configured correctly and identify any outstanding network or software issues.

Only mark a test as passed when you have observed and recorded the corresponding result.

🐛 8. Challenges and Troubleshooting

A technical project should document problems as well as successful outcomes.

Use the following format to record issues encountered during the setup.

Challenge 1: [Describe the Issue]

Observed behavior:
[Explain what happened and include any relevant error message.]

Investigation:
[Describe the checks or commands used to identify the cause.]

Solution applied:
[Explain the change that resolved the problem.]

Verification:
[Record the test used to confirm whether the issue was resolved.]

Challenge 2: [Describe Another Issue, If Applicable]

Observed behavior:
[Describe the problem.]

Root cause:
[Explain what you discovered.]

Resolution:
[Document the steps taken.]

Outcome:
[Explain whether the solution worked.]

If no significant problems occurred, document a configuration check you performed and explain why it was important.

🧠 9. Key Lessons Learned

This assignment demonstrates several important cybersecurity and system administration concepts.

Virtualization: Virtual machines provide a flexible way to build and reset testing environments without requiring separate physical computers.
Network addressing: IP addresses and subnet masks determine how devices identify themselves and communicate across networks.
Routing: The routing table helps explain where network traffic is sent.
DNS: Name resolution translates domain names into IP addresses that applications can use.
Troubleshooting: Testing individual components helps narrow down the source of connectivity problems.
Snapshots: Recovery points make experimentation more manageable by allowing a virtual machine to return to a previous state.
Technical documentation: Clear commands, screenshots, configuration records, and test results make work easier to reproduce and review.
🛡️ 10. Security and Ethical Considerations

This environment is intended for educational use and authorized security testing.

Perform scanning and testing only against systems you own or have explicit permission to assess.
Keep experimental virtual machines separated from production systems and networks.
Verify network adapter settings before performing potentially disruptive exercises.
Use trusted software sources and keep the lab updated.
Avoid storing passwords, private keys, access tokens, or other sensitive information in the repository.
Create snapshots before making significant configuration changes.
Review network exposure before attaching a vulnerable target to any network with external connectivity.
📸 11. Project Evidence

Screenshots should demonstrate the actual work performed during the assignment.

Suggested Repository Structure
text
cybersecurity-lab-setup/
├── README.md
└── screenshots/
    ├── 01-virtualbox-manager.png
    ├── 02-kali-vm-settings.png
    ├── 03-virtual-network.png
    ├── 04-ip-configuration.png
    ├── 05-connectivity-tests.png
    └── 06-baseline-snapshot.png


Create the screenshots/ directory in your repository and add the images you captured. Remove any filenames that do not correspond to evidence you actually have.

Screenshot 1: VirtualBox Manager

!VirtualBox Manager

Screenshot 2: Kali Linux Virtual Machine Settings

!Kali Linux VM Settings

Screenshot 3: Virtual Network Configuration

!Virtual Network Configuration

Screenshot 4: IP Configuration

!Kali Linux IP Configuration

Screenshot 5: Connectivity Tests

!Network Connectivity Tests

Screenshot 6: Baseline Snapshot

!VirtualBox Baseline Snapshot

Note: The images will display after you upload the corresponding files to the screenshots/ directory. Replace the filenames in the Markdown if your actual image filenames differ.
🚀 12. Future Improvements

The lab can be extended through additional controlled exercises, including:

Adding a deliberately vulnerable target virtual machine.
Studying network traffic using Wireshark.
Practicing service discovery with Nmap against authorized lab targets.
Learning basic firewall configuration and traffic filtering.
Recording findings in structured security assessment reports.
Automating routine verification checks with simple scripts.
Exploring additional networking concepts through the Kali Linux Documentation.

Each extension should be introduced incrementally and tested within the authorized lab environment.

📚 13. References
Kali Linux Official Website
Kali Linux Downloads
Kali Linux Installation Documentation
Oracle VirtualBox Downloads
Oracle VirtualBox User Manual
VirtualBox Networking Documentation
Nmap Official Website
Nmap Reference Guide
Wireshark Official Website
7-Zip Official Website
GitHub Markdown Documentation
Linux Manual Pages
👤 14. Author and Assignment Details
Field	Details
Student name	Peter Kariuki W.
Student / batch ID	[Your assigned ID]
Training program	[Your program name]
Assignment	WK1-PM1 — Cybersecurity Lab Setup
Repository	[Your GitHub repository URL]
Completion date	[Date completed]
🏁 Conclusion

This project established the foundation for a practical cybersecurity learning environment by bringing together virtualization, Linux system configuration, network verification, and technical documentation.

The exercise reinforced the importance of understanding how a system is configured before attempting security testing. It also highlighted the value of verification, troubleshooting, and recovery planning in maintaining a dependable laboratory.

The resulting environment provides a starting point for future hands-on exercises in network security, network analysis, and ethical penetration testing.

<p align="center">

Built for learning. Configured for experimentation. Guided by ethical security practices.

</p>
