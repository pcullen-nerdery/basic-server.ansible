# Provisioning for a basic server

This will provision a fresh linux server (tested with ubuntu 14.04) with a few 
basic pieces of functionality.
	- a list of users with passwords and ssh keys (as defined in an encrypted
	vars file)
	- new relic server monitoring
	- a basic nginx site


This assumes your computer has access to a host named basic-server.vagrant on
your network.

```
ansible-galaxy install -r requirements.yml
ansible-playbook -i hosts site.yml --ask-vault-pass
```
