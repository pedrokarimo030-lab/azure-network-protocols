# Azure-Network-Protocols

Azure Compute and Networking: Performing Network Activities.

This project starts by creating an Azure Resource Group, followed by the deployment of two virtual machines: a Windows 10/11 VM and a Linux VM. I create a new Virtual Network (VNet) with a single subnet and place both virtual machines within this network to ensure they operate on the same IP address space and can communicate directly. 

This fig. 1 is the Resource Group

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/79330ec2-b737-4074-920c-96890051d95e" />

Fig. 2 shows the process of creating a Windows 11 VM and the point of deployment.

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/859d7242-bbc2-49c6-a04a-011fc4fbb023" />


<img width="975" height="808" alt="image" src="https://github.com/user-attachments/assets/2fac4fdc-63c8-4158-aeb3-ed6dc0296b2b" />


<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/47c7c61a-727d-425b-af18-e1e079422b8e" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/76df736d-0120-403d-b871-98787482396e" />

<img width="1049" height="439" alt="image" src="https://github.com/user-attachments/assets/54a4e71a-b826-40d2-9846-eaa3689bd89f" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/55135af1-c5aa-4ba8-94c2-e53c06a08bb3" />


Creating a Linux (LX) VM is largely similar to creating a Windows VM; however, there are a few key differences. These include selecting a Linux distribution such as Ubuntu and configuring Linux-specific options during setup. Despite these differences, the overall deployment process remains straightforward, and successfully creating both VMs provides valuable hands-on experience with cross-platform system administration in a cloud environment.

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/84361870-0efc-4741-857d-2d2ce46339dc" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/7f694675-fb6b-4410-a343-99ede49c81ac" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/8753bb6d-e591-49c8-b898-0e603ad73fc1" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/c151b223-9138-4f2f-8122-e353eb5dbc8d" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/a38c8581-c8c7-4da7-8943-228289593727" />

<img width="975" height="549" alt="image" src="https://github.com/user-attachments/assets/54726b26-4c4b-4eea-b528-c612e76753e6" />

Section 2: Observing ICMP Traffic

This section focuses on analyzing Internet Control Message Protocol (ICMP) traffic between two virtual machines. Using Remote Desktop Protocol (RDP), I connect to a Windows 11 VM, install Wireshark, and begin packet capture. I filter the captured traffic to display ICMP packets only.

After retrieving the private IP address of the Ubuntu (Linux) VM, I initiate a ping from the Windows 11 VM to the Linux VM and analyze the resulting ICMP echo requests and echo replies in Wireshark

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/17d2831d-cbf6-4b5c-a670-e33175653d6d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/cd0cb664-0a30-4810-825b-b5b33454980b" />




<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/0a8d210d-1a45-40ca-999b-24af09312bda" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/bbab3159-0451-40a8-b68c-9fab41f841b5" />

<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/25284e05-440c-4424-97b5-0a2286a0fe3d" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/eaa261c6-72c2-4c45-b5cf-38c4803decaf" />




  
  />

















