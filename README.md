# 🛡 UFW Firewall Configuration & Security Hardening Project 

# 📌 Introduction
This repository documents the setup, configuration, and testing of the UFW (Uncomplicated Firewall) on a Kali Linux system. The objective was to establish a robust baseline firewall configuration, block insecure services, and validate security controls against real-world attack vectors using network scanning tools.

UFW acts as a user-friendly interface to iptables, making firewall rule management simpler while still leveraging the full power of Linux's netfilter framework.

# 🔍 Technical Workflow
## 1️⃣ Installing & Enabling UFW

sudo apt update && sudo apt install ufw 


sudo systemctl enable ufw

## 2️⃣ Enabling Firewall Logging

sudo ufw enable

## 3️⃣ Setting Default Policies

sudo ufw default deny incoming


sudo ufw default allow outgoing


## 4️⃣ Blocking Insecure Telnet (Port 23)

sudo ufw deny 23


## 5️⃣ Allowing SSH Access (Port 22)

sudo ufw allow 22

## 6️⃣ Testing Firewall Rules

nmap -p 23 10.0.2.17
Confirms that Telnet is blocked .

# Result 
<img width="1920" height="936" alt="Image" src="https://github.com/user-attachments/assets/f7bf6bce-7e68-4f33-81aa-8fc73f94d06d" />


# 📊 Key Outcomes
Risk Reduction: Removed exposure of Telnet service, preventing plaintext credential theft.

Service Continuity: SSH and essential web services remain operational.

Default-Deny Posture: Minimizes attack surface by only allowing required ports.

IPv4 & IPv6 Support: Protection applies to both protocol stacks.

Operational Visibility: Logging enables post-event analysis and proactive monitoring.

# 🧠 Security Principles Applied
Principle of Least Privilege: Only required ports/services remain open.

Fail-Safe Defaults: Deny-all incoming policy ensures no accidental exposure.

Defense in Depth: Layered rules combining blocking, allowing, and logging.

Auditability: Configured logging for forensic readiness.

# ⚙️ How UFW Works Behind the Scenes
Frontend for iptables: Converts simple commands into complex iptables rules.

Chain Management: Integrates rules into INPUT, OUTPUT, and FORWARD chains.

Stateful Filtering: Tracks connection states for smarter filtering.

Performance Optimization: Prioritizes rule checks for efficiency.

# 🌐 Network Traffic Flow Diagram
Inbound Traffic:

Default DENY rule triggers first.

Allowed ports checked in sequence.

Blocked packets logged (if enabled).

Outbound Traffic:

Allowed by default unless overridden.

Supports updates, browsing, and client-based services.

# 🚀 Recommended Future Enhancements
Immediate Improvements

Apply SSH rate limiting to deter brute force attacks.

Implement geographic IP blocking for region-specific restrictions.

Use port knocking to hide SSH from unauthorized scans.

Integrate Fail2Ban for intrusion prevention.

Advanced Security

Application-layer filtering via reverse proxies.

VLAN-based network segmentation for isolation.

SIEM integration for centralized log management.

Automated firewall rule updates from threat intelligence feeds.

# ✅ Project Highlights
Installed & configured UFW successfully.

Enforced security-first default policies.

Blocked insecure services while preserving administrative access.

Conducted remote & local validation using nmap and telnet.

Achieved dual-stack protection for both IPv4 & IPv6 traffic.

# 📅 Final Notes
This project demonstrates how a properly configured firewall can strengthen network defenses without impacting productivity. By combining default-deny rules, service whitelisting, and logging, it provides a strong foundation for more advanced intrusion prevention systems.


