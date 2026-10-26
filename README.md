# Building My Cybersecurity Lab: From Virtualization to Network Verification

**Week 01 | Practical Assignment WK1-PM1 | Cybersecurity Lab Setup**

A hands-on project documenting the creation of a virtual cybersecurity environment for learning network configuration, system administration, and ethical security testing.

---

## 📌 1. Project Overview

- This project focuses on building a controlled cybersecurity laboratory using virtualization technology and Kali Linux.
- The goal is to prepare a reliable environment where security tools can be explored, network behavior can be observed, and practical cybersecurity exercises can be performed safely.
- This repository documents the installation process, network configuration, connectivity tests, challenges encountered, and lessons learned.

## 🎯 2. Project Objectives

1. Install and configure Oracle VirtualBox.
2. Prepare Kali Linux as a virtual cybersecurity workstation.
3. Create and configure a dedicated virtual network.
4. Understand IP addresses, subnet masks, gateways, and DNS.
5. Verify network connectivity using Linux networking utilities.
6. Confirm that essential cybersecurity tools are available.
7. Create a recoverable baseline using virtual machine snapshots.
8. Document configuration decisions and testing evidence.

## 🧰 3. Tools and Technologies

| Tool | Purpose | Official Resource |
|------|---------|-------------------|
| Oracle VirtualBox | Virtual machine management | https://www.virtualbox.org/wiki/Downloads |
| Kali Linux | Cybersecurity workstation | https://www.kali.org/get-kali/ |
| 7-Zip | Archive extraction | https://www.7-zip.org/download.html |
| Nmap | Network discovery and security testing | https://nmap.org/docs.html |
| GitHub | Documentation and version control | https://docs.github.com/ |
| VirtualBox Networking | Virtual network configuration | https://www.virtualbox.org/manual/ch06.html |

## 🏗️ 4. Laboratory Design

The laboratory consists of a host computer running VirtualBox, with Kali Linux operating as a guest virtual machine.

### Logical Architecture

```text
HOST COMPUTER
     |
Oracle VirtualBox
     |
Virtual Network
     |
Kali Linux
     |
Future Authorized Targets
```

## ⚙️ 5. Lab Configuration

| Component | My Configuration |
|---|---|
| Host OS | Parrot Os |
| Host RAM | 8Gb |
| VirtualBox Version | v7.2.22 |
| Kali Linux Version | 2026.2 |
| Kali RAM Allocation | 2Gb |
| Network Mode |  NAT Network |
| Network Name | LabNET1 |
| IPv4 Network | 10.0.0.0/24 |
| Kali IPv4 Address | 10.0.0.3 |
| Default Gateway | 10.0.0.1 |
| DNS Server | 8.8.8.8 |
| Snapshot Name | `CyberLab-Baseline` |

**Configuration note:** Use the actual values from your environment.

---

## 🪜 6. Implementation Procedure

### Step 1: Prepare the Host Environment

- Checked available memory and storage.
- Verified virtualization support.
- Downloaded required software from official sources.

