# Guide to Deploying a Secure, Highly Available Virtual Machine (VM) in Azure

## Objectives
- Set up a Secure, Highly Available Virtual Machine (VM) in Azure


## Technologies Used
- Azure

## Steps

#Planning
Plan Your Azure Virtual Machine Resources
1. Determine VM Size and Type
Objective: Choose the appropriate VM size based on the application’s workload.
Use General Purpose VMs (like D-series or E-series) for balanced CPU, memory, and storage needs.
For CPU-intensive workloads, use Compute Optimized VMs (F-series).
Memory-Optimized VMs (M-series or E-series) are ideal for memory-heavy applications like databases.
Example: Choose a D4s_v3 (4 vCPUs, 16 GB RAM) for a moderate web application, providing a good balance between CPU, memory, and cost.

2. Select the Operating System
Objective: Choose between Windows or Linux based on the application.

Linux VMs are preferred for open-source applications and web servers like Nginx or Apache.
Windows VMs are necessary for Windows-specific applications such as those built with .NET.
Example: For a web app running PHP, use Ubuntu 20.04 for cost-effectiveness and open-source support.

3. Availability and Redundancy
Objective: Ensure that the VM remains available even if one part of the infrastructure fails. 
Options:
Availability Set: Protects against hardware failures within a single data center and is a cheaper option than availability zones.

Availability Zone: Offers higher availability by placing VMs in physically separate locations.

Use Availability Zones for high availability and fault tolerance. If one zone fails, the VM in another zone will still be operational.
Alternatively, use an Availability Set for protection from hardware failures within a single data center.
Example: Place VMs in two different Availability Zones within a region for higher redundancy.

4. Storage Options
Objective: Choose a storage option that balances performance and redundancy.
Options:
Standard HDD/SSD: Good for dev/test environments or low-IO workloads.
Premium SSD: Ideal for production workloads requiring low latency and high performance.
Ultra SSD: Best for IO-intensive applications like databases.
Justification:
Use Premium SSD for fast read/write operations and better reliability in production environments.
Example: Use a Premium SSD (P30) disk for the operating system and data storage.
5. Networking (Virtual Network)
Objective: Configure networking to ensure secure and efficient communication.
Justification:
Create a dedicated Virtual Network (VNet) to  isolate your resources.
Subdivide the VNet into subnets to separate app tiers (e.g., web, database).
Example:
Create a VNet with two subnets: one for the web tier and another for the database tier.
Use Network Security Groups (NSGs) to control inbound/outbound traffic.

Step 2: Create a Virtual Network (VNet)
Navigate to Virtual Networks:

In the Azure portal, search for and select Virtual Networks.
Click Create.
Configure the VNet:

Name: Choose a name for your VNet (e.g., MySecureVNet).
Region: Choose the region closest to your users.
IP Addressing: Set an address space (e.g., 10.0.0.0/16).
Subnets:
Create two subnets:
WebSubnet (e.g., 10.0.1.0/24) for the front-end web server.
DbSubnet (e.g., 10.0.2.0/24) for the back-end database server.
Step 3: Create a Network Security Group (NSG)
Create an NSG:

In the Azure portal, search for and select Network Security Groups.
Click Create and specify a name and region.
Configure NSG Rules:

Inbound Security Rules:
Allow traffic on port 22 (for SSH) or port 3389 (for RDP).
Allow traffic on port 80 (HTTP) and port 443 (HTTPS) for web traffic.
Outbound Security Rules: Allow outbound traffic as required.
Associate NSG with Subnets:

Associate your NSG with both WebSubnet and DbSubnet to secure traffic within the VNet.
Step 4: Deploy a Virtual Machine
Navigate to Virtual Machines:

In the Azure portal, search for Virtual Machines.
Click Create.
Basic Configuration:

Resource Group: Select the resource group you created earlier.
VM Name: Give your VM a name (e.g., MySecureVM).
Region: Choose the region (e.g., East US).
Availability Options: Select Availability Zone for high availability.
Image: Select the desired OS image (e.g., Ubuntu 20.04 LTS).
VM Size: Choose the appropriate size (e.g., D4s_v3).
Authentication:

Choose SSH public key for Linux VMs or password for Windows VMs.
Upload an SSH public key or generate one for secure authentication.
Step 5: Configure Disks
OS Disk Type: Select Premium SSD for better performance.
Additional Data Disks: Optionally add data disks if your application requires additional storage.
Step 6: Configure Networking
Virtual Network: Select the VNet you created (MySecureVNet).
Subnet: Select the WebSubnet.
Public IP: Create a new public IP for remote access (if needed).
NSG: Select the NSG you created to secure the VM.
Step 7: Configure Management
Monitoring: Enable Boot Diagnostics and Auto-Shutdown to improve cost efficiency and diagnostics.
Backup: Enable Azure Backup for data protection.
Step 8: Review and Create
Review Configuration: Go over your configuration and ensure everything is correct.
Click Create: Once validated, click Create to deploy the VM. This process can take a few minutes.
Step 9: Enable Auto-Scaling and Load Balancing
Create a Load Balancer:

Search for Load Balancers in the Azure portal and create a new one.
Configure a Public IP for the load balancer.
Add your VMs to the load balancer's backend pool to distribute traffic between them.
Configure Auto-Scaling:

Navigate to the VM Scale Set section and set up auto-scaling rules to automatically add or remove VMs based on CPU usage or other metrics.
Step 10: Secure the VM
Enable Just-In-Time VM Access:

Use Azure Security Center to enable Just-in-Time (JIT) VM access, allowing you to limit SSH/RDP access to specific time windows.
Enable Disk Encryption:

Use Azure Disk Encryption to encrypt your VM disks with Azure Key Vault.
Configure Firewalls:


