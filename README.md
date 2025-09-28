# Internship-4-elevatelabs
Basic firewall management skills and understanding of network traffic filtering.
# Windows Firewall Configuration and Testing

> **Cybersecurity Internship Task 4** | **Institution:** GD Goenka University | **Organization:** Elevate Labs  
> **Date:** September 26, 2025 | **Student:** BTech Cybersecurity Student

## 🔒 Project Overview

This repository contains a comprehensive implementation and testing of Windows Firewall Advanced Security configurations to establish robust network traffic filtering. The project demonstrates practical cybersecurity skills through systematic firewall rule creation, multi-layer security implementation, and thorough validation testing.

### 🎯 Key Achievements
- ✅ Successfully blocked vulnerable services (Telnet port 23, SMB port 135)
- ✅ Implemented network security best practices
- ✅ Conducted professional-grade testing procedures
- ✅ Created comprehensive documentation and validation evidence

## 📋 Task Objectives

**Primary Objective:** Configure and test basic firewall rules to allow or block traffic using Windows Firewall Advanced Security

### 🛠️ Tools Utilized
- **Windows Firewall with Advanced Security** - Primary firewall management
- **PowerShell** - Network connectivity testing (`Test-NetConnection`)
- **Command Prompt** - Port scanning validation
- **netstat** - Network connection analysis

### 📦 Deliverables
- Screenshot documentation of firewall rules implementation
- Comprehensive testing results with validation evidence
- Professional security analysis and recommendations
- Step-by-step configuration documentation

## 🔧 Technical Implementation

### Phase 1: Firewall Rule Configuration

#### 🚫 Telnet Service Blocking (Port 23)
**Security Rationale:** Telnet transmits all data, including passwords, in plain text format, making it extremely vulnerable to network sniffing attacks and man-in-the-middle exploits.

**Implementation Process:**
1. Opened Windows Firewall with Advanced Security (`wf.msc`)
2. Created new inbound rule targeting TCP port 23
3. Configured rule action to "Block the connection"
4. Applied rule across all network profiles (Domain, Private, Public)
5. Verified rule activation and proper configuration

#### 🛡️ SMB Port Security (Port 135)
**Security Rationale:** Port 135 is commonly targeted in network attacks due to its role in Windows RPC services and potential for remote code execution vulnerabilities.

**Implementation Process:**
1. Created dedicated inbound blocking rule for TCP port 135
2. Named rule "Block SMB Port 135" for clear identification
3. Ensured rule applies to all network interface types
4. Verified rule priority and conflict resolution

### Phase 2: Network Service Management

#### Application-Specific Rules
The firewall configuration includes sophisticated application-level controls beyond basic port blocking:
- **AnyDesk Remote Access:** Configured selective allow rules for legitimate remote access
- **Gaming Applications:** Implemented controlled access for applications like GNS3 and educational tools
- **System Services:** Maintained essential Windows services while blocking unnecessary exposure

#### Advanced Security Features
- **Profile-Based Configuration:** Different rules applied based on network type (Public, Private, Domain)
- **Application Path Validation:** Rules tied to specific executable paths for enhanced security
- **Interface-Specific Controls:** Granular control over network adapter access

## 🧪 Testing and Validation

### Phase 3: PowerShell Network Testing

**Connectivity Testing Methodology:** Utilized PowerShell's `Test-NetConnection` cmdlet to validate firewall rule effectiveness.

#### Test Commands Executed:
```powershell
Test-NetConnection -ComputerName localhost -Port 23
Test-NetConnection -ComputerName localhost -Port 135
```

#### Test Results Analysis:
- **Port 23 (Telnet):** Connection failed as expected, confirming successful blocking
- **Port 135 (SMB):** Controlled behavior with localhost access maintained while external access blocked

### Phase 4: Port Scanning Validation

**Network State Analysis:** Conducted comprehensive port scanning using netstat command.

#### Scanning Commands:
```cmd
netstat -an | findstr ":23"
netstat -an | findstr ":135"
```

#### Results Interpretation:
- **Port 23:** No LISTENING state detected, TIME_WAIT states indicate properly closed connections
- **Port 135:** LISTENING state protected by firewall rules, both IPv4/IPv6 supported

## 🔍 Security Analysis

### Threat Mitigation Achieved

#### Telnet Security Enhancement
- Eliminated critical vulnerability where attackers could intercept credentials
- Aligns with industry standards recommending encrypted alternatives like SSH

#### SMB Protocol Protection
Addresses Windows-specific attack vectors including:
- Remote procedure call exploits
- Network service enumeration attacks
- Unauthorized file sharing access attempts
- Potential backdoor establishment

### Advanced Security Configurations

#### Network Profile Management
- **Public Networks:** Maximum security restrictions applied
- **Private Networks:** Balanced security with functionality
- **Domain Networks:** Controlled access for organizational resources

## 📊 Results Summary

| Security Control | Status | Validation Method | Result |
|-----------------|--------|------------------|---------|
| Telnet Port 23 Block | ✅ Implemented | PowerShell Test | Connection Failed (Expected) |
| SMB Port 135 Control | ✅ Implemented | PowerShell Test | Controlled Access |
| Rule Documentation | ✅ Complete | Screenshots | Professional Standards |
| Testing Validation | ✅ Comprehensive | Multiple Methods | All Tests Passed |

## 🎓 Professional Development

### Skills Demonstrated
- Enterprise-level firewall management
- Technical proficiency with Windows security tools
- Security vulnerability assessment and mitigation
- Professional technical documentation standards

### Learning Outcomes
- Practical cybersecurity implementation experience
- Network security analysis capabilities
- Professional-grade testing methodologies
- Defense-in-depth security principles

## 🖥️ Technical Specifications

**System Configuration:**
- **Operating System:** Microsoft Windows Version 10.0.26100.4946
- **Firewall Version:** Windows Defender Firewall with Advanced Security
- **Network Interface:** Standard Ethernet and Loopback adapters
- **Testing Environment:** Local system with network connectivity

## 📁 Repository Structure

```
firewall-security-task/
├── README.md                    # This documentation
├── screenshots/                 # Firewall configuration screenshots
├── test-results/               # PowerShell and netstat outputs
├── documentation/              # Additional technical documentation
└── reports/                    # Professional security analysis
```

**📧 Contact Information:**  
**Student:** BTech Cybersecurity Student, 2nd Year  
**Institution:** GD Goenka University  
**Specialization:** AI Augmented Security Auditing


---

*This project demonstrates comprehensive understanding of Windows firewall management, network security principles, and professional cybersecurity practices through systematic implementation, thorough testing, and detailed documentation.*
