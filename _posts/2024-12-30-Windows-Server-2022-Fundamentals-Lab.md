## Active Directory Lab

![Microsoft Active Directory](https://github.com/user-attachments/assets/4f0b1532-79a4-4756-a74c-ddce8055fc6f)

Active Directory (AD) is a critical tool for managing networks, users, and devices. As a Cyber Security Analyst, I understand this technology deeply, which is essential for identifying misconfigurations, managing access controls, and enhancing network security.

In this series, I demonstrate how I set up and manage Active Directory on Windows Server 2022. This project showcases my ability to configure and optimize AD while highlighting its importance in secure network management.

### What Will Be Covered
Part 1: Install Active Directory on Windows Server 2022.

Part 2: Setting up a NAT network, updating the server, enabling a static IP, enabling Remote Desktop, and renaming the server.

Part 3: Transforming the server into a domain controller and joining it to a domain.

Part 4: Configuring DNS forward lookup zones.

Part 5: Joining a Windows 11 device to my domain.

Part 6: Creating Organizational Units (OUs), users, and groups, and demonstrating logging into accounts.

Part 7: Sharing folders securely within the AD environment.

### Prerequisites
1. Oracle VirtualBox
  
2. Windows Server 2022 ISO

### Part 1: Installing Windows Server 2022.

### Task 1

The first step is to install Windows Server on Virtual Box if we have not done so already. We do this by creating a new machine as seen below: 

![1](https://github.com/user-attachments/assets/0a50d9c2-43b9-4f68-911b-569006c1f382)

We then proceed to name the machine Windows Server 2022 select the ISO image corresponding to Windows Server 2022, and finish setting up the required Hardware and hard disk configurations for our server.

![2](https://github.com/user-attachments/assets/f4eb3356-c698-493c-8786-f82ec0f6b782) 

### Part 2 

### Task 1

The first thing we do for task 1 is to create a NAT Network to which we will join our server. This is done by going to the NAT Networks tab under the tools section in Virtual Box and then selecting Create New. For our server, we will have the IPv4 of 192.168.199.0/24 and name the network windowsserver2022 as seen in the image below: 

![f](https://github.com/user-attachments/assets/685146b7-0a86-4b7b-90f8-e5a84b301946)

### Task 2: Updating the Server

We then boot up our machine and open up Server Manager. We want to update the server so we do this by navigating to the "local server" on the left dashboard and then selecting Download Updates only using Windows Updates as seen in the image below: 

![7](https://github.com/user-attachments/assets/8c2a23b7-4f38-4cb5-85b0-65684b293575)

This will then open up Windows Update Settings, where we can install available updates to our machine if there are any when we select "Check for updates" 

![8](https://github.com/user-attachments/assets/93cc60f1-fd6f-410c-ae10-fbf5553e30d0)
 

### Task 3: Updating Server Time Zone 
In the Server Manager, we can see that the Time Zone is set to UTC-08:00 Pacific Time US & Canada. To update this to my Time Zone which is UTC+02:00, we select the time zone, which opens up the Date and Time settings where we can either click Change Date and Time or Change Time Zones. For this server, we will change the Time Zone to UTC+02:00 Harare, Pretoria being that it is the same as here in Malawi. With this, we will have updated our server successfully. 

![9](https://github.com/user-attachments/assets/360c30f2-b58b-4d16-a8c0-22cb251e27f8)

### Task 4:  

