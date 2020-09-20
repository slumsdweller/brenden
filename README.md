# brenden
GitHub Repository


Automated ELK Stack Deployment
The files in this repository were used to configure the network depicted below.
 
These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the install-elk.yml file may be used to install only certain pieces of it, such as Filebeat.
This document contains the following details:

•	Description of the Topology

•	Access Policies

•	ELK Configuration 

o	Beats in Use

o	Machines Being Monitored

•	How to Use the Ansible Build


Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly secure, in addition to restricting only allowed IPs to connect to the network.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system metrics.
The configuration details of each machine may be found below. 

| Name        | Function | IP Address | Operating System |
|--------------|----------|------------|------------------|
| Jump Box    | Gateway  | 10.1.0.8   | Linux            |
| Web-3       | DVWA     | 10.1.0.11  | Linux            |
| Project-1VM | ELK      | 10.2.0.5   | Linux            |

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 75.132.235.87
 
 
A summary of the access policies in place can be found in the table below.
Name	Publicly Accessible	Allowed IP Addresses
Jump Box	Yes/No	75.132.235.87
Web-3	No	10.1.0.8
	
	
Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because ansible makes it much easier for creating computer software and processes used day to day. Ansible helps a lot out with IAC because of overwatching and management of infrastructure.

The playbook implements the following tasks:
•	Installing python3
•	Installing docker.io
•	Installing docker
•	Increasing virtual memory
•	Enabling docker service

The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.
  
Target Machines & Beats
This ELK server is configured to monitor the following machines:
•	10.1.0.9, 10.1.0.10, 10.1.0.11, 10.2.0.5

We have installed the following Beats on these machines:
•	Filebeat
 
 
These Beats allow us to collect the following information from each machine:
•	Filebeat is used for monitoring system logs being edited and locations specified by the admin. Filebeat does not only monitor logs, but also collects log events and             forwards to them to Elasticsearch or Logstash for indexing. This being used effectively on a network is incredibly useful and ensures security.

Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:
•	Copy the install-elk.yml file to machines that will use ELK.
•	Update the config file to include which machines will install either ELK or Filebeat
•	Run the playbook, and navigate to http://[elkserverpublicip]:5601/app/kibana#/home to check 
