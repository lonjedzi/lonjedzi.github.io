## DNS Reverse Lookup Configuration

![OIP](https://github.com/user-attachments/assets/1cb0c259-9e87-4508-8313-f3a97bd56af6)

In the previous blog, we successfully installed Active Directory and DNS on our server, transforming it into a functional domain controller. Now, it’s time to take the next step: properly configuring the DNS. As the backbone of network communication, DNS ensures seamless name resolution within our domain, a critical component for maintaining a secure and efficient network

First, we run the nslookup command to verify that our DNS server is functioning correctly. This command helps us check if the server can resolve domain names to IP addresses, ensuring the DNS is properly integrated with our Active Directory setup.

![a](https://github.com/user-attachments/assets/2d867f1c-9f2a-47f7-b00f-2cc002cf07a1)

Running the nslookup command returns:

  Default Server: Unknown  
  IP Address: 192.168.199.4

This output indicates that while the DNS server is reachable at the correct IP address (192.168.199.4), it does not yet have a configured hostname. This will be addressed as we proceed with properly setting up the DNS.


