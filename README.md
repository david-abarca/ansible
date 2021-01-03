# ansible
Ansible repo containing various projects used for both Vagrant and external systems.

# Roles
## config_linux_base
Provision new linux host (RedHat and Debian family) with basic software dotfiles (private).
- desired software, for eg. vim, exa, tree, htop etc.
- new system admin user (only SSH auth)
- firewall enforced
- journalctl persistence
- SSHD secured, for eg. no root login, no password auth etc.
- Fail2ban enforced

To run this playbook you need to configure your own dotfiles and environment variables, for eg.

```
ANSIBLE_ADMIN=my_admin_user
ANSIBLE_SSH_PRIVATE_KEY=repo.com_key_name
```
