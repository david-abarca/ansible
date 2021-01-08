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
SSH_DOTFILES_KEY=repo.com_key_name
```
## config_admin_user
Configure linux admin since root will be disabled as much as possible (SSH for eg.).
## config_macos
Ansible role for configuring and updating a macOS host. Over time I'll add more features the more I figgure out how to automate.
- Homebrew (normal and cask)
- System Finder
- System Dock (inkl. Mission Control)
- System TextEdit
- System language & region

Below is required to run homebrew_cask installations.
```
ansible-galaxy collection install -r requirements.yml
```
Once requirements are met simply run the playbook.
```
ansible-playbook config_macos.yml -e 'target=my_macos'
```
