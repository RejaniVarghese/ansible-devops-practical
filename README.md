# DevOps Practical Mission – Ansible Automation using AWS and Docker

## Project Overview

This project demonstrates the implementation of Infrastructure Automation using AWS EC2, Ansible, Docker, Ansible Navigator, Roles, Templates, Inventory Management, and GitHub Version Control.

The project was implemented using Amazon Linux 2023 and follows the requirements specified in the DevOps Practical Mission assignment.

---

## Technologies Used

* AWS EC2
* Amazon Linux 2023
* Docker
* Ansible Navigator
* Ansible Roles
* Jinja2 Templates
* Git
* GitHub

---

## Mission 1 – Build and Configure an Ansible Automation Environment

### Infrastructure Setup

Three EC2 instances were created in the Mumbai Region:

| Instance Name  | Purpose              |
| -------------- | -------------------- |
| mumbai-control | Ansible Control Node |
| mumbai-client1 | Development Node     |
| mumbai-client2 | Test Node            |

### User Configuration

* Created a user named `devops` on all servers.
* Configured SSH key-based authentication between the control node and managed nodes.
* Created the Ansible project directory under `/home/devops/ansible`.

---

## Project Structure

```text
ansible/
├── inventory
├── ansible.cfg
├── packages.yml
├── myrole.yml
├── issue.yml
├── custom.yml
└── roles
    └── myrole
        ├── tasks
        │   └── main.yml
        └── templates
            └── index.j2
```

---

## Tasks Completed

### Task 1 – AWS Infrastructure Setup

* Created three Amazon Linux 2023 EC2 instances.
* Configured networking and security group rules.
* Created and configured the devops user.

### Task 2 – Ansible Environment Setup

* Installed Docker.
* Installed Ansible Navigator.
* Configured inventory and ansible.cfg.
* Verified connectivity between control and client nodes.

### Task 3 – Package Management Automation

Installed the following packages:

* MariaDB
* PHP

For the Development Group:

* Development Tools Package Group
* System Package Updates

### Task 4 – Role Creation and Template Deployment

Created a reusable Ansible role:

```text
roles/myrole
```

The role performs:

* Apache installation
* Apache service configuration
* Web page deployment using a Jinja2 template

Template output:

```text
Welcome to <hostname> on <IP Address>
```

### Task 5 – Content Modification

Modified:

```text
/etc/issue
```

Values configured:

Development Hosts:

```text
development
```

Test Hosts:

```text
test
```

### Task 6 – Custom Web Server Configuration

Configured Apache on Development hosts.

Custom document root:

```text
/webdev
```

Created symbolic link:

```text
/webdev -> /var/www/html
```

Web page content:

```text
development
```

### Task 7 – Git Integration

Uploaded project files to a GitHub repository for version control and future infrastructure recreation.

---

## Mission 2 – Infrastructure Recreation Using Git

A new environment was created in the Hyderabad Region.

Instances:

| Instance Name     | Purpose          |
| ----------------- | ---------------- |
| hyderabad-control | Control Node     |
| hyderabad-client1 | Development Node |
| hyderabad-client2 | Test Node        |

User created:

```text
clone
```

Tasks performed:

* Cloned the Git repository.
* Updated inventory for the Hyderabad environment.
* Verified SSH connectivity.
* Executed all Ansible playbooks using Ansible Navigator.

---

## Playbook Execution

Examples:

```bash
ansible-navigator run packages.yml -m stdout

ansible-navigator run myrole.yml -m stdout

ansible-navigator run issue.yml -m stdout

ansible-navigator run custom.yml -m stdout
```

---

## Verification Performed

* SSH Connectivity Verification
* Package Installation Verification
* Apache Service Verification
* Role Execution Verification
* Template Deployment Verification
* /etc/issue Modification Verification
* Custom Web Server Verification
* Git Repository Verification

---

## Learning Outcomes

This project provided hands-on experience in:

* AWS EC2 Infrastructure Management
* Linux User Administration
* SSH Key Authentication
* Docker-Based Ansible Execution
* Inventory Management
* Ansible Playbooks
* Ansible Roles
* Jinja2 Templates
* Configuration Management
* Git Version Control
* GitHub Repository Management
* Infrastructure as Code (IaC)

---

## Author

**Rejani Mary Varghese**

DevOps Practical Mission Project

Platform: AWS EC2 (Amazon Linux 2023)

Automation Tool: Docker-based Ansible Navigator

Version Control: Git and GitHub

---

## Conclusion

This project successfully demonstrated the implementation of a complete Ansible automation environment using AWS EC2 instances running Amazon Linux 2023. Docker and Ansible Navigator were used for containerized playbook execution, while Git and GitHub were used for version control and infrastructure recreation. The project highlighted the benefits of automation, consistency, scalability, and Infrastructure as Code practices in modern DevOps environments.
