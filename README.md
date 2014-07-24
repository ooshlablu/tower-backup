tower-backup
============

These playbooks are meant to accomplish two functions:

- First to backup the configs, keys and relevant files plus the database of a Tower install
- Second to restore the above to a freshly installed and working second Tower install.

To use:
-------

- Ensure your Tower host(s) are properly set up with ssh keys or user/pass variables in the hosts file, and that user has sudo access (in testing, I used passwordless sudo access.  You can set sudo passwords for the ansible_ssh_user per the documentation if you need.)
- Modify hosts file to have the IP address of your Tower instance(s)
- If you are only backing up, set the restore variable to "no"
- If you are backing up tower1 and restoring it to another Tower host (tower2 in the hosts file) then set the restore variable to "yes"
- set your pulldest variable to the path of the local directory you want to pull the tower1 backup files to.  In this case, I pull to /tmp, however you could pull to /home/user/Documents/towerbackup (NOTE: no trailing slash in the variable, please.)
- run the following:
```
ansible-playbook backup1-restore2.yml -i hosts
```
