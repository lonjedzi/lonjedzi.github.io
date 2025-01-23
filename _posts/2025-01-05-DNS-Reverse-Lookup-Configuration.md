## DNS Reverse Lookup Configuration

![OIP](https://github.com/user-attachments/assets/1cb0c259-9e87-4508-8313-f3a97bd56af6)

In the previous blog, we successfully installed Active Directory and DNS on our server, transforming it into a functional domain controller. Now, it’s time to take the next step: properly configuring the DNS. As the backbone of network communication, DNS ensures seamless name resolution within our domain, a critical component for maintaining a secure and efficient network

First, we run the nslookup command to verify that our DNS server is functioning correctly. This command helps us check if the server can resolve domain names to IP addresses, ensuring the DNS is properly integrated with our Active Directory setup.

![a](https://github.com/user-attachments/assets/2d867f1c-9f2a-47f7-b00f-2cc002cf07a1)

Running the nslookup command returns:

  Default Server: Unknown  
  IP Address: 192.168.199.4

This output indicates that while the DNS server is reachable at the correct IP address (192.168.199.4), it does not yet have a configured hostname. This will be addressed as we proceed with properly setting up the DNS.

To address this issue, the fix is simple. We start by opening Server Manager, then navigating to Tools > DNS.

![z](https://github.com/user-attachments/assets/1068d24d-38fa-4783-af0e-b6f7c1991f12)

Next, we click on our server name in the DNS Manager. From the options available, we select Reverse Lookup Zone. To proceed, right-click on the Reverse Lookup Zone and choose Create New Zone.
This launches the New Zone Wizard, as shown in the image below:

![y](https://github.com/user-attachments/assets/38a45c68-c53c-49bb-8066-6428439e1463)

We click Next to proceed, and then we create a new Primary Zone, as the zone will be on our server. 

![x](https://github.com/user-attachments/assets/e97b5772-d8db-4282-86fd-c408580ad0e4)

Our reverse lookup zone will be for IPv4, so we select that option and click Next to proceed.

![w](https://github.com/user-attachments/assets/73cee6c1-1bc3-4b67-8d6e-cd76ab6b1200)

For the Reverse Lookup Zone name, enter the network ID 192.168.199 as shown below:

![v](https://github.com/user-attachments/assets/092de0fc-170b-4e1d-acda-8a1d49e5661d)

Allow secure dynamic updates yes

![u](https://github.com/user-attachments/assets/dc2f0821-20b8-4974-a967-a0b5381cbeca)

To complete the process and add the zone, click "Finish" to close the wizard.

![t](https://github.com/user-attachments/assets/547e0d29-6896-40c9-836d-cf4f12d50dcf)

In the final step, navigate to Forward Lookup Zones > smalloffice.com, click on Win22-dc, and check "Update associated pointer records."

![s](https://github.com/user-attachments/assets/f307f3e0-eedd-420d-ae6f-9cd0c4901b40)

After running the nslookup command again in PowerShell, the result now shows a valid response, and we no longer see "unknown."

![r](https://github.com/user-attachments/assets/af90aea0-14ad-4039-a55c-52912d14d75a)