**Resources:**
- [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
- [Kali Linux Downloads](https://www.kali.org/get-kali/)

### Step 2: Install VirtualBox

- Installed Oracle VirtualBox.
- Verified that the application opened correctly.
- Prepared the environment for virtual machine creation.

**Evidence:** `screenshots/01-virtualbox-manager.png`

### Step 3: Prepare Kali Linux

- Downloaded or imported Kali Linux.
- Configured virtual machine memory.
- Checked the network adapter settings.
- Started the virtual machine.

**Evidence:** `screenshots/02-kali-vm-settings.png`

**Resource:**
- [Kali Linux Documentation](https://www.kali.org/docs/)

### Step 4: Configure the Virtual Network

- Created or selected the appropriate virtual network.
- Attached the Kali Linux network adapter.
- Verified the selected networking mode.

**Evidence:** `screenshots/03-virtual-network.png`

**Resource:**
- [VirtualBox Networking Documentation](https://www.virtualbox.org/manual/ch06.html)

### Step 5: Inspect Network Settings

Display network interfaces and IP addresses:

```bash
ip a
```

Inspect the routing table:

```bash
ip route
```

**Purpose:**
- Identify active network interfaces.
- Confirm IP address assignment.
- Inspect the default gateway and routing configuration.

**Evidence:** `screenshots/04-ip-configuration.png`

### Step 6: Verify Connectivity

Check the routing configuration:

```bash
ip route
```

Test the gateway:

```bash
ping -c 4 <gateway-ip>
```

Test external IP connectivity:

```bash
ping -c 4 1.1.1.1
```

Check DNS resolution:

```bash
getent hosts example.com
```

Verify Nmap installation:

```bash
nmap --version
```

**Important:** Replace `<gateway-ip>` with your actual gateway address. Failed ping tests may result from ICMP filtering rather than a network failure.

**Evidence:** `screenshots/05-connectivity-tests.png`

### Step 7: Create a Recovery Snapshot

Create a VirtualBox snapshot named:

`CyberLab-Baseline`

The snapshot provides a recovery point before future experiments.

**Evidence:** `screenshots/06-baseline-snapshot.png`

---

## 🔎 7. Verification and Results

| Test | Command / Method | Actual Result |
|---|---|---|
| IP address assignment | `ip a` | [Pass / Fail + observation] |
| Routing configuration | `ip route` | [Pass / Fail + observation] |
| Gateway connectivity | `ping -c 4 <gateway-ip>` | [Pass / Fail + observation] |
| External connectivity | `ping -c 4 1.1.1.1` | [Pass / Fail + observation] |
| DNS resolution | `getent hosts example.com` | [Pass / Fail + observation] |
| Nmap availability | `nmap --version` | [Pass / Fail + observation] |
| Snapshot creation | VirtualBox Snapshot Manager | [Pass / Fail + observation] |

### Results Summary

- **Overall status:** [Completed / Partially completed / In progress]
- **Outstanding issues:** [List any unresolved problems]
- **Evidence captured:** [List screenshots available]

Only mark tests as passed after observing and recording their actual results.

---

## 🐛 8. Challenges and Troubleshooting

### Challenge 1: [Describe the Issue]

- **Observed behavior:** [What happened?]
- **Investigation:** [Commands or checks performed]
- **Root cause:** [What caused the issue?]
- **Solution:** [How was it resolved?]
- **Verification:** [What confirmed the outcome?]

### Challenge 2: [Describe Another Issue]

- **Observed behavior:** [Describe the problem]
- **Investigation:** [Explain the checks performed]
- **Resolution:** [Document the solution]
- **Outcome:** [Record the result]

---

## 🧠 9. Key Lessons Learned

- **Virtualization:** Virtual machines provide flexible and recoverable testing environments.
- **Network addressing:** IP addresses and subnet masks help determine how devices communicate.
- **Routing:** Routing tables show where network traffic is directed.
- **DNS:** DNS translates domain names into IP addresses.
- **Troubleshooting:** Testing individual network functions helps isolate problems.
- **Snapshots:** Recovery points make experimentation safer.
- **Documentation:** Screenshots and recorded test results improve reproducibility.

---

## 🛡️ 10. Security and Ethical Considerations

- Perform security testing only against systems you own or have permission to assess.
- Keep experimental machines separated from production networks.
- Verify network adapter settings before performing security exercises.
- Download software from trusted sources.
- Avoid committing passwords, private keys, or access tokens.
- Create snapshots before significant configuration changes.
- Use isolated networking when internet access is unnecessary.

---

## 📸 11. Project Evidence

### Repository Structure

```text
cybersecurity-lab-setup/
├── README.md
└── screenshots/
    ├── 01-virtualbox-manager.png
    ├── 02-kali-vm-settings.png
    ├── 03-virtual-network.png
    ├── 04-ip-configuration.png
    ├── 05-connectivity-tests.png
    └── 06-baseline-snapshot.png
```

### Displaying Screenshots

Use the following Markdown syntax to display a screenshot:

```markdown
![VirtualBox network configuration](screenshots/03-virtual-network.png)
```

Ensure the screenshot filenames match the actual files in your repository.

---

## 🚀 12. Future Improvements

- Add a deliberately vulnerable target virtual machine.
- Analyze network traffic using Wireshark.
- Practice authorized service discovery with Nmap.
- Learn firewall configuration and traffic filtering.
- Write structured security assessment reports.
- Automate network verification using Bash scripts.
- Create an isolated network for vulnerable target machines.

### Resources

- [Wireshark Official Website](https://www.wireshark.org/)
- [Nmap Reference Guide](https://nmap.org/book/man.html)
- [Kali Linux Documentation](https://www.kali.org/docs/)
- [VirtualBox User Manual](https://www.virtualbox.org/manual/)

---

## 📚 13. References

1. [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads)
2. [VirtualBox User Manual](https://www.virtualbox.org/manual/)
3. [VirtualBox Networking Documentation](https://www.virtualbox.org/manual/ch06.html)
4. [Kali Linux Downloads](https://www.kali.org/get-kali/)
5. [Kali Linux Documentation](https://www.kali.org/docs/)
6. [7-Zip Official Downloads](https://www.7-zip.org/download.html)
7. [Nmap Documentation](https://nmap.org/docs.html)
8. [GitHub Flavored Markdown Guide](https://github.github.com/gfm/)
9. [GitHub Repository Documentation](https://docs.github.com/en/repositories)

---

## 👤 14. Author and Assignment Details

| Field | Details |
|---|---|
| Student Name | Peter Kariuki W. |
| Student / Batch ID | [Your assigned ID] |
| Training Program | [Your program name] |
| Assignment | WK1-PM1 — Cybersecurity Lab Setup |
| Repository | [Your GitHub repository URL] |
| Completion Date | [Date completed] |

---

## 🏁 Conclusion

This project established the foundation for a practical cybersecurity learning environment by combining virtualization, Linux system configuration, network verification, and technical documentation.

The exercise reinforced the importance of understanding system configuration before attempting security testing. It also highlighted the value of verification, troubleshooting, and recovery planning.

The lab provides a starting point for further learning in network analysis, system hardening, and authorized penetration testing.
