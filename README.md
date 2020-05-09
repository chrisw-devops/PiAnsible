# Pi Ansible

This repository includes all the building steps to setup my pi nodes in a repeatable and reusable way.

## Getting Started

### Installing Ansible

_These instructions have been created against Ubuntu 20.04. Any other OS instructions may vary._

Get all available packages from apt repos
```bash
sudo apt-get update
```

Install the PIP package manager for Python
```bash
sudo apt-get install python3-pip -y
```

Install the latest version of Ansible
```bash
sudo pip3 install ansible
```

(Optional) If you will be connecting via password to a node install the sshpass program
```bash
sudo apt-get install sshpass -y
```

### Cloning repository

Install git
```bash
sudo apt-get install git
```

Validate that your SSH agent is able to connect to GitHub
```bash
ssh -T git@github.com
```

Clone the repository to the home directory of the current user
```bash
cd ~ && git clone git@github.com:chrisw-devops/PiAnsible.git
```

## Ansible Playbooks

Before running any playbooks make sure you are in the home directory on the local server. Run the following comand.

```bash
cd ~/PiAnsible
```

### Master-node

#### Commands

If you are using an SSH key to connect to nodes run the following
```bash
 ansible-playbook -i inventories/home/hosts master-node.yml
```

If you are entering a password run the following command
```bash
ansible-playbook -i inventories/home/hosts master-node.yml --ask-pass
```