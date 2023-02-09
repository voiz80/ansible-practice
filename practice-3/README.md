# Ansible Practice 3 - Playbooks and Templates

1. Create playbook and look over the details of the YAML file
2. Create Templates
3. Run the playbook
4. Test connectivity to server

### Run playbook
``` shell
ansible-playbook -i practice-3/hosts -K practice-3/playbook1.yml
```

### Test Connectivity to server
``` shell
curl web01:8000
```