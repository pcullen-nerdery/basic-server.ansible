# Provisioning for a basic server

This will provision a fresh linux server (tested with ubuntu 14.04) with a few
basic pieces of functionality.

- a list of users with passwords and ssh keys (as defined in an encrypted
vars file)
- new relic server monitoring
- a basic nginx site


This assumes your computer has access to a host named basic-server.vagrant on
your network.

This also assumes you know what the vault password is :)

```
ansible-galaxy install -r requirements.yml
ansible-playbook -i hosts site.yml --ask-vault-pass
```

a few ansible ad-hoc commands
```
ansible all -m ping -i hosts

# -s makes it run with sudo
ansible all -s -m shell -a 'apt-get install nginx'
ansible all -s -m apt -a 'pkg=nginx state=installed update_cache=true'
```

great tutorial 
https://serversforhackers.com/an-ansible-tutorial
