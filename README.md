# Azure Compute and Networking: Performing Network Activities

## 📌 Objective


This lab focuses on designing and deploying a basic Azure networking environment.  
A Virtual Network (VNet) with a single subnet was created, and both a Windows 11 and Ubuntu Linux virtual machine were deployed within the same IP address space to enable private communication.

The lab also analyzes network traffic behavior using Wireshark and demonstrates how Azure Network Security Groups (NSGs) control and filter traffic within the virtual network.

---

## 📑 Table of Contents

- [Section 1: Azure Environment Setup](#section-1-azure-environment-setup)
- [Section 2: Windows 11 VM Deployment](#section-2-windows-11-vm-deployment)
- [Section 3: Ubuntu Linux VM Deployment](#section-3-ubuntu-linux-vm-deployment)
- [Section 4: ICMP Traffic Analysis](#section-4-icmp-traffic-analysis)
- [Section 5: RDP Traffic Analysis](#section-5-rdp-traffic-analysis)
- [Section 6: Network Security Group (NSG) Configuration](#section-6-network-security-group-nsg-configuration)
- [Section 7: Additional Protocol Observations](#section-7-additional-protocol-observations)
- [Project Roadmap](#project-roadmap)

---

## Section 1: Azure Environment Setup

A Resource Group was created to logically organize all Azure resources used in this lab.  
This allows centralized management, simplified monitoring, and efficient cleanup.

<p align="center">
  <img src="https://github.com/user-attachments/assets/79330ec2-b737-4074-920c-96890051d95e" width="800"/>
</p>

<p align="center"><em>Figure 1: Azure Resource Group Overview</em></p>

---

## Section 2: Windows 11 VM Deployment

A Windows 11 virtual machine was deployed using the Azure portal. Configuration included:

- Selecting Windows 11 image  
- Choosing VM size  
- Configuring authentication  
- Assigning networking settings within the VNet  

<p align="center">
  <img src="https://github.com/user-attachments/assets/2fac4fdc-63c8-4158-aeb3-ed6dc0296b2b" width="750"/>
</p>

<p align="center"><em>Figure 2: Windows VM Configuration</em></p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/47c7c61a-727d-425b-af18-e1e079422b8e" width="750"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/859d7242-bbc2-49c6-a04a-011fc4fbb023" width="750"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/54a4e71a-b826-40d2-9846-eaa3689bd89f" width="750"/>
</p>

---

## Section 3: Ubuntu Linux VM Deployment

An Ubuntu Linux virtual machine was deployed within the same subnet as the Windows VM.

Key differences included:

- Selecting Ubuntu image  
- Configuring SSH authentication  
- Adjusting Linux-specific settings  

Deploying both systems in the same VNet enables cross-platform communication and administration.

<p align="center">
  <img src="https://github.com/user-attachments/assets/84361870-0efc-4741-857d-2d2ce46339dc" width="750"/>
</p>

<p align="center"><em>Figure 3: Ubuntu VM Deployment</em></p>

---

## Section 4: ICMP Traffic Analysis

Using Remote Desktop Protocol (RDP), Wireshark was installed on the Windows 11 VM.

### ICMP Filter Used:

icmp

css
Copy code

A continuous ping was initiated:

ping <Linux-Private-IP> -t

yaml
Copy code

Wireshark successfully captured ICMP Echo Requests and Echo Replies.

<p align="center">
  <img src="https://github.com/user-attachments/assets/17d2831d-cbf6-4b5c-a670-e33175653d6d" width="800"/>
</p>

---

## Section 5: RDP Traffic Analysis

Wireshark was configured to filter RDP traffic:

tcp.port == 3389

yaml
Copy code

Observed traffic showed encrypted RDP packets during the active session, demonstrating secure remote communication.

<p align="center">
  <img src="https://github.com/user-attachments/assets/bbab3159-0451-40a8-b68c-9fab41f841b5" width="750"/>
</p>

---

## Section 6: Network Security Group (NSG) Configuration

The Network Security Group associated with the Ubuntu VM was modified to deny inbound ICMP traffic.

Result:

- Echo Requests continued  
- Echo Replies stopped  
- Wireshark showed only outgoing ICMP  

This confirmed Azure firewall enforcement at the infrastructure level.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0b27d298-de0c-4ba2-9de7-dd2b08c8e878" width="800"/>
</p>

---

## Section 7: Additional Protocol Observations

### SSH Traffic

SSH session initiated from Windows VM to Ubuntu VM.

Filter used:

tcp.port == 22

yaml
Copy code

Observed encrypted SSH traffic during command execution.

---

### DHCP Traffic

Filter used:

dhcp

yaml
Copy code

Captured DHCP Discover, Offer, Request, and Acknowledge messages.

---

### DNS Traffic

Filter used:

dns

markdown
Copy code

Observed hostname resolution over UDP port 53.

---

## 🗺️ Project Roadmap

### Phase 1 — Environment Deployment
- [x] Create Resource Group  
- [x] Deploy Windows VM  
- [x] Deploy Ubuntu VM  
- [x] Configure VNet and Subnet  

### Phase 2 — Traffic Observation
- [x] Capture ICMP traffic  
- [x] Capture RDP traffic  
- [x] Capture SSH traffic  
- [x] Observe DNS and DHCP  

### Phase 3 — Security Controls
- [x] Configure NSG rules  
- [x] Block ICMP inbound traffic  
- [x] Validate rule enforcement  

### Phase 4 — Enhancements (Future Improvements)
- [ ] Add network topology diagram  
- [ ] Add Azure CLI deployment scripts  
- [ ] Add Terraform version  
- [ ] Add troubleshooting guide  

---

## ✅ Conclusion

This lab demonstrated Azure compute and networking fundamentals, including:

- VNet design  
- Cross-platform VM deployment  
- NSG-based firewall enforcement  
- Real-time protocol analysis using Wireshark  
# Azure Compute and Networking: Performing Network Activities

## 📌 Objective

This lab focuses on designing and deploying a basic Azure networking environment.  
A Virtual Network (VNet) with a single subnet was created, and both a Windows 11 and Ubuntu Linux virtual machine were deployed within the same IP address space to enable private communication.

The lab also analyzes network traffic behavior using Wireshark and demonstrates how Azure Network Security Groups (NSGs) control and filter traffic within the virtual network.

---

## 📑 Table of Contents

- [Section 1: Azure Environment Setup](#section-1-azure-environment-setup)
- [Section 2: Windows 11 VM Deployment](#section-2-windows-11-vm-deployment)
- [Section 3: Ubuntu Linux VM Deployment](#section-3-ubuntu-linux-vm-deployment)
- [Section 4: ICMP Traffic Analysis](#section-4-icmp-traffic-analysis)
- [Section 5: RDP Traffic Analysis](#section-5-rdp-traffic-analysis)
- [Section 6: Network Security Group (NSG) Configuration](#section-6-network-security-group-nsg-configuration)
- [Section 7: Additional Protocol Observations](#section-7-additional-protocol-observations)
- [Project Roadmap](#project-roadmap)

---

## Section 1: Azure Environment Setup

A Resource Group was created to logically organize all Azure resources used in this lab.  
This allows centralized management, simplified monitoring, and efficient cleanup.

<p align="center">
  <img src="https://github.com/user-attachments/assets/79330ec2-b737-4074-920c-96890051d95e" width="800"/>
</p>

<p align="center"><em>Figure 1: Azure Resource Group Overview</em></p>

---

## Section 2: Windows 11 VM Deployment

A Windows 11 virtual machine was deployed using the Azure portal. Configuration included:

- Selecting Windows 11 image  
- Choosing VM size  
- Configuring authentication  
- Assigning networking settings within the VNet  

<p align="center">
  <img src="https://github.com/user-attachments/assets/2fac4fdc-63c8-4158-aeb3-ed6dc0296b2b" width="750"/>
</p>

<p align="center"><em>Figure 2: Windows VM Configuration</em></p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/47c7c61a-727d-425b-af18-e1e079422b8e" width="750"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/859d7242-bbc2-49c6-a04a-011fc4fbb023" width="750"/>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/54a4e71a-b826-40d2-9846-eaa3689bd89f" width="750"/>
</p>

---

## Section 3: Ubuntu Linux VM Deployment

An Ubuntu Linux virtual machine was deployed within the same subnet as the Windows VM.

Key differences included:

- Selecting Ubuntu image  
- Configuring SSH authentication  
- Adjusting Linux-specific settings  

Deploying both systems in the same VNet enables cross-platform communication and administration.

<p align="center">
  <img src="https://github.com/user-attachments/assets/84361870-0efc-4741-857d-2d2ce46339dc" width="750"/>
</p>

<p align="center"><em>Figure 3: Ubuntu VM Deployment</em></p>

---

## Section 4: ICMP Traffic Analysis

Using Remote Desktop Protocol (RDP), Wireshark was installed on the Windows 11 VM.

### ICMP Filter Used:

icmp

css
Copy code

A continuous ping was initiated:

ping <Linux-Private-IP> -t

yaml
Copy code

Wireshark successfully captured ICMP Echo Requests and Echo Replies.

<p align="center">
  <img src="https://github.com/user-attachments/assets/17d2831d-cbf6-4b5c-a670-e33175653d6d" width="800"/>
</p>

---

## Section 5: RDP Traffic Analysis

Wireshark was configured to filter RDP traffic:

tcp.port == 3389

yaml
Copy code

Observed traffic showed encrypted RDP packets during the active session, demonstrating secure remote communication.

<p align="center">
  <img src="https://github.com/user-attachments/assets/bbab3159-0451-40a8-b68c-9fab41f841b5" width="750"/>
</p>

---

## Section 6: Network Security Group (NSG) Configuration

The Network Security Group associated with the Ubuntu VM was modified to deny inbound ICMP traffic.

Result:

- Echo Requests continued  
- Echo Replies stopped  
- Wireshark showed only outgoing ICMP  

This confirmed Azure firewall enforcement at the infrastructure level.

<p align="center">
  <img src="https://github.com/user-attachments/assets/0b27d298-de0c-4ba2-9de7-dd2b08c8e878" width="800"/>
</p>

---

## Section 7: Additional Protocol Observations

### SSH Traffic

SSH session initiated from Windows VM to Ubuntu VM.

Filter used:

tcp.port == 22

yaml
Copy code

Observed encrypted SSH traffic during command execution.

---

### DHCP Traffic

Filter used:

dhcp

yaml
Copy code

Captured DHCP Discover, Offer, Request, and Acknowledge messages.

---

### DNS Traffic

Filter used:

dns

markdown
Copy code

Observed hostname resolution over UDP port 53.

---

## 🗺️ Project Roadmap

### Phase 1 — Environment Deployment
- [x] Create Resource Group  
- [x] Deploy Windows VM  
- [x] Deploy Ubuntu VM  
- [x] Configure VNet and Subnet  

### Phase 2 — Traffic Observation
- [x] Capture ICMP traffic  
- [x] Capture RDP traffic  
- [x] Capture SSH traffic  
- [x] Observe DNS and DHCP  

### Phase 3 — Security Controls
- [x] Configure NSG rules  
- [x] Block ICMP inbound traffic  
- [x] Validate rule enforcement  

### Phase 4 — Enhancements (Future Improvements)
- [ ] Add network topology diagram  
- [ ] Add Azure CLI deployment scripts  
- [ ] Add Terraform version  
- [ ] Add troubleshooting guide  

---

## ✅ Conclusion

This lab demonstrated Azure compute and networking fundamentals, including:

- VNet design  
- Cross-platform VM deployment  
- NSG-based firewall enforcement  
- Real-time protocol analysis using Wireshark  

By observing ICMP, DNS, SSH, and RDP traffic before and after NSG rule changes, the lab validated how Azure controls network communication at the infrastructure level.

The exercise reinforced practical cloud security skills in troubleshooting connectivity issues, interpreting packet captures, and managing firewall rules.




By observing ICMP, DNS, SSH, and RDP traffic before and after NSG rule changes, the lab validated how Azure controls network communication at the infrastructure level.

The exercise reinforced practical cloud security skills in troubleshooting connectivity issues, interpreting packet captures, and managing firewall rules.























  
  />

















