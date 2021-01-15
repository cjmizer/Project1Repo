## Project 1 - Automated ELK Stack Deployment

Within this repository you will find the files used to configure the cloud network in Microsoft Azure.

Below is a visual overview of the network 

(Diagrams/HW12 Mizer.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the file may be used to install only certain pieces of it, such as Filebeat.

The configuration details of each machine may be found below.

| Name                 | Function | IP Address | Operating System |
|----------------------|----------|------------|------------------|
| Jump-Box-Provisioner | Gateway  | 10.0.0.9   | Linux            |
| Web-1                | Server   | 10.0.0.8   | Linux            |
| Web-2                | Server   | 10.0.0.6   | Linux            |
| Web-Redundancy       | Server   | 10.0.0.11  | Linux            |
| ELKUbuntuVM          |Monitoring| 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet.
The Jump-box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses 

SSH port 22 

Machines within the network can only be accessed by Jump-Box-Provisioner.
Which machine did you allow to access your ELK VM - Jump-Box-Provisioner.

Private IP address  - 10.0.0.9

A summary of the access policies in place can be found in the table below.

| Name                 | Publicly Accessible | Allowed IP Addresses  |
|----------------------|---------------------|-----------------------|
| Jump-Box-Provisioner | Yes                 |(My Local IP)/10.0.0.x |
| Web-1                | No                  | 10.0.0.9              |
| Web-2                | No                  | 10.0.0.9              |
| Web-Redundancy       | No                  | 10.0.0.9              |
| ELKUbuntuVM          | No                  | 10.0.0.9              |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
Install docker.io 
Install pip3
Install Docker python module


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/sudodockerpselk761.PNG)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:

Webserver 1 10.0.0.10

Webserver 2 10.0.0.11

We have installed Metricbeat and filebeat these machines:

These Beats allow us to collect the following information from each machine:

Metricbeat collects up content on server, then take metrics from the operating system to out configuration.

Filebeat reviews data logs then sends it to the correct output. unit.

### Using the Playbook

In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:

-Copy the Playbook file to Ansible.

nano ansible.cfg

-Update the host file to include both webserver and ELK.


Webservers

10.0.0.8 ansible_python_interpreter=/usr/bin/python3

10.0.0.6 ansible_python_interpreter=/usr/bin/python3

10.0.0.11 ansible_python_interpreter=/usr/bin/python3

Elk

10.1.0.4 ansible_python_interpreter=/usr/bin/python3

###### note: a large portion of this readme was copy/pasted and edited to fit my project. 
