# Detection Home Lab

## Objective

Design and implement a cybersecurity environment comprising four distinct Virtual Machines (VMs) using Oracle VirtualBox: Active Directory, Splunk, Kali Linux, and Atomic Red Team. Establish user accounts within the Active Directory VM. Integrate a NAT network configuration with static IP addressing across all VMs to enable seamless communication for event ingestion into Splunk. Utilize Atomic Red Team to simulate real-world attack scenarios aligned with the MITRE ATT&CK framework, generating actionable telemetry data for analysis and mitigation.

### Skills Learned

- Virtualization: Proficiency in setting up and configuring virtual machines using tools like Oracle VirtualBox.<br>
- Networking: Knowledge of networking concepts including NAT configuration and IP addressing for inter-VM communication.<br>
- Active Directory Management: Ability to create and manage user accounts within an Active Directory environment.<br>
- Security Tools: Familiarity with security tools such as Splunk for log management and analysis.<br>
- Penetration Testing: Experience with Kali Linux for conducting penetration tests and vulnerability assessments.<br>
- Threat Simulation: Understanding of threat emulation frameworks like Atomic Red Team for simulating real-world attack scenarios.<br>
- MITRE ATT&CK Framework: Knowledge of the MITRE ATT&CK framework for mapping and categorizing cyber threats and techniques.<br>


### Tools Used

- Oracle VirtualBox<br> 
- Active Directory<br>
- Splunk<br>
- Kali Linux<br>
- Atomic Red Team<br>
- MITRE ATT&CK Framework<br>


## Steps

Step 1- Create a network diagram to show the flow of traffic. Both Windows 10 and the Active Directory server will be forwarding data to the Splunk Server.   ![Diagram Active Directory Final](https://github.com/hknapp518/HomeLab/assets/125601731/ddbfe115-7637-4956-b199-a4cff686b3bd)

Step 2- Open Windows Server VM and promote it to a Domain Controller. Create two Organizational Units (IT & HR) and add users in Active Directory.
![Vittoria in HR](https://github.com/user-attachments/assets/a7257fe6-6109-4d51-a59d-e75a5b4502ad)
![Ana in Active Directory HR](https://github.com/user-attachments/assets/a17df7ba-ebaf-4eb0-a396-47f7e7f99df1)

Step 3- Configure the Windows 10 machine to join to the AD.
![configure my windows 10 machine to join to the AD](https://github.com/user-attachments/assets/77b67a1a-f57a-4f2d-b740-1a6ea0cdcc24)

Step 4- Configure Kali Linux to a static IP address according to the graph.
![Configure our Kali Linux to a static IP address according to the graph](https://github.com/user-attachments/assets/58d7475d-501d-4862-bb73-37934501c970)

Step 5- Create a directory called "ad-project" and download Crowbar to perform a brute force attack. 
![Create a directory called ad-project and download crowbar to perform a brute for attack ](https://github.com/user-attachments/assets/9e7989c4-4605-4057-b719-d0a135fa4869)

Step 6- Use rockyou.txt as a wordlist for the brute force attack by utilizing the first 20 lines. Open rockyou.txt in Nano and add any password guesses you have for the AD user. We will use RDP in conjunction with Crowbar to brute force the password for the AD user Ana Knapp
![AD crowbar password break](https://github.com/user-attachments/assets/177e1d59-cdb4-4f47-87c7-005c0b66f807)

Step 7- Now, open the Splunk server to review the telemetry generated during the brute force attack. Filter the results to search for failed login attempts for the user "Aknapp" in the index endpoint with the search query index=endpoint Aknapp 4625. You should observe events with ID 4625, indicating failed login attempts. Look specifically for Event ID 4265, which signifies that the account failed to log on. 
![Splunk failed login attempts on Aknapp event code 4625 ](https://github.com/user-attachments/assets/915d50bd-4906-4d5a-a507-9306151a1a0b)

Step 8- Install Atomic Red Team on the Windows 10 client. Use the MITRE ATT&CK Framework to select an attack technique to execute against the AD user. For instance, I utilized technique T1136.001 to create a new Windows admin user in Active Directory. Subsequently, I verified the account's creation using Splunk.
![Screenshot 2024-05-04 173203](https://github.com/user-attachments/assets/ac688b97-4c96-45c5-8f65-ff4df79e6888)
![New Local User in Splunk](https://github.com/user-attachments/assets/1d0140e4-e23d-4abc-8894-ab4ed7fc3a0a)

