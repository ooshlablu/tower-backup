# About
This playbook was suggested to us by James Martin over at ansible. It is originally pulled from [[https://github.com/dfederlein/tower-backup]].  

# Use
This playbook has been sligtly modified from the original version to be more dynamically configurable, per our standards with ansible tower.  

### Variables
* `tower-backup`: Defaults to `true`. When set to `true`, this playbook will backup all Tower configs, keys, and the database. When set to `false` this playbook will apply the backups retrieved from the master.
* `pulldest`: The directory where all backups should be sent.
