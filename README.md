## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)
sysadmin@UbuntuDesktop:~/Pictures/Week13 HW Diagram.PNG
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
filebeat_playbook.yml
This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use: MetricBeat
  - Machines Web1, Web2, Web3
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly STABLE, in addition to restricting INTRUDERS to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
Segregation of the network and creating another step for intruders. 
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __Logs_ and system _Intrusion__.
- _TODO: What does Filebeat watch for?_ Saves specified logs and locations. It can push push or save this data to a chosen location
- _TODO: What does Metricbeat record?_Saves specified metrics of a machine's systems and services. 

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.1   | Linux            |
| Web-1    |Web Server| 13.83.47.88| Linux            |
| Web-2    |Web Server| 13.83.47.88| Linux            |
| Web-3    |Web-Server| 13.83.47.88| Linux            |
|Elk-Server|Data Proc | 10.0.0.4   | Linux            |
### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _Web Servers 1, 2, 3 machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_ SshFromJumpBox IP 10.0.0.4, JumpBoxSsh 67.182.239.97, 

Machines within the network can only be accessed by JumpBox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_ 
JumpBox Private IP 10.0.0.4
A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes/No              | 10.0.0.1 10.0.0.2    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_ 
You can automaticly spin up update dockers files.
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Install elastic search. This will help you search and is an analytics engine. It can index streams of logs and decoded network packets.
- Install Beats. Beats are open source data shippers and they act as agents on servers to send data to elastic search.
- Install MetricBeat. Metricbeat are operational data or scripts that can be run from terminal or powershell.
- Install Kibana. This is a open source analytics platform designed to work with elasticsearch.
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_ Webservers 10.0.0.5, 10.0.0.6, 10.0.0.8

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ MetricBeats and Filebeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._Filebeat collects logs of specific files set by system admin. Metricbeat collects system and services information set by system or security admin.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _config and playbook yml files__ file to ansible container_____.
- Update the __playbook___ file to include...host ip adresses, host names and save to locations
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_filebeat_playbook.yml and saved in ansible. metricbeat_playbook.yml and saves in ansible
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
