## Windows Server 2022 Fundamentals Lab

![Windows-Server-2022-Logo](https://github.com/user-attachments/assets/6836444e-f032-441e-b319-720a43f5a740)

Windows Server is a critical tool for managing networks, users, and devices. As a Cyber Security Analyst, understanding this technology deeply is essential for identifying misconfigurations, managing access controls, and enhancing network security.

In this series, I demonstrate how I set up and manage Windows Server 2022. This project showcases my ability to configure and optimize a Windows Server environment while highlighting its importance in secure network management.

### What Will Be Covered
Task 1: Install Windows Server 2022.

Task 2: Setting up a NAT network on Virtual Box

Task 3: updating the server

Task 4: Enabling a static IP

Task 5: Enabling Remote Desktop

Task 6: Renaming the server

### Prerequisites
1. Oracle VirtualBox
  
2. Windows Server 2022 ISO (https://info.microsoft.com/ww-landing-windows-server-2022.html) 

### Task 1:  Installing Windows Server 2022.

The first step is to install Windows Server on VirtualBox. We start by creating a new virtual machine in VirtualBox, as illustrated below:

![1](https://github.com/user-attachments/assets/0a50d9c2-43b9-4f68-911b-569006c1f382)

In the VirtualBox machine setup menu, we name the machine "Windows Server 2022." We then select the ISO image corresponding to Windows Server 2022 and complete the setup by configuring the required hardware and hard disk settings for our server

![2](https://github.com/user-attachments/assets/f4eb3356-c698-493c-8786-f82ec0f6b782) 

We then boot up our machine and allow it to install the operating system. 

![3](https://github.com/user-attachments/assets/7bff187b-6faf-42d5-9306-778aa50ebf7e)

### Task 2: Setting up a NAT network on Virtual Box

The first step in this task is to create a NAT Network to which we will join our server. To achieve this, we navigate to the "NAT Networks" tab under the Tools section in VirtualBox and select "Create New." For our server, we'll use the IPv4 address range 192.168.199.0/24 and name the network "windowsserver2022," as shown in the image below:

![f](https://github.com/user-attachments/assets/685146b7-0a86-4b7b-90f8-e5a84b301946)

### Task 3: Updating the server

Next, we boot up our machine and open Server Manager. To update the server, we navigate to the "Local Server" tab on the left-hand dashboard and then select "Download Updates Only" using Windows Updates, as shown in the image below:

![7](https://github.com/user-attachments/assets/8c2a23b7-4f38-4cb5-85b0-65684b293575)

This will open Windows Update settings, where we can install any available updates by selecting "Check for updates."

![8](https://github.com/user-attachments/assets/93cc60f1-fd6f-410c-ae10-fbf5553e30d0) 

In Server Manager, we can observe that the Time Zone is set to UTC-08:00 Pacific Time US & Canada. To update this to our Time Zone, which is UTC+02:00, we click on the time zone setting. This action opens the Date and Time settings, where we can either select "Change Date and Time" or "Change Time Zones." For this server, we will change the Time Zone to UTC+02:00 Harare, Pretoria, as it matches the time zone in Malawi. By doing this, we successfully update our server's time zone.

![9](https://github.com/user-attachments/assets/360c30f2-b58b-4d16-a8c0-22cb251e27f8)

### Task 4: Enabling a static IP

