# Azure Compute and Networking: Performing Network Activities

Objective:

The purpose of this lab is to design and deploy a basic Azure networking environment, deploy cross-platform virtual machines, and observe network traffic behavior using packet analysis tools. The lab also demonstrates how Azure Network Security Groups (NSGs) control traffic flow within a virtual network. A new Virtual Network (VNet) with a single subnet is created. Both virtual machines are deployed into this same subnet to ensure they share the same IP address space and can communicate directly using private IP addresses.

Section 1: Azure Environment Setup
Resource Group Creation

The lab begins by creating an Azure Resource Group, which serves as a logical container for all Azure resources used in this project. This approach simplifies resource management, monitoring, and cleanup.

(Figure 1: Resource Group Overview)

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/79330ec2-b737-4074-920c-96890051d95e" />

Windows 11 Virtual Machine Deployment
A Windows 11 virtual machine is created using the Azure portal. The configuration process includes selecting the appropriate image, VM size, authentication method, and networking options. Once the configuration is complete, the VM is successfully deployed.

(Figure 2: Windows 11 VM Creation Process)

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/859d7242-bbc2-49c6-a04a-011fc4fbb023" />


<img width="975" height="808" alt="image" src="https://github.com/user-attachments/assets/2fac4fdc-63c8-4158-aeb3-ed6dc0296b2b" />


<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/47c7c61a-727d-425b-af18-e1e079422b8e" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/76df736d-0120-403d-b871-98787482396e" />

<img width="1049" height="439" alt="image" src="https://github.com/user-attachments/assets/54a4e71a-b826-40d2-9846-eaa3689bd89f" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/55135af1-c5aa-4ba8-94c2-e53c06a08bb3" />


Linux (Ubuntu) Virtual Machine Deployment
A Linux virtual machine (Ubuntu) is deployed following a similar process to the Windows VM. Key differences include selecting a Linux distribution and configuring Linux-specific settings such as SSH authentication. Despite these differences, the overall deployment process remains straightforward.
Deploying both Windows and Linux virtual machines in the same environment provides practical experience with cross-platform system administration in a cloud network.


<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/84361870-0efc-4741-857d-2d2ce46339dc" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/7f694675-fb6b-4410-a343-99ede49c81ac" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/8753bb6d-e591-49c8-b898-0e603ad73fc1" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/c151b223-9138-4f2f-8122-e353eb5dbc8d" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/a38c8581-c8c7-4da7-8943-228289593727" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/54726b26-4c4b-4eea-b528-c612e76753e6" />

Section 2: Observing ICMP Traffic
Packet Capture Setup
Using Remote Desktop Protocol (RDP), the lab connects to the Windows 11 virtual machine. Wireshark is installed and configured to begin packet capture. A display filter is applied to show only ICMP traffic:
icmp


<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/17d2831d-cbf6-4b5c-a670-e33175653d6d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cd0cb664-0a30-4810-825b-b5b33454980b" />




<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/0a8d210d-1a45-40ca-999b-24af09312bda" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/bbab3159-0451-40a8-b68c-9fab41f841b5" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/25284e05-440c-4424-97b5-0a2286a0fe3d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eaa261c6-72c2-4c45-b5cf-38c4803decaf" />

Section 3 focuses on configuring a firewall using a Network Security Group (NSG) and initiating a continuous ping from the Windows 11 VM to the Ubuntu VM. First, the lab opens the Ubuntu VM’s Network Security Group and disables inbound ICMP traffic.

Next, from the Windows 11 VM, the lab observes ICMP traffic using Wireshark alongside the ongoing ping activity in the command line. Afterward, the lab re-enables inbound ICMP traffic in the Ubuntu VM’s Network Security Group.

Returning to the Windows 11 VM, the lab confirms that ICMP traffic resumes in both Wireshark and the command-line ping output, indicating restored network connectivity. Finally, the lab stops the ping activity.

Firewall turn off

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/1a6a8583-797a-4c5e-b07d-2335bd40b0c2" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/fe2b420b-5604-4180-8a1c-310a8f034338" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/042d27b0-6fbd-4e94-b606-3ecbf5305a83" />


<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/219cd47e-bf6d-4a61-b775-0014fab1ccde" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/fe204e23-ce73-48e3-8472-b581f7463daa" />

Disabling incoming (inbound) ICMP Traffic

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/134bff45-3a2d-41ad-860a-7c2461dddb54" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/4121b5e2-bae3-4c39-b551-155405663652" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/dab73b14-d103-439b-a74f-fee426fd1737" />

Fig. below shows perpetual traffic before traffic denial

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/543bb990-d213-4872-9201-390e746cd77b" />


In contrast, the figure that follows shows only Requests and no Replies, meaning there was no communication between the two devices: (Linux Private IP address 172.17.0.4 and the Public IP address 52.190.17.69) after the denial of ICMP Traffic.

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/eba39179-7e9f-43d6-b632-0c6b24f046d8" />

SSH Traffic

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/cca955de-74b5-4e00-b569-1e82f52e5b95" />

DHCP Traffic in Wireshark, filtering for DHCP only

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/6b07c1ba-ec79-4fee-abf7-7768d71a1661" />

DNS Traffic

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/97da3435-8974-42e4-9625-4d449186baf9" />

RDP Traffic, filtering in Wireshark for RDP traffic only (TCP.Port==3389)

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/c8290915-a47e-477b-872b-b88bd766e39b" />

This lab successfully demonstrated Azure compute and networking fundamentals, including VNet design, VM deployment, NSG-based traffic filtering, and protocol analysis using Wireshark. By observing ICMP, DNS, and RDP traffic before and after NSG rule changes, the lab validated how Azure controls network communication at the infrastructure level. The exercise reinforced practical skills in troubleshooting connectivity issues, interpreting packet captures, and managing cloud firewall rules.



























  
  />

















