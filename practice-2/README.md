# Ansible Practice 2 - Add tasks and Modules


1. Use APT module to install services
2. Use service module to manage services
3. Use ansible to reboot webstack

### Install Services using APT module
https://docs.ansible.com/ansible/latest/modules/apt_module.html
``` shell
ansible all -i practice-2/hosts --become -m apt -a "update_cache=yes"
ansible webservers -i practice-2/hosts --become -m apt -a "name=apache2 state=present"
ansible database -i practice-2/hosts --become -m apt -a "name=mysql-server state=present"
```

### Restart Services using Service module
https://docs.ansible.com/ansible/latest/modules/service_module.html
``` shell
ansible database -i practice-2/hosts -m service -a "name=mysql state=started"
ansible database --become -i practice-2/hosts -m service -a "name=mysql state=restarted"
 ```

### Use Ansible to reboot the webstack
``` shell
ansible webstack -i practice-2/hosts --become -a "reboot --reboot"
 ```