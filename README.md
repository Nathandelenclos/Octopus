
# Octopus

This fourth DevOps project will introduce you to another aspect of the notion of automation: configuration management.
You will learn how to use a solid, 10-year old, and still strong, tool: Ansible. 
You will write playbooks, create your inventory, and be the master of the automated configuration tentacles you are going to control, in order to automatically deploy an entire application to remote machines.
In the end, you will have a handy knowledge of a clean and efficient way of configuring machines, as well as documenting the way the infrastructure is set up (is that another instance of infrastructure-as-code?), to help you set up environments in which you will be able to deploy your projects with just one command, and that is mega cool.


## Environment Variables

To run this project, you will need to add the following environment variables to your environment.

`ANSIBLE_VAULT_PASSWORD_FILE` Path to the file that contains the password.


## Installation

Check the contents of the encrypt variables.

```bash
ansible-vault edit group_vars/all.yml
```
    
Modify all IPs in the inventory.yml file

```yml
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

```bash
ansible-playbook -i inventory.yml playbook.yml
```

Now you can access poll platform on host ip poll-1. (example: http://34.77.149.226)

And you can see the results of the poll on the ip of the host result-1. (example: http://35.195.128.93)

