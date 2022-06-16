# Project1Repository
Project 1 Credentials
# Rodrigo_Quiroz_Project_1
Rodrigo’s class files Cyber Security Bootcamp
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![](Images/cloud infrastructure_.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible playbook (.yml) file may be used to install only certain pieces of it, such as Filebeat.

RodrigoQuirozElkProject1.yml
RodrigoQuirozMetricbeatProj1.yml
RodrigoQuirozPlaybookProj1.yml
RodrigoQuirozFilebeatProj1.yml
RodrigoQuirozPentestProj1.yml
RodrigoQuirozRemoveApacheProj1.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly effective & available, in addition to restricting traffic to the network. From a security standpoint, load balancers manage traffic spikes as well as prevent high traffic on a single server.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
What does Filebeat watch for?_Filebeat looks over log files and then sends information to programs (Elasticsearch).
What does Metricbeat record?_Metricbeat collects metric data from the Operating system as well as services running from the server.
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
|  Web 1   |Web server| 10.0.0.5   | Linux            |
|  Web 2   |Web server| 10.0.0.6   | Linux            |
|  Elk     |  Server  | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: Workstation IP address

Machines within the network can only be accessed by ssh port.
Which machine did you allow to access your ELK VM? What was its IP address?_Jumpbox 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |     No              | 10.0.0.1 10.0.0.2    |
|     web1 |     No              |     10.0.0.5         |
|     web2 |     No              |     10.0.0.6         |
|     Elk  |     No              |    workstation IP TCP|
|Load balancer|     No           |Workstation IP HTTP80 |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
What is the main advantage of automating configuration with Ansible? With Ansible you can create Playbooks which automates how you want to deploy or setup your vm. You wont have to write code for the setup every single time.

The playbook implements the following tasks:
In 3-5 bullets, explain the steps of the ELK installation play. 
~ Docker Installation
~ Increase Memory
~ use sysctl module
~ use docker module

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Update the path with the name of your screenshot of docker ps output](Images/ELK_docker_ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
List the IP addresses of the machines you are monitoring:\
10.0.0.5 & 10.0.0.6

We have installed the following Beats on these machines:
Filebeat & Metricbeat

These Beats allow us to collect the following information from each machine:

Filebeat monitors the log files and send them to programs like Elasticsearch/Logstash. Metricbeat collects metrics on the system.


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the playbook file to ansible node.
- Update the host file to include the webservers & Elk Server
- Run the playbook, and navigate to Kibana (http://[Host IP]/app/kibana#/home) to check that the installation worked as expected.

Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ the yml file refers to the playbook
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? /etc/ansible/hosts
- _Which URL do you navigate to in order to check that the ELK server is running? http://[ELK-VM IP]:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

Assuming you are in root: apt install docker.io, container docker start, systemctl status docker, docker attach
