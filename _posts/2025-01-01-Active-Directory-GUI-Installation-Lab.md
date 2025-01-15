## Active Directory Installation Lab

![Microsoft Active Directory](https://github.com/user-attachments/assets/bf348d47-24e4-4762-9f19-2693943c904b) 

In our last blog, we set up Windows Server 2022 on a virtual machine and completed key tasks like configuring a NAT network, enabling a static IP, setting up Remote Desktop, and renaming the server. Now, we’re moving forward with Active Directory (AD), a vital tool for managing and securing network resources. Let’s log in to our server, access Server Manager, and begin the AD installation.

### Installing Active Directory
In Server Manager, we  click on the Manage option in the top-right corner of the dashboard and select Add Roles and Features. This action launches the Add Roles and Features Wizard, which will guide us through the process of installing Active Directory and setting up a domain controller.

![b](https://github.com/user-attachments/assets/9541eaea-fee6-465a-a749-d2a98b6d5d88)

In the Server Selection step of the wizard, select your server from the list and click Next.

On the Server Roles menu, we check the boxes for Active Directory Domain Services (AD DS) and DNS Server. These roles are essential for creating and managing a domain controller and ensuring proper domain name resolution within your network. After selecting these roles, we click Next to proceed.

![d](https://github.com/user-attachments/assets/4be7de8b-55fc-406b-8dfd-eb3146c33304)

In the Features menu, leave the default selections as they are and click Next.

Similarly, on the Active Directory Domain Services and DNS Server menus, we review the information and click Next without making changes. We continue this process until you reach the Confirmation menu, where we can review selected roles and features before proceeding with the installation. 

![e](https://github.com/user-attachments/assets/58a21bcd-2455-4cae-811d-950cec600e79)

After a successful installation, we click on the Promote this server to a domain controller option in the menu. This will open the Active Directory Domain Services Configuration Wizard.

![g](https://github.com/user-attachments/assets/af5f10fe-25d1-409a-b77f-0edee4efe8ec)

In the Deployment Configuration menu, we select Add a new forest and enter the forest name as smalloffice.com. Once entered, we click Next to proceed with the domain controller configuration.

![h](https://github.com/user-attachments/assets/b758ba7f-3e57-45d7-b556-d21f2f2c8e55)

In the Domain Controller Options menu, we leave all settings as default and only add a Directory Services Restore Mode (DSRM) password. This password is used for restoring Active Directory in case of a failure. Once you’ve set the DSRM password, click Next to proceed.

![i](https://github.com/user-attachments/assets/b49a1349-e838-406b-8f90-e08727dd7f6c)

In the Additional Options menu, we confirm the NetBIOS name and proceed.

In the Paths menu, we leave the default settings for the Database, Log files, and SYSVOL paths.

Next, we review our configurations on the Review menu. After confirming everything is correct, we click Next and allow the wizard to complete the prerequisite checks before moving forward.

![j](https://github.com/user-attachments/assets/39c43e63-19f8-4fb4-9459-00beed611633)

After the prerequisite checks pass, we proceed with the installation. Once complete, we allow the server to reboot and apply all changes and settings automatically.

After the reboot is completed successfully, we open Server Manager to verify that the domain has been updated. Here, we confirm that Active Directory Domain Services (AD DS) and DNS are now available and functioning as expected.

![k](https://github.com/user-attachments/assets/168c7111-4b18-42bb-964b-92e5ee27ec87)

After the reboot, we notice there is no internet connection. To resolve this, we navigate to Network Settings > Ethernet Status > Properties > IPv4. Here, we find that the DNS has been changed to 127.0.0.1, which differs from our intended configuration. We update this back to 192.168.199.4, the IP address of our machine, restoring the intended settings. 

To access Active Directory, we return to Server Manager, click on Tools, and select Active Directory Users and Computers. Here, we can confirm that Active Directory is live and operational.

![l](https://github.com/user-attachments/assets/f2361d2b-5faf-497e-ae15-c4ff50bf1d97)

### Conclusion 
With Active Directory now live and operational, we’ve successfully set up a secure and manageable domain controller. This marks a critical step in our cybersecurity project, laying the foundation for effective network management and security. Stay tuned for the next phase as we dive deeper into utilizing AD for advanced configurations and management
