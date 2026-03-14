# Virtual Cybersecurity Lab: A Hands-On SOC & Penetration Testing Environment
A fully isolated virtual lab for simulating real-world cyber attacks (DDoS, MITM, Exploitation) and practising defensive security operations with industry-standard tools

## 📜 Project Overview

This project addresses the critical gap between theoretical cybersecurity knowledge and practical skills. I designed, implemented, and documented a fully isolated virtual cybersecurity laboratory using desktop virtualization. The lab provides a safe, legal, and controlled environment to simulate real-world cyber threats and practice both offensive and defensive security techniques, mirroring the workflows of a Security Operations Center (SOC).

The core of this project was to move beyond theory and build a platform for experiential learning, enabling hands-on practice in threat detection, incident response, and network defense.

## 🏗️ Lab Architecture

The lab is built on *VMware Workstation Pro* using a *Host-Only network* (192.168.100.0/24) to ensure complete isolation from external networks. It consists of three specialized virtual machines:

*   *Attacker (Kali Linux):* A penetration testing platform equipped with tools for reconnaissance, exploitation, and attack simulation.
*   *Target (Metasploitable 2):* An intentionally vulnerable Ubuntu server, providing a realistic and safe target for practicing exploitation techniques.
*   *Defender (Ubuntu Server 22.04):* A dedicated monitoring and defense platform, configured with tools for traffic analysis, intrusion detection, and firewall management.

![System Design Architecture](https://github.com/chikochikomba/Virtual-Cybersecurity-Lab/blob/83f56279b7e0ef6c62a77861f4339e1b052251da/System%20Design%20Architecture.png)
<!-- PRO TIP: Take a screenshot of Figure 1 from your thesis (page 30) and save it as an image in your repo. Link it here. -->

## 🛠️ Tools & Technologies Used

| Category | Tools |
| :--- | :--- |
| *Virtualization* | VMware Workstation Pro |
| *Offensive Security* | Kali Linux, Nmap, Metasploit Framework, hping3, arpspoof (dsniff) |
| *Defensive Security* | Ubuntu Server, Wireshark, tcpdump, iptables, fail2ban, arpwatch |
| *Vulnerable Target* | Metasploitable 2 (vsftpd 2.3.4, etc.) |

## 🔬 Hands-On Exercises & Simulations

This lab was validated through several realistic cybersecurity scenarios that demonstrate its educational value:

### 1. Distributed Denial of Service (DDoS) Attack & Mitigation
*   *Action:* Simulated a SYN flood attack from Kali against the Ubuntu server using hping3.
*   *Detection:* Monitored the attack in real-time on the Ubuntu defender using *Wireshark* to analyze the traffic spike.
*   *Mitigation:* Implemented and tested defensive *iptables* firewall rules on the Ubuntu server to rate-limit incoming traffic and block the attacker's IP, successfully mitigating the attack.

### 2. Vulnerability Exploitation & Patching (Full Lifecycle)
*   *Recon:* Performed service and version enumeration on Metasploitable using *Nmap* (-sV).
*   *Exploit:* Identified the infamous *vsftpd 2.3.4 backdoor (CVE-2011-2523)* and used the *Metasploit Framework* to exploit it, gaining a reverse shell on the target system.
*   *Remediation:* "Patched" the vulnerability by updating the service and hardening its configuration.
*   *Validation:* Re-scanned the target with Nmap and re-ran the exploit to confirm the vulnerability was successfully mitigated.

### 3. Man-in-the-Middle (MITM) Attack with ARP Spoofing
*   *Action:* Executed an ARP spoofing attack from Kali to intercept network traffic between the Metasploitable target and the Ubuntu defender.
*   *Interception:* Enabled IP forwarding on Kali to become a transparent relay.
*   *Analysis:* Used *tcpdump* on Kali to capture and analyze the live traffic stream between the two victim machines, demonstrating how easily unencrypted communications can be intercepted.

## 🚀 Practical Use Cases

Beyond structured exercises, the lab is designed for practical application:

*   *Rapid Deployment:* Pre-configured VMs allow for a fully functional, multi-role lab environment to be operational in minutes.
*   *Safe Maintenance:* The Host-Only network ensures all malicious activity is contained. Temporary internet access can be enabled for *safe tool updates* (e.g., updating Kali's tool suite) without exposing the vulnerable target.
*   *Repeatable Learning:* *VMware snapshots* are crucial, allowing the entire lab or individual machines to be reverted to a clean state in seconds. This enables endless, risk-free experimentation and consistent exercise repetition.

## ✅ Validation & Key Achievements

*   *Proven Isolation:* Successfully configured a Host-Only network, confirming that VMs could communicate internally but had no access to the external internet.
*   *Exercise Reproducibility:* Validated the snapshot and recovery process, guaranteeing that the lab can be reset to a pristine state for consistent training.
*   *Educational Value:* Demonstrated the lab's effectiveness by successfully executing three distinct attack/defense scenarios, providing a platform for developing practical skills in threat response and network defense.

## 📚 Thesis Documentation

For a complete, in-depth analysis of the project's design, implementation, and pedagogical foundation, please refer to the full thesis document:
[Virtual_Cybersecurity_Lab_Thesis_Chikomborero_Chikomba.pdf](link_to_your_pdf)

## 🧑‍💻 About Me

I am an IT professional and soon-to-be Computer Science graduate passionate about cybersecurity. I built this lab to bridge the gap between theory and practice, and I am eager to apply these skills in a Security Operations Center (SOC) or as a Cybersecurity Analyst. Connect with me on [LinkedIn](your-linkedin-url).

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
![VMware](https://img.shields.io/badge/VMware-Workstation%20Pro-green)
![Kali](https://img.shields.io/badge/Kali-Linux-blue)
![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04-orange)
