
# Octopus
***
[![version](https://img.shields.io/badge/Version-1.0-vert)](https://github.com/Nathandelenclos/Octopus)

Our project is focused on automating the configuration and deployment process of an application to remote machines using Ansible, a powerful configuration management tool. Through this project, we will learn how to write playbooks and manage inventories, gaining practical knowledge of the most effective and efficient ways to configure machines. Our ultimate goal is to create stable and reliable environments for deploying our projects with just one command, saving us valuable time and preventing costly mistakes. By the end of the project, we will have developed a solid understanding of configuration management, giving us enhanced confidence in deploying our projects.

***
## Table of Contents

-  [About](#about)
-  [Prerequisites](#prerequisites)
-  [Environment](#env)
-  [Install](#installation)
-  [Usage/Examples](#usage)
-  [Demo](#demo)
-  [Contact](#contact)
-  [Subject](#subject)
-  [License](#license)
***

## About
<div id="about"></div>
Our DevOps project focuses on configuration management and automating the process of deploying an application to remote machines. To achieve this goal, we are using Ansible, a 10-year-old tool that is known for its robustness and effectiveness in configuration management. We write playbooks to describe the tasks to be performed and configure our inventory to define the machines to be configured.

During the project, we are mastering automated configuration by using Ansible to deploy the application. We are gaining practical knowledge of how to configure machines in a clean and efficient way, and documenting how the infrastructure is set up to help us create environments in which we can deploy our projects with just one command.

The ultimate goal is to create stable and reliable environments for deploying our projects with ease. We are confident that automated configuration management will save us time and prevent costly mistakes. By the end of the project, we will have developed a solid expertise in configuration management and be able to deploy our projects with enhanced confidence.
***
## Prerequisites
<div id="prerequisites"></div>

This project uses [Ansible](https://www.ansible.com/). 

## Environment Variables
<div id="env"></div>

To run this project, you will need to add the following environment variables to your environment.

`ANSIBLE_VAULT_PASSWORD_FILE` Path to the file that contains the password.


## Install
<div id="installation"></div>

Setup and encrypt your variables.

```bash
copy group_vars/example.yml group_vars/all.yml
nano group_vars/all.yml
ansible-vault encrypt group_vars/all.yml
```

```yml
# group_vars/example.yml
postgresql_pass:
postgresql_user:
postgresql_db:
postgresql_port:
postgresql_host:

redis_port:
redis_bind:
redis_dir:
redis_host:
result_port:
```
    
Modify all IPs in the inventory.yml file

```yml
# inventory.yml
all:
  children:
    redis:
      hosts:
        redis-1:
          ansible_host: 0.0.0.0
    postgres:
      hosts:
        postgres-1:
          ansible_host: 0.0.0.0
    poll:
      hosts:
        poll-1:
          ansible_host: 0.0.0.0
    result:
      hosts:
        result-1:
          ansible_host: 0.0.0.0 
    worker:
      hosts:
        worker-1:
          ansible_host: 0.0.0.0

```

## Usage/Examples
<div id="usage"></div>

```bash
ansible-playbook -i inventory.yml playbook.yml
```

Now you can access poll platform on host ip poll-1.

And you can see the results of the poll on the ip of the host result-1.

## Demo
<div id="demo"></div>

[![Video](https://zupimages.net/up/23/14/vos3.png)](https://youtu.be/3BQnNwuDkA4)
 
## Contact
<div id="contact"></div>

-  [Epitech](https://www.epitech.eu/) - Product Owner.
-  [Nathan DELENCLOS](mailto:nathan.delenclos@epitech.eu) - Developer

## Subject
<div id="subject"></div>

[B-DOP-400_octopus.pdf](https://github.com/Nathandelenclos/Octopus/blob/main/B-DOP-400_octopus.pdf) 

## License
<div id="license"></div>

[ISC](LICENSE) © EPITECH
