## Simple Elastic SIEM Lab

My first project is a Simple Elastic SIEM lab, where I’m exploring how to set up and use Elastic Security for monitoring and detecting potential threats. It’s a hands-on dive into the basics of SIEM tools and cybersecurity!


### Task 1 
The first step in setting up a Simple Elastic SIEM lab is signing up for the Elastic SIEM free trial. The registration process is straightforward and provides access to all the tools needed for the lab.

![1](https://github.com/user-attachments/assets/402b5a8e-809d-40d1-9e59-74a0c38789bf)

Once the account is created, we log in to the Elastic dashboard.

### Task 2

The second step is to install VirtualBox, which will allow us to manage our virtual machines. After that, we download and set up the Kali Linux virtual image, a powerful tool for penetration testing and cybersecurity tasks. With both VirtualBox and Kali Linux ready, let's set up  Elastic SIEM.

![3](https://github.com/user-attachments/assets/ae04c696-789e-4904-80c7-356df6feeddf)

### Task 3

The third step involves navigating to the "Add Integrations" section in the Elastic dashboard and selecting the "Elastic Defend" integration, which is used for host monitoring and protection.

![7](https://github.com/user-attachments/assets/70006166-c8c0-434b-a25c-eaeff2a7fda0)

### Task 4

The fourth step is to install the Elastic Agent on our Kali host. Using the documentation provided on the Elastic web page, we copy the code for the Linux integration and paste it into the terminal on our Kali machine. 

![8](https://github.com/user-attachments/assets/21c5c2b2-649a-41b8-8b91-0a5bfe77c5ef)

![9](https://github.com/user-attachments/assets/e698953a-1489-48ab-85bd-8a58d3cadfde)

Additionally, to confirm that the integration is running, we confirm by running the following command in the terminal: 

 ```tsql
sudo systemctl status elastic-agent.service
 ```

![10](https://github.com/user-attachments/assets/4b7d5841-1a5f-485d-9688-fa8def2bc4b8)

### Task 5

To confirm log data is being sent from your Kali virtual machine to the SIEM, run the command:

``` tsql
nmap -p- localhost
```
![11](https://github.com/user-attachments/assets/8a9b35c0-2b38-4d79-ad55-cc8e32307858)

Now we go back to the Elastic Dashboard and 

