# Securing-Remote-Access-for-Linux-Virtual-Machines-on-Azure
## Objective
Understand the fundamentals of securing remote access.
Configure remote access for Linux VMs on Azure.
Implement best practices for securing SSH connections.
Utilize Azure security features to enhance VM protection

### Skills Learned


- Configuring Azure Virtual Machines: Learn how to set up Linux VMs on Azure, -including selecting appropriate settings and options for your needs.
- Securing Remote Access: Understand how to configure SSH access securely, including the use of SSH key pairs and the disabling of password authentication.
- Network Security Group (NSG) Management: Gain experience in configuring NSG rules to control and monitor inbound and outbound traffic to your VMs.
- Best Practices for Linux Security: Learn best practices for securing Linux servers, including the use of firewalls, monitoring, and logging.
- Using Azure Security Features: Explore Azure-specific security features such as Azure Bastion for secure connectivity without exposing VMs to the public internet.
- Troubleshooting Connectivity Issues: Develop troubleshooting skills for common issues related to SSH access and VM connectivity.
### Tools Used
Tools Used
1. Azure Portal
Used to create and manage Linux Virtual Machines.
Configured Network Security Groups (NSGs) and enabled Just-In-Time (JIT) VM access.
2. SSH (Secure Shell)
The primary tool for remote access to the Linux VM.
Configured SSH key-based authentication and disabled password-based login.
3. Azure Bastion
Securely accessed the Linux VM without exposing its public IP.
Enhanced security by providing remote access over a secure Azure-managed connection.
4. Azure CLI (Command Line Interface)
Managed Azure resources like VMs and NSGs via the command line.
Deployed and configured security settings using commands.
5. Network Security Groups (NSG)
Restricted SSH access to specific IP addresses by setting up inbound and outbound security rules.
6. Azure Security Center
Monitored security configurations and detected vulnerabilities in the Linux VM.
Enabled Just-In-Time (JIT) access for time-limited remote sessions.
7. Linux Command-Line Tools
Configured and managed SSH settings.
Used tools like nano, systemctl, and sshd_config for editing configuration files and restarting services.

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Steps
