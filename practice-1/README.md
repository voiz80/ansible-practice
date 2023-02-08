# Ansible Practice 1 - Installation and Inventory file basics

1. ssh to our ansible-host
2. Copy /vagrant/hosts_file to /etc/hosts 
3. Install ansible
4. Create an inventory file named hosts
5. Test out a command
6. Generate SSH Keys and copy to hosts
7. Test running ad-hoc commands to all hosts
8. Install python-simplejson module. This allows clients to be fully managed.

### Setup Vagrant and connect to ansible-control server
``` shell
 vagrant up
 vagrant ssh ansible-host
```

### Copy hosts file on ansible-host
``` shell
cp /vagrant/hosts_file /etc/hosts 
```

### Install Ansible
``` shell
 sudo apt-get install ansible
```

### Create a SSH key and copy to all servers
``` shell
ssh-keygen
ssh-copy-id localhost
ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer && ssh-copy-id db01
```

### Run a ad-hoc command to the webstack group
``` shell
ansible webstack -i practice-1/hosts -m command -a hostname
```

### Install python-simplejson
``` shell
ansible all -i practice-1/hosts -m command -a 'sudo apt-get -y install python-simplejson'
```
