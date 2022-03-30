# Project-1
First project for cybersecurity bootcamp course
![Diagram drawio](https://user-images.githubusercontent.com/102194142/159622160-e5c2c093-1b0d-4bcf-a7f6-67a27de2eb99.png)

## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram]
Images/Project_1_Diagram.png 

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._
           my-playbook3.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
 A load balancer distributes traffic to servers to help minimize the servers from being overloaded. It also checks periodically to make sure the server is working prior to sending traffic.         
 A jump box is exposed to the public and acts as a barrier to to machines that are not exposed to the public. Acts like a "gateway router" (lecture 12.2).

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?_
 Watches which files have changed and when that occured. 
- _TODO: What does Metricbeat record?_
 Collects metrics (like statistics) from your system
The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web-1    |          | 10.0.0.5   | Linux            |
| Web2     |          | 10.0.0.6   | Linux            |
| Elk      |          | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_
68.6.172.173

Machines within the network can only be accessed by _____.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
Web-1 and Web2. Public IP addresses are 13.78.237.147

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 10.0.0.5 10.0.0.6    |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: It will eliminate the variablility between configurations

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...Configure Elk VM with Docker
- ...Install docker.io
- ...Install python3-pip
- ... Install docker module
- ... Download and launch a docker web container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output]
Images/elk_playbook.png

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5
- 10.0.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
The data from filebeat collects when files have been modified and when so observing log files. 
Metricbeat observes your system statistics like memory. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the anisble playbook file to /etc/ansible.
- Update the anisble playbook file to include...
- Run the playbook, and navigate to kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ 
ansible file and copied it to /etc/ansible.
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
The playbook file in order to run the playbook on a specific machine. To sepcify which machine to install the Elk server on versus which to install the Filebeat on is through the ansible Elk and Filebeat playbooks. 
- _Which URL do you navigate to in order to check that the ELK server is running?
http://[20.25.213.127]:5601/app/kibana. 

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
