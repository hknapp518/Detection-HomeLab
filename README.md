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

Step 2- Open Windows Server VM and promote to a Domain Controller. Create two Organizational Units (IT & HR) and add users in Active Directory.
![Vittoria in HR](https://github.com/user-attachments/assets/a7257fe6-6109-4d51-a59d-e75a5b4502ad)
![Ana in Active Directory HR](https://github.com/user-attachments/assets/a17df7ba-ebaf-4eb0-a396-47f7e7f99df1)

Step 3- Configure the Windows 10 machine to join to the AD.
![configure my windows 10 machine to join to the AD](https://github.com/user-attachments/assets/77b67a1a-f57a-4f2d-b740-1a6ea0cdcc24)


