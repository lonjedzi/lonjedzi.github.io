## DNS Reverse Lookup Configuration

![reverse-dns-jpg](https://github.com/user-attachments/assets/999a6afd-040f-4ff4-8260-04ea120c776a)


In the previous blog, we successfully installed Active Directory and DNS on our server, transforming it into a functional domain controller. Now, it’s time to take the next step: properly configuring the DNS. As the backbone of network communication, DNS ensures seamless name resolution within our domain, a critical component for maintaining a secure and efficient network

First, we run the nslookup command to verify that our DNS server is functioning correctly. This command helps us check if the server can resolve domain names to IP addresses, ensuring the DNS is properly integrated with our Active Directory setup.

![a](https://github.com/user-attachments/assets/2d867f1c-9f2a-47f7-b00f-2cc002cf07a1)

Running the nslookup command returns:

  Default Server: Unknown  
  IP Address: 192.168.199.4

This output indicates that while the DNS server is reachable at the correct IP address (192.168.199.4), it does not yet have a configured hostname. We will address this as we proceed with properly setting up the DNS.

To address this issue, the fix is simple. We start by opening Server Manager, then navigate to Tools > DNS. This will open the DNS Manager, where we can configure the necessary settings to resolve the hostname issue and ensure proper DNS functionality.

![z](https://github.com/user-attachments/assets/1068d24d-38fa-4783-af0e-b6f7c1991f12)

Next, we click on our server name in the DNS Manager. From the available options, we select Reverse Lookup Zone. To proceed, right-click on Reverse Lookup Zone and choose Create New Zone. This action launches the New Zone Wizard, where we can configure the reverse lookup zone settings:

![y](https://github.com/user-attachments/assets/38a45c68-c53c-49bb-8066-6428439e1463)

We click Next to proceed, and then we create a new Primary Zone, as the zone will be on our server. 

![x](https://github.com/user-attachments/assets/e97b5772-d8db-4282-86fd-c408580ad0e4)

Since our reverse lookup zone will be for IPv4, we select that option and click Next to proceed with the configuration. This will allow the server to handle reverse DNS lookups for IPv4 addresses.

![w](https://github.com/user-attachments/assets/73cee6c1-1bc3-4b67-8d6e-cd76ab6b1200)

For the Reverse Lookup Zone name, enter the network ID 192.168.199 as shown below:

![v](https://github.com/user-attachments/assets/092de0fc-170b-4e1d-acda-8a1d49e5661d)

In the next step, we select Allow secure dynamic updates to ensure that only authorized devices can register and update their DNS records. This enhances the security of our DNS configuration by preventing unauthorized changes. 

![u](https://github.com/user-attachments/assets/dc2f0821-20b8-4974-a967-a0b5381cbeca)

To complete the process and add the zone, click "Finish" to close the wizard.

![t](https://github.com/user-attachments/assets/547e0d29-6896-40c9-836d-cf4f12d50dcf)

In the final step, navigate to Forward Lookup Zones > smalloffice.com, click on Win22-dc, and check the option for Update associated pointer records. This ensures that the reverse lookup zone is properly linked to the forward lookup zone, allowing seamless resolution between hostnames and IP addresses. After making this selection, click Next to complete the configuration.

![s](https://github.com/user-attachments/assets/f307f3e0-eedd-420d-ae6f-9cd0c4901b40)

After running the nslookup command again in PowerShell, the result now shows a valid response, and we no longer see "Unknown." This confirms that our DNS configuration is working properly, and the server is correctly resolving domain names to IP addresses.

![r](https://github.com/user-attachments/assets/af90aea0-14ad-4039-a55c-52912d14d75a)

### Conclusion

With the DNS properly configured, our server is now capable of handling both forward and reverse lookups, ensuring smooth name resolution within our network. This configuration enhances the security and functionality of our Active Directory setup, setting the stage for a fully operational domain environment.

