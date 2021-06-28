Ansible Role: Hostname
=========

Description
------------

This role will set hostname on any target host.
By default hostname is same as `inventory_hostname`,
but can be set as different by using vars. Updates hosts file too.

Requirements
------------

No requiments.

- CentOs 5 requires **python-simplejson** package installed for general Ansible work. 
- Ubuntu 16.04 has no **python** package installed by default. It is required for general Ansible to work. 

Role Variables
--------------

| Variable                     | Default                  | Explanation                                                    |
| ---------------------------- | ------------------------ | -------------------------------------------------------------- |
| hostname_hosts_file_location | "/etc/hosts"             | Hosts file location.                                           |
| hostname_hosts_backup        | False                    | You can make backup of hosts file before changes will be made. |
| hostname_fqdn_full           | inventory_hostname       | By default this role uses **inventory_hostname** from inventory file to get host hostname, but you can set **hostname_fqdn_full** and **hostname_fqdn_short** to change this behavior. |
| hostname_fqdn_short          | inventory_hostname_short |                                                                |
| hostname_hosts_ipv4_enabled  | true                     | When true, add an IPv4 entry to /etc/hosts.                    |
| hostname_hosts_ipv6_enabled  | true                     | When true, add an IPv6 entry to /etc/hosts.                    |

Dependencies
------------

Independent role.

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
    - { role: insspb.hostname }
```
	
Development information
----------------
This role is developed with community help. 

Process of development follows this rule: 

   - You are free to add any pull request to develop branch. All request will be answered in timely manner. 
   - If you want to made any contribution, but do not know where to start - check issues.
   - Master branch updated just after significant changes in develop.
   - Please include documentation for new features. 
   - Please use variables.
   - Please do not forget to set defaults.
   - Please do your best to keep backward compatibility if possible.
   - Please use packet installation as default software installation method. Source installation must be optional anywhere if possible.
   - Please use official software developers repositories instead of general Debian/Ubuntu/Centos etc for main application. 
   - Do you best to keep role independent from any other roles. User must have the way to choose what roles to use.

License
-------

MIT

Author Information
------------------

This role is a fork of https://github.com/insspb/ansible-role-hostname.
