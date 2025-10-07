 Виконав самостійно Шевченко Артем РПЗ 24-А
##  Objective

To get acquainted with the popular cloud provider Amazon Web Services (AWS) and learn how to create and configure virtual machines (EC2 instances) in the AWS environment.

##  Preliminary Preparation Questions and Answers

1. **What are AMIs used for? What is the difference between private and public AMIs?**  
   AMIs (Amazon Machine Images) are templates used to create EC2 instances.  
   Public AMIs are available for all AWS users, while private AMIs are created and used within a single account or organization for specific configurations.

2. **What is the purpose of EBS? What types of EBS are supported in AWS?**  
   EBS (Elastic Block Store) provides persistent block storage for EC2 instances.  
   Main EBS types include: General Purpose SSD (gp3/gp2), Provisioned IOPS SSD (io2/io1), Throughput Optimized HDD (st1), and Cold HDD (sc1).

3. **What are Snapshots used for?**  
   Snapshots are used to back up the state of an EBS volume. They allow restoring data or creating new volumes based on the saved image.

4. **List the main types of instances in AWS. When is it appropriate to use each of them?**  
   - **General Purpose** – balanced for CPU, memory, and network (e.g., t2.micro, t3).  
   - **Compute Optimized** – for tasks needing high CPU power (e.g., c5).  
   - **Memory Optimized** – for databases or in-memory applications (e.g., r5).  
   - **Storage Optimized** – for large data processing or analytics (e.g., i3).  
   - **Accelerated Computing** – for GPU or machine learning workloads (e.g., p3).

5. **Which OS distributions are available in AWS Free Tier AMIs? Describe one for each family (Windows / Linux / Mac).**  
   - **Linux**: Ubuntu Server 22.04 LTS – lightweight, stable, and widely used; 1 vCPU, 1 GB RAM.  
   - **Windows**: Windows Server 2022 Base – includes GUI, supports Remote Desktop; 1 vCPU, 1 GB RAM.  
   - **Mac**: macOS Monterey – used for Apple app development; higher cost and resource requirements.

##  Practical Task №1 – Linux Virtual Machine

1. Logged into AWS Management Console.
2. Opened EC2 → Launch Instance.
3. Created instance named **Linux_Lab4** using **Ubuntu Server 22.04 LTS**.
4. Instance type: **t2.micro** (Free Tier).
5. Created new Key Pair for SSH connection.
6. Allowed network protocols: SSH, HTTP, HTTPS.
7. Disk size: 8 GB.
8. In User Data, added script for Nginx installation:

   ```bash
   #!/bin/bash
   sudo apt update
   sudo apt install nginx -y
   sudo systemctl start nginx
   ```

9. Verified that Nginx is running by opening the instance’s public IP in a browser.
10. Took screenshots of configuration and Nginx welcome page.

*(Screenshots would be attached here in a real repo, e.g., `screenshots/linux-config.png` and `screenshots/nginx-welcome.png`.)*

##  Practical Task №2 – Windows Virtual Machine

1. Opened EC2 → Launch Instance.
2. Created instance named **Windows_Lab4** using **Windows Server 2022 Base**.
3. Instance type: **t2.micro**.
4. Created new Key Pair and kept default network settings.
5. Connected via Remote Desktop (RDP).
6. Opened system properties and changed computer name to **AWS-Windows-Lab4**.
7. Restarted instance and confirmed name change.
8. Took screenshots of configuration, RDP session, and renamed server.

*(Screenshots would be attached here in a real repo, e.g., `screenshots/windows-config.png`, `screenshots/rdp-session.png`, and `screenshots/renamed-server.png`.)*

##  Control Questions and Answers

1. **What role does the Key Pair play when connecting to an EC2 instance?**  
   The Key Pair ensures secure authentication. The private key is used to access the instance via SSH or RDP.

2. **What command is used to connect to an EC2 instance via SSH?**  
   ```bash
   ssh -i your-key.pem ubuntu@your-public-ip
   ```

3. **How can you connect to a Linux AWS EC2 instance?**  
   Using an SSH client (e.g., PowerShell, PuTTY, or terminal) with the private key.

4. **How can you connect to a Windows AWS EC2 instance?**  
   By using Remote Desktop Connection (RDP) with the administrator password decrypted using the private key.

5. **What is the difference between Stop and Terminate states?**  
   - **Stop**: the instance is turned off but can be started again.  
   - **Terminate**: the instance and its data are permanently deleted.

##  Conclusion

During this laboratory work, I learned how to create and configure virtual machines in AWS using both Linux and Windows operating systems.  
I practiced connecting to EC2 instances through SSH and RDP, installing and running a web server, and managing instance states.  
This helped me understand the basics of cloud infrastructure and virtual server management in AWS.

---
